# ADAL market

Кликабельный прототип совместных закупок через лидеров ЖК (статический сайт, один файл `index.html`).

Деплой: Render Static Site, publish path `./`, без сборки.

## База данных

Supabase (проект reels-sabak, таблицы с префиксом `adal_`). Сайт ходит в REST API с публичным ключом:
- читает `adal_products` и `adal_zk` (код лидера скрыт);
- создаёт заказы через `rpc/adal_place_order` (цены считаются на сервере);
- заявки лидеров — `rpc/adal_submit_application`;
- кабинет лидера — `rpc/adal_leader_data` и `rpc/adal_leader_action` по коду доступа (10 ошибок за 15 минут блокируют вход).

Демо-доступ лидера: ЖК Северный парк, код `123456`.
