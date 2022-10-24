---
sidebar_position: 3
---

# Room actions

The **Routes** that exist are :

- GET → `http://127.0.0.1:3333/api/room/all`
- GET → `http://127.0.0.1:3333/api/room/show/:token`
- POST  → `http://127.0.0.1:3333/api/room/create`
- ** PUT  → `http://127.0.0.1:3333/api/room/update/:token`**
- DELETE  → `http://127.0.0.1:3333/api/room/delete/:token`

## get all rooms public and not started and not finished

When you want get all rooms : 
- need to be auth
### header you have to inform :
```http title="header"
  Authorization: Bearer eyJhbGciOiJSUzI1NiJ9.eyJkYXRhIjp7InVzZXJJZCI6MiwidXNlciI6eyJlbWFpbCI6ImNoYXByaXN0aUBnbWFpbC5jb20ifX0sImlhdCI6MTY2NjUyMTM0MCwiZXhwIjoxNjY2NTI0OTQwfQ.mG_goMcHAH3sCqzYiTKdocmbk_JZE8yEzJngrzcqTFRHDIXY9gGvJgrilFtZWjzFa6HW3R0jzjSaD3P1YJ2v0HqhfaH0F1PQnT9ymfauVPt6ahzRiF-6psLD3FLQg3bB8CkGVGnNX5QvL3Fg_lu5NswRraSqJM5ZjfUu9_6dF5tNbxH9MZZ7RQocDePpRl0XhesGXxxOHPYf8K3Tt5lPEkevJ9nytTpmHX0pYcto9Z3pA_sUr9rCH6PBx05f5L91LffRK1MXNNDGzOiFiaPUaWSXk_uPhniwtvoD6dtlvBjHSZqP_0CyyahmKac1KAIfB_L6mAUsCXKeA2IRnA5QPl4znGQI5BvZseDXfVjTWojNJP3dfLs-aFL3rvruldUfjFWIUF9h9led0EZdBK83bsFk7s9nF-cYpMvAHMYlkq1Wyep7UxYeCXh6Hl6iYg6SW_6WfLjzFw46sXY9vtJQElLc-8RduPeLi-XW2jDZfG-gkH1RTvR-dB5D2nZ2J0w94fewkV_FtM7nrraQVUga2UvmYl2HNZF9I2_2q4D1sAt_USjO3VzYkNjs4AWQfrotWGTNP08CBAQYuI7Bqt7TjATBqJU1iaewT4OG46uNkFyd1aO-ygVtyOlBVjKu5tFJ8QZmUaZQzypFTt0bJZ7VhCZakjSj0EL5a-nNDS6QMBo
```

### req.response() :

```json title="an exemple of what the server return"
{
	"room": [
		{
			"is_closed": 0,
			"is_started": 0,
			"id": 1,
			"game_id": 1,
			"token": "ZDFGF78-DFHFGJ5-FHF784",
			"created_at": "2022-10-23T17:22:07.000+02:00",
			"updated_at": "2022-10-23T17:22:07.000+02:00"
		}
	]
}
```
---

## Get a room with his token

When you want get a room in particulary:
- you must be connected
### header you have to inform :
```http title="header"
  Authorization: Bearer eyJhbGciOiJSUzI1NiJ9.eyJkYXRhIjp7InVzZXJJZCI6MiwidXNlciI6eyJlbWFpbCI6ImNoYXByaXN0aUBnbWFpbC5jb20ifX0sImlhdCI6MTY2NjUyMTM0MCwiZXhwIjoxNjY2NTI0OTQwfQ.mG_goMcHAH3sCqzYiTKdocmbk_JZE8yEzJngrzcqTFRHDIXY9gGvJgrilFtZWjzFa6HW3R0jzjSaD3P1YJ2v0HqhfaH0F1PQnT9ymfauVPt6ahzRiF-6psLD3FLQg3bB8CkGVGnNX5QvL3Fg_lu5NswRraSqJM5ZjfUu9_6dF5tNbxH9MZZ7RQocDePpRl0XhesGXxxOHPYf8K3Tt5lPEkevJ9nytTpmHX0pYcto9Z3pA_sUr9rCH6PBx05f5L91LffRK1MXNNDGzOiFiaPUaWSXk_uPhniwtvoD6dtlvBjHSZqP_0CyyahmKac1KAIfB_L6mAUsCXKeA2IRnA5QPl4znGQI5BvZseDXfVjTWojNJP3dfLs-aFL3rvruldUfjFWIUF9h9led0EZdBK83bsFk7s9nF-cYpMvAHMYlkq1Wyep7UxYeCXh6Hl6iYg6SW_6WfLjzFw46sXY9vtJQElLc-8RduPeLi-XW2jDZfG-gkH1RTvR-dB5D2nZ2J0w94fewkV_FtM7nrraQVUga2UvmYl2HNZF9I2_2q4D1sAt_USjO3VzYkNjs4AWQfrotWGTNP08CBAQYuI7Bqt7TjATBqJU1iaewT4OG46uNkFyd1aO-ygVtyOlBVjKu5tFJ8QZmUaZQzypFTt0bJZ7VhCZakjSj0EL5a-nNDS6QMBo
```
### req.response() :

```json title="an exemple of what the server return"
{
	"room": [
		{
			"is_closed": 0,
			"is_started": 0,
			"id": 1,
			"game_id": 1,
			"token": "ZDFGF78-DFHFGJ5-FHF784",
			"created_at": "2022-10-23T17:22:07.000+02:00",
			"updated_at": "2022-10-23T17:22:07.000+02:00"
		}
	]
}

```
---

## Create new Room

When you want to create new room you have to know the user who is creating the room become admin of this room:
- need to be auth
### header you have to inform :
```http title="header"
  Authorization: Bearer eyJhbGciOiJSUzI1NiJ9.eyJkYXRhIjp7InVzZXJJZCI6MiwidXNlciI6eyJlbWFpbCI6ImNoYXByaXN0aUBnbWFpbC5jb20ifX0sImlhdCI6MTY2NjUyMTM0MCwiZXhwIjoxNjY2NTI0OTQwfQ.mG_goMcHAH3sCqzYiTKdocmbk_JZE8yEzJngrzcqTFRHDIXY9gGvJgrilFtZWjzFa6HW3R0jzjSaD3P1YJ2v0HqhfaH0F1PQnT9ymfauVPt6ahzRiF-6psLD3FLQg3bB8CkGVGnNX5QvL3Fg_lu5NswRraSqJM5ZjfUu9_6dF5tNbxH9MZZ7RQocDePpRl0XhesGXxxOHPYf8K3Tt5lPEkevJ9nytTpmHX0pYcto9Z3pA_sUr9rCH6PBx05f5L91LffRK1MXNNDGzOiFiaPUaWSXk_uPhniwtvoD6dtlvBjHSZqP_0CyyahmKac1KAIfB_L6mAUsCXKeA2IRnA5QPl4znGQI5BvZseDXfVjTWojNJP3dfLs-aFL3rvruldUfjFWIUF9h9led0EZdBK83bsFk7s9nF-cYpMvAHMYlkq1Wyep7UxYeCXh6Hl6iYg6SW_6WfLjzFw46sXY9vtJQElLc-8RduPeLi-XW2jDZfG-gkH1RTvR-dB5D2nZ2J0w94fewkV_FtM7nrraQVUga2UvmYl2HNZF9I2_2q4D1sAt_USjO3VzYkNjs4AWQfrotWGTNP08CBAQYuI7Bqt7TjATBqJU1iaewT4OG46uNkFyd1aO-ygVtyOlBVjKu5tFJ8QZmUaZQzypFTt0bJZ7VhCZakjSj0EL5a-nNDS6QMBo
```
### req.send() :

```json title="an exemple of what the server return"
{ 
    "gameId" : 1,
	"isOnline" : true
} 
```
### req.response() :

```json title="an exemple of what the server return"
{
	"room": {
		"is_closed": false,
		"is_started": false,
		"game_id": 1,
		"token": "88c0a5d1-7b3a-431c-a21f-8818cc538524",
		"is_online": true,
		"created_at": "2022-10-24T22:08:48.082+02:00",
		"updated_at": "2022-10-24T22:08:48.082+02:00",
		"id": 3
	},
	"player": {
		"room_id": 3,
		"user_id": 2,
		"role": "ROLE_ADMIN",
		"created_at": "2022-10-24T22:08:48.092+02:00",
		"id": 2
	}
}

```

---

## Update current User datas

When you want to update current user informations:
- need to be auth
### header you have to inform :
```http title="header"
  Authorization: Bearer eyJhbGciOiJSUzI1NiJ9.eyJkYXRhIjp7InVzZXJJZCI6MiwidXNlciI6eyJlbWFpbCI6ImNoYXByaXN0aUBnbWFpbC5jb20ifX0sImlhdCI6MTY2NjUyMTM0MCwiZXhwIjoxNjY2NTI0OTQwfQ.mG_goMcHAH3sCqzYiTKdocmbk_JZE8yEzJngrzcqTFRHDIXY9gGvJgrilFtZWjzFa6HW3R0jzjSaD3P1YJ2v0HqhfaH0F1PQnT9ymfauVPt6ahzRiF-6psLD3FLQg3bB8CkGVGnNX5QvL3Fg_lu5NswRraSqJM5ZjfUu9_6dF5tNbxH9MZZ7RQocDePpRl0XhesGXxxOHPYf8K3Tt5lPEkevJ9nytTpmHX0pYcto9Z3pA_sUr9rCH6PBx05f5L91LffRK1MXNNDGzOiFiaPUaWSXk_uPhniwtvoD6dtlvBjHSZqP_0CyyahmKac1KAIfB_L6mAUsCXKeA2IRnA5QPl4znGQI5BvZseDXfVjTWojNJP3dfLs-aFL3rvruldUfjFWIUF9h9led0EZdBK83bsFk7s9nF-cYpMvAHMYlkq1Wyep7UxYeCXh6Hl6iYg6SW_6WfLjzFw46sXY9vtJQElLc-8RduPeLi-XW2jDZfG-gkH1RTvR-dB5D2nZ2J0w94fewkV_FtM7nrraQVUga2UvmYl2HNZF9I2_2q4D1sAt_USjO3VzYkNjs4AWQfrotWGTNP08CBAQYuI7Bqt7TjATBqJU1iaewT4OG46uNkFyd1aO-ygVtyOlBVjKu5tFJ8QZmUaZQzypFTt0bJZ7VhCZakjSj0EL5a-nNDS6QMBo
```
### req.send() :

```json title="an exemple of what the server return"
{ 
	"username" : "Louis12"
	"email" : ???
	"password" : ???
} 

```
### req.response() :

```json title="an exemple of what the server return"
{ 
	"role": "ROLE_USER", 
	"id": 2, 
	"username": "Louis12", 
	"email": "chapristi@gmail.com", 
	"created_at": "2022-10-23T12:32:55.000+02:00", 
	"updated_at": "2022-10-23T15:22:01.497+02:00" 
} 

```
---

## Refresh token

When you want to refresh the token when the current token is invalid

### req.send() :

```json title="an exemple of what the server return"
{ 
    "refresh_token" : "4a3819e84ade62caa705871b52bf683e78027792a3f38c6b55bc1f4dab50aade" 
}  

```
### req.response() :

```json title="an exemple of what the server return"
{ 
	"jwt": { 
		"type": "bearer", 
		"token": "eyJhbGciOiJSUzI1NiJ9.eyJkYXRhIjp7InVzZXJJZCI6MiwidXNlciI6eyJlbWFpbCI6ImNoYXByaXN0aUBnbWFpbC5jb20ifX0sImlhdCI6MTY2NjUzMTQzOSwiZXhwIjoxNjY2NTM1MDM5fQ.PHCZvtRJHbNR5MSyP7qYpq-R2V25JpA1hEx_CUagyozfffPtDbG5QSdjf9VyyjZCKDJDM5so972TZKP6T-nXBpkW6X3dMIunHyO253QDuSVxmSqypwMNSw21iOVZcLD72LHli6m4P6ugG1TP3Yw2TLd1JLvqeki9oDkZ2q-aZO6enp3CFlGefYQTet37KklIRjZoXg-IO6I7ka2rjWNm-49YPbsDbkeKDAzK5MC3GguLmKUqdZwJBu1Isu7uBwhqEhXtInD3Ivm7S1K2cBvmEKPl_5twNhCGf6AIT8CLVK2C6d43jWmzcXa-BrreKaaVSLYQBa0MMU0yAlgsmWZa94xnlcR84kjxLroAZcZGwCTYcA2vF-5ZkLnA0qHgUu0v6Z_EtIsuUqOh9vtFpBEDBnjnm2CnYchVjJJX1OIrM8lV7hhKq1CHDdTGYnYaBTtW1TlXqTmaxRyyPAbKdY4tqR5A90fx1hEVbCAU3NciD3K--CdFZsVoSrrbIK3RMm2gXrA1lYpgS8kgFtqyxRof5vBEGefErgyUsO0OghQ5LOj8l1JgobdfSWz5UF6UFWmQJmJDcJYgRpgBT45_90qb4ZKLEOj8woj_OEDOc05gI8ZgnhP-Dj5CQE7fxfaFj-e85DrxHDRocNhmspwg_q3b3r9SmmxB-wZ9Jx_sKFwrW6A", 
		"refreshToken": "4273c2ebf6a647c0a80f4650e28ad9b08998113dae40d4ed4ec8b957e1221f9e", 
		"expires_at": "2022-10-23T16:23:59.710+02:00" 
	} 
} 
```
---

## Logout

When you want to destroy refresh token and token to logout the current user:
- need to be auth
### header you have to inform :
```http title="header"
  Authorization: Bearer eyJhbGciOiJSUzI1NiJ9.eyJkYXRhIjp7InVzZXJJZCI6MiwidXNlciI6eyJlbWFpbCI6ImNoYXByaXN0aUBnbWFpbC5jb20ifX0sImlhdCI6MTY2NjUyMTM0MCwiZXhwIjoxNjY2NTI0OTQwfQ.mG_goMcHAH3sCqzYiTKdocmbk_JZE8yEzJngrzcqTFRHDIXY9gGvJgrilFtZWjzFa6HW3R0jzjSaD3P1YJ2v0HqhfaH0F1PQnT9ymfauVPt6ahzRiF-6psLD3FLQg3bB8CkGVGnNX5QvL3Fg_lu5NswRraSqJM5ZjfUu9_6dF5tNbxH9MZZ7RQocDePpRl0XhesGXxxOHPYf8K3Tt5lPEkevJ9nytTpmHX0pYcto9Z3pA_sUr9rCH6PBx05f5L91LffRK1MXNNDGzOiFiaPUaWSXk_uPhniwtvoD6dtlvBjHSZqP_0CyyahmKac1KAIfB_L6mAUsCXKeA2IRnA5QPl4znGQI5BvZseDXfVjTWojNJP3dfLs-aFL3rvruldUfjFWIUF9h9led0EZdBK83bsFk7s9nF-cYpMvAHMYlkq1Wyep7UxYeCXh6Hl6iYg6SW_6WfLjzFw46sXY9vtJQElLc-8RduPeLi-XW2jDZfG-gkH1RTvR-dB5D2nZ2J0w94fewkV_FtM7nrraQVUga2UvmYl2HNZF9I2_2q4D1sAt_USjO3VzYkNjs4AWQfrotWGTNP08CBAQYuI7Bqt7TjATBqJU1iaewT4OG46uNkFyd1aO-ygVtyOlBVjKu5tFJ8QZmUaZQzypFTt0bJZ7VhCZakjSj0EL5a-nNDS6QMBo
```

### req.response() :

```json title="an exemple of what the server return"
{
     "revoked" : true
} 
```
