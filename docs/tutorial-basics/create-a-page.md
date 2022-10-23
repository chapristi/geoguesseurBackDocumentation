---
sidebar_position: 1
---

# User actions

The **Routes** files that exist are : 

- POST → `http://127.0.0.1:3333/api/user/register`
- POST → `http://127.0.0.1:3333/api/user/login`
- GET  → `http://127.0.0.1:3333/api/user`

## Create an user

When you create an user you have to know the username et email are unique 
### req.send() : 
```json title="an exemple of request"
 { 
	"password" : "dsdfg", 
	"username" : "Louis", 
	"email" : "chapristi@gmail.com"
} 
```
### req.response() :

```json title="an exemple of what the server return"

{ 
	"role": "ROLE_USER", 
	"email": "chapristi@gmail.com", 
	"username": "Louis", 
	"created_at": "2022-10-23T12:32:55.659+02:00", 
	"updated_at": "2022-10-23T12:32:55.659+02:00", 
	"id": 2 
} 

```
---

## Login to an account

When you want to connect to an account
### req.send() :
```json title="an exemple of request"
 { 
	"password" : "dsdfg", 
	"username" : "Louis" 
} 
```
### req.response() :

```json title="an exemple of what the server return"
{ 
    "token": { 
		"type": "bearer", 
		"token": "eyJhbGciOiJSUzI1NiJ9.eyJkYXRhIjp7InVzZXJJZCI6MiwidXNlciI6eyJlbWFpbCI6ImNoYXByaXN0aUBnbWFpbC5jb20ifX0sImlhdCI6MTY2NjUyMTM0MCwiZXhwIjoxNjY2NTI0OTQwfQ.mG_goMcHAH3sCqzYiTKdocmbk_JZE8yEzJngrzcqTFRHDIXY9gGvJgrilFtZWjzFa6HW3R0jzjSaD3P1YJ2v0HqhfaH0F1PQnT9ymfauVPt6ahzRiF-6psLD3FLQg3bB8CkGVGnNX5QvL3Fg_lu5NswRraSqJM5ZjfUu9_6dF5tNbxH9MZZ7RQocDePpRl0XhesGXxxOHPYf8K3Tt5lPEkevJ9nytTpmHX0pYcto9Z3pA_sUr9rCH6PBx05f5L91LffRK1MXNNDGzOiFiaPUaWSXk_uPhniwtvoD6dtlvBjHSZqP_0CyyahmKac1KAIfB_L6mAUsCXKeA2IRnA5QPl4znGQI5BvZseDXfVjTWojNJP3dfLs-aFL3rvruldUfjFWIUF9h9led0EZdBK83bsFk7s9nF-cYpMvAHMYlkq1Wyep7UxYeCXh6Hl6iYg6SW_6WfLjzFw46sXY9vtJQElLc-8RduPeLi-XW2jDZfG-gkH1RTvR-dB5D2nZ2J0w94fewkV_FtM7nrraQVUga2UvmYl2HNZF9I2_2q4D1sAt_USjO3VzYkNjs4AWQfrotWGTNP08CBAQYuI7Bqt7TjATBqJU1iaewT4OG46uNkFyd1aO-ygVtyOlBVjKu5tFJ8QZmUaZQzypFTt0bJZ7VhCZakjSj0EL5a-nNDS6QMBo", 
		"refreshToken": "4a3819e84ade62caa705871b52bf683e78027792a3f38c6b55bc1f4dab50aade", 
		"expires_at": "2022-10-23T13:35:40.455+02:00" 
	} 
} 

```

## Get current User datas

When you want to get current user informations
### header you have to inform :
```http title="header"
  Authorization: Bearer eyJhbGciOiJSUzI1NiJ9.eyJkYXRhIjp7InVzZXJJZCI6MiwidXNlciI6eyJlbWFpbCI6ImNoYXByaXN0aUBnbWFpbC5jb20ifX0sImlhdCI6MTY2NjUyMTM0MCwiZXhwIjoxNjY2NTI0OTQwfQ.mG_goMcHAH3sCqzYiTKdocmbk_JZE8yEzJngrzcqTFRHDIXY9gGvJgrilFtZWjzFa6HW3R0jzjSaD3P1YJ2v0HqhfaH0F1PQnT9ymfauVPt6ahzRiF-6psLD3FLQg3bB8CkGVGnNX5QvL3Fg_lu5NswRraSqJM5ZjfUu9_6dF5tNbxH9MZZ7RQocDePpRl0XhesGXxxOHPYf8K3Tt5lPEkevJ9nytTpmHX0pYcto9Z3pA_sUr9rCH6PBx05f5L91LffRK1MXNNDGzOiFiaPUaWSXk_uPhniwtvoD6dtlvBjHSZqP_0CyyahmKac1KAIfB_L6mAUsCXKeA2IRnA5QPl4znGQI5BvZseDXfVjTWojNJP3dfLs-aFL3rvruldUfjFWIUF9h9led0EZdBK83bsFk7s9nF-cYpMvAHMYlkq1Wyep7UxYeCXh6Hl6iYg6SW_6WfLjzFw46sXY9vtJQElLc-8RduPeLi-XW2jDZfG-gkH1RTvR-dB5D2nZ2J0w94fewkV_FtM7nrraQVUga2UvmYl2HNZF9I2_2q4D1sAt_USjO3VzYkNjs4AWQfrotWGTNP08CBAQYuI7Bqt7TjATBqJU1iaewT4OG46uNkFyd1aO-ygVtyOlBVjKu5tFJ8QZmUaZQzypFTt0bJZ7VhCZakjSj0EL5a-nNDS6QMBo
```
### req.response() :

```json title="an exemple of what the server return"
{ 
   "role": "ROLE_USER", 
   "id": 2, 
   "username": "Louis", 
   "email": "chapristi@gmail.com", 
   "created_at": "2022-10-23T12:32:55.000+02:00", 
   "updated_at": "2022-10-23T12:32:55.000+02:00" 
} 

```
