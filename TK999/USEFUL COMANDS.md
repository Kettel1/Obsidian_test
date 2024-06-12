Сделать и выгрузить дамп на ПК
1) `ssh tk999`
2) `docker compose exec mysql mysqldump -uroot -pexample tk999 > PROD_DUMP_30_APR.sql`
3) `scp tk999:/root/stage1/PROD_DUMP_30_APR.sql ./Desktop/DUMPS`
4) `rm PROD_DUMP_08_APR.sql`

Запуск скриптов на SSH
docker compose exec runner node ./prisma/bin/deleteEmptyOrders.js