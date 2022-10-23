---
sidebar_position: 2
---

# Games actions

The **Routes** that exist are :

- POST → `http://127.0.0.1:3333/api/game/create`
- GET  → `http://127.0.0.1:3333/api/game/show/:id`
- GET  → `http://127.0.0.1:3333/api/game/all?categorie_name=France`

## Create a Game

When you create a user you have to know the username et email are unique:
- need to be auth and be an admin
### header you have to inform :
```http title="header"
  Authorization: Bearer eyJhbGciOiJSUzI1NiJ9.eyJkYXRhIjp7InVzZXJJZCI6MiwidXNlciI6eyJlbWFpbCI6ImNoYXByaXN0aUBnbWFpbC5jb20ifX0sImlhdCI6MTY2NjUyMTM0MCwiZXhwIjoxNjY2NTI0OTQwfQ.mG_goMcHAH3sCqzYiTKdocmbk_JZE8yEzJngrzcqTFRHDIXY9gGvJgrilFtZWjzFa6HW3R0jzjSaD3P1YJ2v0HqhfaH0F1PQnT9ymfauVPt6ahzRiF-6psLD3FLQg3bB8CkGVGnNX5QvL3Fg_lu5NswRraSqJM5ZjfUu9_6dF5tNbxH9MZZ7RQocDePpRl0XhesGXxxOHPYf8K3Tt5lPEkevJ9nytTpmHX0pYcto9Z3pA_sUr9rCH6PBx05f5L91LffRK1MXNNDGzOiFiaPUaWSXk_uPhniwtvoD6dtlvBjHSZqP_0CyyahmKac1KAIfB_L6mAUsCXKeA2IRnA5QPl4znGQI5BvZseDXfVjTWojNJP3dfLs-aFL3rvruldUfjFWIUF9h9led0EZdBK83bsFk7s9nF-cYpMvAHMYlkq1Wyep7UxYeCXh6Hl6iYg6SW_6WfLjzFw46sXY9vtJQElLc-8RduPeLi-XW2jDZfG-gkH1RTvR-dB5D2nZ2J0w94fewkV_FtM7nrraQVUga2UvmYl2HNZF9I2_2q4D1sAt_USjO3VzYkNjs4AWQfrotWGTNP08CBAQYuI7Bqt7TjATBqJU1iaewT4OG46uNkFyd1aO-ygVtyOlBVjKu5tFJ8QZmUaZQzypFTt0bJZ7VhCZakjSj0EL5a-nNDS6QMBo
```

### req.send() :
```json title="an exemple of request"
 { 
	"longitude" : "1,26195", 
	"latitude" : "45,8288", 
	"categorie_id" : 1
 } 
```
### req.response() :

```json title="an exemple of what the server return"
 { 
    "longitude" : "1,26195", 
	"latitude" : "45,8288", 
	"categorie_id" : 1
	"created_at": "2022-10-23T12:32:55.659+02:00", 
	"updated_at": "2022-10-23T12:32:55.659+02:00", 
	"id": 1
 }  

```
---

## Show a game with his id
When you want to get only one game with his id:
- need to be auth
### header you have to inform :
```http title="header"
  Authorization: Bearer eyJhbGciOiJSUzI1NiJ9.eyJkYXRhIjp7InVzZXJJZCI6MiwidXNlciI6eyJlbWFpbCI6ImNoYXByaXN0aUBnbWFpbC5jb20ifX0sImlhdCI6MTY2NjUyMTM0MCwiZXhwIjoxNjY2NTI0OTQwfQ.mG_goMcHAH3sCqzYiTKdocmbk_JZE8yEzJngrzcqTFRHDIXY9gGvJgrilFtZWjzFa6HW3R0jzjSaD3P1YJ2v0HqhfaH0F1PQnT9ymfauVPt6ahzRiF-6psLD3FLQg3bB8CkGVGnNX5QvL3Fg_lu5NswRraSqJM5ZjfUu9_6dF5tNbxH9MZZ7RQocDePpRl0XhesGXxxOHPYf8K3Tt5lPEkevJ9nytTpmHX0pYcto9Z3pA_sUr9rCH6PBx05f5L91LffRK1MXNNDGzOiFiaPUaWSXk_uPhniwtvoD6dtlvBjHSZqP_0CyyahmKac1KAIfB_L6mAUsCXKeA2IRnA5QPl4znGQI5BvZseDXfVjTWojNJP3dfLs-aFL3rvruldUfjFWIUF9h9led0EZdBK83bsFk7s9nF-cYpMvAHMYlkq1Wyep7UxYeCXh6Hl6iYg6SW_6WfLjzFw46sXY9vtJQElLc-8RduPeLi-XW2jDZfG-gkH1RTvR-dB5D2nZ2J0w94fewkV_FtM7nrraQVUga2UvmYl2HNZF9I2_2q4D1sAt_USjO3VzYkNjs4AWQfrotWGTNP08CBAQYuI7Bqt7TjATBqJU1iaewT4OG46uNkFyd1aO-ygVtyOlBVjKu5tFJ8QZmUaZQzypFTt0bJZ7VhCZakjSj0EL5a-nNDS6QMBo
```
### req.response() :

```json title="an exemple of what the server return"
{
	"post": {
		"id": 1,
		"longitude": "1.24759",
		"latitude": "45.83362",
		"created_at": "2022-10-22T11:32:36.000+02:00",
		"updated_at": "2022-10-22T11:32:36.000+02:00",
		"categorie_id": 1
	}
} 
```
---
## Show all the games 

When you want to show all games or with categorie filter :
- need to be auth 
- pagination :
  - limit of 10
  - start with first page
### header you have to inform :
```http title="header"
  Authorization: Bearer eyJhbGciOiJSUzI1NiJ9.eyJkYXRhIjp7InVzZXJJZCI6MiwidXNlciI6eyJlbWFpbCI6ImNoYXByaXN0aUBnbWFpbC5jb20ifX0sImlhdCI6MTY2NjUyMTM0MCwiZXhwIjoxNjY2NTI0OTQwfQ.mG_goMcHAH3sCqzYiTKdocmbk_JZE8yEzJngrzcqTFRHDIXY9gGvJgrilFtZWjzFa6HW3R0jzjSaD3P1YJ2v0HqhfaH0F1PQnT9ymfauVPt6ahzRiF-6psLD3FLQg3bB8CkGVGnNX5QvL3Fg_lu5NswRraSqJM5ZjfUu9_6dF5tNbxH9MZZ7RQocDePpRl0XhesGXxxOHPYf8K3Tt5lPEkevJ9nytTpmHX0pYcto9Z3pA_sUr9rCH6PBx05f5L91LffRK1MXNNDGzOiFiaPUaWSXk_uPhniwtvoD6dtlvBjHSZqP_0CyyahmKac1KAIfB_L6mAUsCXKeA2IRnA5QPl4znGQI5BvZseDXfVjTWojNJP3dfLs-aFL3rvruldUfjFWIUF9h9led0EZdBK83bsFk7s9nF-cYpMvAHMYlkq1Wyep7UxYeCXh6Hl6iYg6SW_6WfLjzFw46sXY9vtJQElLc-8RduPeLi-XW2jDZfG-gkH1RTvR-dB5D2nZ2J0w94fewkV_FtM7nrraQVUga2UvmYl2HNZF9I2_2q4D1sAt_USjO3VzYkNjs4AWQfrotWGTNP08CBAQYuI7Bqt7TjATBqJU1iaewT4OG46uNkFyd1aO-ygVtyOlBVjKu5tFJ8QZmUaZQzypFTt0bJZ7VhCZakjSj0EL5a-nNDS6QMBo
```


### req.response() :

```json title="an exemple of what the server return without filter"
{
	"meta": {
		"total": 1,
		"per_page": 10,
		"current_page": 1,
		"last_page": 1,
		"first_page": 1,
		"first_page_url": "/?page=1",
		"last_page_url": "/?page=1",
		"next_page_url": null,
		"previous_page_url": null
	},
	"data": [
		{
			"id": 1,
			"longitude": "1.24759",
			"latitude": "45.83362",
			"created_at": "2022-10-22T11:32:36.000+02:00",
			"updated_at": "2022-10-22T11:32:36.000+02:00",
			"categorie_id": 1,
			"categorie": {
				"id": 1,
				"name": "France"
			}
		}
	]
}
```

```json title="an exemple of what the server return with filter"
{
	"meta": {
		"total": 1,
		"per_page": 10,
		"current_page": 1,
		"last_page": 1,
		"first_page": 1,
		"first_page_url": "/?page=1",
		"last_page_url": "/?page=1",
		"next_page_url": null,
		"previous_page_url": null
	},
	"data": [
		{
			"id": 1,
			"longitude": "1.24759",
			"latitude": "45.83362",
			"created_at": "2022-10-22T11:32:36.000+02:00",
			"updated_at": "2022-10-22T11:32:36.000+02:00",
			"categorie_id": 1,
			"categorie": {
				"id": 1,
				"name": "France"
			}
		}
	]
}
```


