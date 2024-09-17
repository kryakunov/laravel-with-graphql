
# Laravel with Graphql

Реализация простых CRUD операций с использованием graphql и пакета Lighthouse

### Разворачиваем проект:

1. docker-compose up -d
2. composer i
3. cp .env.example .env
4. php artisan key:generate
5. php artisan migrate
6. php artisan db:seed


### Как пользоваться? 

Открываем главную страницу или /graphiql и пробуем отправлять запросы

### Получить всех пользователей:
```
{
    users {
        id
        name
        email
    }
}
```

### Получить конкретного пользователя:
```
{
    user(id: 3){
        id
        name
        email
    }
}
```
### Создать пользователя:
```
    mutation {
        createUser(name: "Andrey", password: "asdf",email: "test@test.ru") {
            id, name, email
        }
    }
```
### Обновить пользователя:
```
    mutation {
        updateUser(id: 3, name: "updated", email: "update@mail.ru", password: "newpass") {
            id, name, email
        }
    }
```

### Обновить или создать пользователя:
```
    mutation {
        upsertUser(id: 3, name: "Andrey", email: "est@test.ru", password: "newpass") {
            id, name, email
        }
    }
```

### Удалить пользователя:
```
    mutation {
        deleteUser(id: 15) {
            name
        }
    }
```

