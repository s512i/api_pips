# api_pips
Описание функций API PIPS.by

HOST: http://api.evan.by:9090/pips_test/hs/v1/

В каждом запросе в заголовках передается логин и пароль пользователя

## Получение списка заказов [/order_list/{?startdate}{?enddate}]
Получение списка заказов доступных пользователю - это его заказы и заказы субклиентов
Возможно получение списка за период, по умолчанию возвращает список за год
Список содержит основные атрибуты заказов

### Получить список [GET]
	
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
		
## Работа с данными заказов [/orders/?id[i]=n]			

Создание и редактирование заказов как своих, так и заказов субклиентов

### Получить данные заказов [GET]

+ Request 

	+ Headers
		
		login: text/plain - логин пользователя
		password: text/plain - пароль пользователя
		
	+ Parameters
	
		id: (array of numbers, required)
		
+ Response 200 (application/json)

	+ Body
	{
		"orders": [
			{
			"delivery": false,
			"delivery_address": "тудой",
			"delivery_date": "2022-02-22T00:00:00",
			"order_comment": "быстро",
			"order_date": "2022-02-20T14:03:10",
			"order_number": 20,
			"payment_form": "Безналичная",
			"subclient_requisites": "д. Заболотье, д. 2, +375 25 8974560",
			"subclient_name": "Сторонний контрагент",
			"subclient_presentation": "Иванов И.И.",
			"subclient_id": 0,
			"subclient_unp": "",
			"client_id": 282,
			"client_name": "Реут Геннадий Николаевич ИП",
			"client_unp": "691440228",
			"status": "Новый",
			"client_email": "genashut@mail.ru",
			"address_of_works": "д. Заболотье, д. 2,",
			"products": [
				{
				"art": "14322",
				"brand": "Эван",
				"product_name": "Электрический котел Warmos Comfort 8",
				"product_id": 11438,
				"stock_price": 1129.06,
				"retail_price": 1505,
				"vat_rate": 20,
				"vat": 188.18,
				"sum": 1129.06,
				"quantity": 1,
				"retail_sum": 1505,
				"vendor_name": "Автотрейдинвест",
				"vendor_id": 1,
				"store_name": "Сырокомли 7",
				"store_id": 7,
				"offer_name": "Опт 3",
				"offer_id": 19,
				"order_number": 20,
				"product_status": "",
				"purchase_price": 0,
				"supply_date": "0001-01-01T00:00:00"
				}
			],
			"works": [
				{
				"item_name": "Монтаж теплого пола, м.кв.",
				"quantity": 20,
				"price": 50,
				"sum": 1000,
				"order_number": 20
				},
				{
				"item_name": "Установка котла, шт",
				"quantity": 1,
				"price": 200,
				"sum": 200,
				"order_number": 20
				},
				{
				"item_name": "Разводка труб, м",
				"quantity": 40,
				"price": 25,
				"sum": 1000,
				"order_number": 20
				},
				{
				"item_name": "Установка радиаторов, шт",
				"quantity": 3,
				"price": 80,
				"sum": 240,
				"order_number": 20
				}
			],
			"expenses": [
				{
				"item_name": "Транспортные расходы, км",
				"quantity": 0,
				"price": 0,
				"sum": 0,
				"order_number": 20
				}
			],
			"serviсes_list": [
				{
				"item_name": "Установка радиаторов, шт"
				},
				{
				"item_name": "Установка котла, шт"
				},
				{
				"item_name": "Снятие/навеска радиатора"
				},
				{
				"item_name": "Сборка радиатора"
				}
			],
			"suppliers_orders_numbers": [
				{
				"client_order_number": 20,
				"order_number": 21,
				"supplier_name": "Автотрейдинвест",
				"payment_form": "Безналичная",
				"delivery": false,
				"delivery_date": "2022-02-22T00:00:00",
				"sum": 3308.3,
				"status": "Новый",
				"order_date": "2022-02-20T14:03:10"
			}
			]
			}
			],
			"result": "ok"
		}	
	
	
	