## Задание 5. Проектирование GraphQL API

### API

[Эквивалентная схема GraphQL](new_api.graphql)

### Примеры

```
Пример 1: Получение информации о клиенте (аналог REST GET /clients/{id})

query GetClient {
  client(id: "12345") {
    id
    name
    age
  }
}

Пример 2: Получение документов клиента (аналог REST GET /clients/{id}/documents)

query GetClientDocuments {
  clientDocuments(id: "12345") {
    id
    type
    number
    issueDate
    expiryDate
  }
}

Пример 3: Получение родственников клиента (аналог REST GET /clients/{id}/relatives)

query GetClientRelatives {
  clientRelatives(id: "12345") {
    id
    name
    relationType
    age
  }
}

Пример 4: Комбинированный запрос (получение всей информации за один раз)

query GetFullClientProfile {
  client(id: "12345") {
    id
    name
    age
    documents {
      type
      number
      expiryDate
    }
    relatives {
      name
      relationType
      age
    }
  }
}

Пример 5: Частичный выбор полей

query GetRelativesNames {
  client(id: "12345") {
    relatives {
      name
      relationType
    }
  }
}

```

