##### **БИЗНЕСОВЫЕ**
2. Редизайн сайта клиентской части
3. Приложение для телефонов (с вероятностью 99% не нужно, нужно еще подумать, дорогое решение, нужно искать других разработчиков)
4. *ДЛЯ ГЕННАДИЯ* Раздел "Согласование"
   - Согласование при создании бесплатных билетов
   - Согласование изменений в маршруте(цена, машина, даты следования, выключение даты продажи)
1. *ДЛЯ ГЕННАДИЯ* Дополнить раздел аналитики (подумать какие еще метрики необходимы)
   - Средняя загруженность рейса от месяца к Месяцу 
   - разбитие дохода от агенств, отдельным блкомо вывести колво билетов
2. Темная тема в админ панели(для удобной работы вечером)
3. Отзывы для клиентов после рейса с возможностью ответа на них
4. Реализовать [[BRAINSTORM|дополнительные]] рейсы
5. Добавить остановку высадки для рейсов у которых пункт прибытия "Урай" Обсудить как это нужно сделать, чтобы все указывали остановки, или только водители выбирали


##### **ТЕХНИЧЕСКИЕ**
2. При отправке смс кода отправлять @tk999.ru для автоматической подстановки кода в поле ввода
3. Таймер в рядом с кнопкой возврата должен ссылаться на серверную дату, а не на клиентскую
4. Сделать защиту для серверных роутов, добавить проверку дополнительную проверку на роль, чтобы к роутам /dashboard могли делать все кроме роли User
5. Сделать пагинацию изменений по примеру подмены машины

##### **ВИЗУАЛЬНЫЕ**
1. Сделать белым backgrund у body, и красить отдельные блоки страницы(для айфона)
2. Добавить стрелочку вниз у иконки открытия главного меню на клиентской части




Тема: Предложение по улучшению системы управления доступом

Проблема:
Текущая система ролей ограничивает гибкость управления правами сотрудников. 
Любые изменения требуют участия разработчиков и обновление сайта.

Влияние на бизнес:
- Медленная адаптация под новые процессы
- Ограничения в организационной структуре  
- Дополнительные затраты на разработку

Решение:
Создать систему с гибким управлением правами через интерфейс, где можно:
- Создавать новые роли без программистов
- Точечно настраивать права сотрудников
- Точечно настраивать права конкретных ролей

Сроки: 3-4 недели

Ожидаемый результат:
Полная автономность в управлении правами доступа, можно например Надежду наделить правами для редактирования ролей









Предложение по улучшению контроля ценообразования
Проблема:
Текущая система управления ценами на билеты имеет критические недостатки в области контроля и планирования. Любой диспетчер может изменить цену в любой момент без согласования и предварительного уведомления.

Как происходит сейчас:
Диспетчер Ваня в 15:30 решил устроить саботаж, и поменял на 850₽. Клиенты, которые час назад видели одну цену, теперь видят другую. Руководство узнает об этом случайно
Решение:
Создать систему планового управления ценами с разграничением доступа:
Контроль доступа:

- Только назначенные ответственные лица могут планировать изменения цен
- Диспетчеры работают с установленными ценами, но не могут их менять

Плановые изменения:

Возможность заранее запланировать: "с 1 августа цена меняется с 700₽ на 800₽"
Клиенты и сотрудники заранее знают о предстоящих изменениях

Прозрачность:
Полная история: кто, когда и почему изменил цену
Возможность отменить запланированные изменения до их вступления в силу

Сроки: 1-2 недели
Ожидаемый результат:

Централизованный контроль: только Елена может планировать изменения цен
Прозрачность: полная отчетность по всем изменениям цен
Защита от ошибок: исключены случайные и несанкционированные изменения
Профессиональный подход: клиенты получают уведомления о предстоящих изменениях

Пример использования:
"Елена Сергеевна 15 июля планирует изменение: с 25 июля цена на маршрут Москва-СПб меняется с 700₽ на 800₽ в связи с ростом операционных расходов. Все диспетчеры видят эту информацию и могут предупреждать клиентов заранее."
Результат: организованная система вместо хаоса, ответственность вместо случайности.