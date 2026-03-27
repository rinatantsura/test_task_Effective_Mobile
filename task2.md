Для поставленной задачи будет необходим один хердлер:
#### Path

```bash
GET /api/parthers/avaliable
```

Нам необходимо дать какую-то информацию серверу, чтобы рассчитать для пользователя доступные магазины. Для удобства и простоты, чтобы не передавать точные координаты пользователя, решила передавать почтовый индекс. И делаю пагинацию, для того чтобы данные подгружались постепенно, и объем данных контролировался клиентом
#### QueryParams
```json
?zip_code=10961&page=1&limit=10
```

Пример ответа:
#### Body

```json
{
	"avaliable_stores": [
		{
			"id": "uuid",
			"name": "Metro",
			"logo_path": "path_to_logo_fetch",
			"delivery_windows": [
				{
					"from": "time-stamp",
					"to": "time-stamp",
					"fast_delivery": {
						"from": 20,
						"to": 60
					}
				}
			],
			"external_link": "www.metro.com?promo_code=hire_me&user_trace=1243432"
		}
	],
	"page": 1,
	"total": 100	
}
```

Прикладываю swagger для этого endpoint:
