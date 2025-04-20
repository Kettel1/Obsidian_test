Сделать и выгрузить дамп на ПК
 `ssh tk999`
 `docker compose exec mysql mysqldump -uroot -pexample tk999 > PROD_DUMP_30_APR.sql`
 `scp tk999:/root/stage1/PROD_DUMP_30_APR.sql ./Desktop/DUMPS`
 `rm PROD_DUMP_08_APR.sql`

Запуск скриптов на SSH
`docker compose exec runner node ./prisma/bin/deleteEmptyOrders.js`

Зайти в базу на проде
`docker compose exec mysql mysql -h 127.0.0.1 -P 3306 -uroot -pexample`

Полезные комадны MYSQL
1. Удалить билет
`DELETE FROM orders WHERE id IN (121534, 122108);`
2. Обновить роль у пользователя
`UPDATE users SET role = 'Developer' WHERE id = 1301;`


DELETE FROM tickets WHERE id IN (151142);


UPDATE users SET role = 'Dispatcher' WHERE id = 6630;

Пример запрос для тестового отправки письма
`curl -X POST -H "Content-Type: application/json" -d '{"id": "89547"}' http://localhost:3001/api/ticket/email`


Количетсво билетов в промежутке по времени
 `const sixDaysAgo = addDays(startOfDay(new Date()), -60);`

  `const tickets = await prisma.ticket.findMany({`
    `where: {`
      `route_id: 10,`
      `order: {`
        `author_type: "agentHM",`
      `},`
      `created_at: {`
        `gte: sixDaysAgo, // Больше или равно 60 дней назад`
        `lt: new Date(), // Меньше текущей даты и времени`
      `},`
    `},`
  `});`

  `const ticketsBetweenElevenAndTwelve = tickets.filter((ticket) => {`
    `const elevenAM = new Date(ticket.created_at);`
    `elevenAM.setHours(15, 30, 0, 0); // Установим время 11:00`

    `const twelvePM = new Date(ticket.created_at);`
    `twelvePM.setHours(16, 0, 0, 0); // Установим время 12:00`

    `if (`
      `isWithinInterval(ticket.created_at, {`
        `start: elevenAM,`
        `end: twelvePM,`
      `})`
    `) {`
      `console.log({`
        `ticket_id: ticket.id,`
      `});`
      `return true;`
    `} else {`
      `return false;`
    `}`
  `});`



Здравствуйте! Вас приветствует транспортная компания 999. Приобрести билет теперь можно в нашей кассе по адресу г. Урай, Западный 15А (Здание паровозик) или на сайте tk999.ru. Оставайтесь на линии, мы соединяем вас с оператором, обратите внимание, что все разговоры записываются.

Здравствуйте! Вас приветствует транспортная компания 999. Мы принимаем звонки с 09:00 до 19:00. Вы можете приобрести билеты на нашем сайте tk999.ru. По остальным вопросам ждем вашего звонка в рабочее время. Всего доброго






Всем привет, начиная с сегодняшнего дня у нас по новому образу формируются цены для пассажиров с детьми, если кратко, то теперь на одного взрослого может приходиться 2 ребенка со скидкой. Например если пассажир везет детей, например 1 взрослый и 10 детей, скидка применится только двум детям, с остальных 8 детей будет взята полная стоимость за билет. Если едет 2 взрослых и 10 детей, то 4 детей проедут по скидке а 6 детей за полную стоимость. На сайте, при покупке билета клиентов это будет показано отдельной графой, какие места будут за полную стоимость у детского билета, а какие с 50% скидкой. Эти правила так же распространяются и на административный интерфейс. 

Кассиры, диспетчеры, и агентства будут продавать билеты по такой же логике, чтобы добиться этого поведения пришлось отказаться от функциональности указания "своей" цены за билет, это значит, что все вахтовики, транзитники, в общем вся эта ниша людей начиная с сегодняшнего дня должна будет платить полную стоимость за билет, не имеет знач