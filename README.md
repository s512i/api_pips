# api_pips
Описание функций API PIPS.by

HOST: http://api.evan.by:9090/pips_test/hs/v1/

В каждом запросе в заголовках передается логин и пароль пользователя

## Получение списка заказов [/order_list]
Получение списка заказов доступных пользователю - это его заказы и заказы субклиентов
Список содержит основные атрибуты заказов

### Список [GET]
	
	+ Request
	
		+ Headers
			
			login: text/plain - логин пользователя
			password: text/plain - пароль пользователя
	
	+ Response 200 (application/json)

		+ Body

            {
			"result": "ok",
			"count": 2,
			"orders": [
				{
				"num": 6,
				"date": "2022-01-27T16:20:44",
				"sum": 3150.3,
				"status": "Новый",
				"goods_list": "Электрический котел ЭВАН EXPERT PLUS-5 1шт 1 604,75 : 1 604,75\nЭлектроотопительный котел Expert 7 1шт 1 545,55 : 1 545,55\n",
				"subclient_presentation": "",
				"subclient_id": "",
				"subclient_unp": "",
				"client_id": 282,
				"client_name": "Реут Геннадий Николаевич ИП",
				"client_unp": "691440228"
				},
				{
				"num": 7,
				"date": "2022-01-27T17:04:02",
				"sum": 3150.3,
				"status": "Новый",
				"goods_list": "Электрический котел ЭВАН EXPERT PLUS-5 1шт 1 604,75 : 1 604,75\nЭлектроотопительный котел Expert 7 1шт 1 545,55 : 1 545,55\n",
				"subclient_presentation": "Реут Геннадий Николаевич ИП",
				"subclient_id": 282,
				"subclient_unp": "691440228",
				"client_id": 1,
				"client_name": "Автотрейдинвест",
				"client_unp": "192641021"}
				]
			}