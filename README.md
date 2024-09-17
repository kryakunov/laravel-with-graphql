
# Laravel with Graphql

Реализация простых CRUD операций с использованием graphql и пакета Lighthouse

## Как пользоваться?

Разворачиваем проект:


1. docker-compose up -d
2. composer i
2. php artisan migrate
3. php artisan db:seed

Далее можно использовать Postman и отправлять запросы на http://localhost:8080/graphql

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

