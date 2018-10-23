---
title: EasyBuy API reference v1

language_tabs: # must be one of https://git.io/vQNgJ
  - http: HTTP

includes:
  - errors

search: false
---

# Введение

Описание API для проекта EasyBuy


# Аутентификация

> в процессе обсуждения:

```http
GET / HTTP/1.1
Accept: application/json
```


# Справочники

## Получить справочные данные 

```http
GET /api/v1/informations HTTP/1.1

```

> Ответ сервера:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Позволяет получить все справочные данные, необходимые для работы программы.

### HTTP Request

`GET http://example.com/api/v1/informations`

### Части ответа

Parameter |  Описание
--------- | ------- 
pants_sizes | Справочник  размеров штанов.
occupations | Справочник занятий пользоватея
price_categories | Справочник ценовых категорий
colors | Справочник цветов
events | Справочник возможных событий 

### Справочник  размеров штанов

```json
{
    "id": 7,
    "title": "179/39"
}
```

Каждый элемент имеет следующую структуру

Ключ | Описание
-----|---------
id   | ID размера
title| Текстовое описание



## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

