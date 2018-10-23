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
{
  "pants_sizes": [{
    "id": 1,
    "title": "179/39"
  }, {
    "id": 2,
    "title": "180/42"
  }, {
    "id": 3,
    "title": "182/44"
  }, {
    "id": 4,
    "title": "184/46"
  }],
  "occupations": [{
    "id": 1,
    "title": "Менеджер"
  }, {
    "id": 2,
    "title": "Дизайнер"
  }, {
    "id": 3,
    "title": "Художник"
  }, {
    "id": 4,
    "title": "Бизнесмен"
  }],
  "price_categories": [{
    "id": 1,
    "title": "Эконом",
    "maxprice": 8000
  }, {
    "id": 2,
    "title": "Бизнес",
    "maxprice": 16000
  }, {
    "id": 3,
    "title": "Люкс",
    "maxprice": 32000
  }],
  "colors": [{
    "id": 1,
    "title": "Зеленый",
    "hexcode": "#008000"
  }, {
    "id": 2,
    "title": "Синий",
    "hexcode": "#0000FF"
  }, {
    "id": 3,
    "title": "Оранжевый",
    "hexcode": "#FF5700"
  }, {
    "id": 4,
    "title": "Жёлтый",
    "hexcode": "#ffb90f"
  }],
  "events": [{
    "id": 1,
    "title": "На вечеринку",
    "outfits": [{
      "id": 1,
      "event_id": 1,
      "picture_url": "/uploads/outfit_variant/picture/1/266f020728b7441f8cb841e9798b0afe.png"
    }, {
      "id": 2,
      "event_id": 1,
      "picture_url": "/uploads/outfit_variant/picture/2/266f020728b7441f8cb841e9798b0afe.png"
    }, {
      "id": 3,
      "event_id": 1,
      "picture_url": "/uploads/outfit_variant/picture/3/266f020728b7441f8cb841e9798b0afe.png"
    }, {
      "id": 4,
      "event_id": 1,
      "picture_url": "/uploads/outfit_variant/picture/4/266f020728b7441f8cb841e9798b0afe.png"
    }, {
      "id": 5,
      "event_id": 1,
      "picture_url": "/uploads/outfit_variant/picture/5/266f020728b7441f8cb841e9798b0afe.png"
    }]
  }, {
    "id": 2,
    "title": "Деловая встреча",
    "outfits": [{
      "id": 6,
      "event_id": 2,
      "picture_url": "/uploads/outfit_variant/picture/6/266f020728b7441f8cb841e9798b0afe.png"
    }, {
      "id": 7,
      "event_id": 2,
      "picture_url": "/uploads/outfit_variant/picture/7/266f020728b7441f8cb841e9798b0afe.png"
    }]
  }]
}
```

Позволяет получить все справочные данные, необходимые для работы программы.

### HTTP Request

`GET http://example.com/api/v1/informations`

### Части ответа

Parameter |  Описание
--------- | ------- 
pants_sizes | [Справочник  размеров штанов](#pants_sizes)
occupations | [Справочник занятий пользоватея](#occupations)
price_categories | [Справочник ценовых категорий](#price_categories)
colors | [Справочник цветов](#colors)
events | [Справочник мероприятий](#events) 

<aside class="notice">
Раздел размеров будет переработан, т.к. появились всякие RU, US, EU, INTL, Талия, рост. + размер верха
</aside>


## Описание частей ответа

### <a name="pants_sizes"></a> Справочник размеров штанов

> Справочник размеров штанов

```json
{
    "id": 1,
    "title": "179/39"
  }
```

Каждый элемент имеет следующую структуру

Ключ | Описание
-----|---------
id   | ID размера
title| Текстовое описание

### <a name="occupations"></a> Справочник занятий пользоватея

> Справочник занятий

```json
{
    "id": 1,
    "title": "Менеджер"
  }
```

Каждый элемент имеет следующую структуру

Ключ | Описание
-----|---------
id   | ID размера
title| Текстовое описание

### <a name="price_categories"></a> Справочник ценовых категорий

> Справочник ценовых категорий

```json
{
    "id": 1,
    "title": "Эконом",
    "maxprice": 8000
  }
```

Каждый элемент имеет следующую структуру

Ключ | Описание
-----|---------
id   | ID размера
title| Текстовое описание
maxprice | Максимальная цена категории


### <a name="colors"></a> Справочник цветов

> Справочник цветов

```json
{
    "id": 1,
    "title": "Зеленый",
    "hexcode": "#008000"
  }
```

Каждый элемент имеет следующую структуру

Ключ | Описание
-----|---------
id   | ID размера
title| Название цвета
hexcode | Код цвета в формате #hex

### <a name="events"></a> Справочник мероприятий 

> Справочник мероприятий 

```json
{
    "id": 1,
    "title": "На вечеринку",
    "outfits": [{
      "id": 1,
      "event_id": 1,
      "picture_url": "/uploads/outfit_variant/picture/1/266f020728b7441f8cb841e9798b0afe.png"
    }, {
      "id": 2,
      "event_id": 1,
      "picture_url": "/uploads/outfit_variant/picture/2/266f020728b7441f8cb841e9798b0afe.png"
    }, {
      "id": 3,
      "event_id": 1,
      "picture_url": "/uploads/outfit_variant/picture/3/266f020728b7441f8cb841e9798b0afe.png"
    }, {
      "id": 4,
      "event_id": 1,
      "picture_url": "/uploads/outfit_variant/picture/4/266f020728b7441f8cb841e9798b0afe.png"
    }, {
      "id": 5,
      "event_id": 1,
      "picture_url": "/uploads/outfit_variant/picture/5/266f020728b7441f8cb841e9798b0afe.png"
    }]
  }
```

Каждый элемент имеет следующую структуру

Ключ | Описание
-----|---------
id   | ID размера
title| Название цвета
outfits | Массив вариантов образов для данного типа мероприятий

в разделе `outfits` каждый вариант образа обладает следующими параметрами

Ключ | Описание
-----|---------
id   | ID образа
event_id| к какому мероприятию относится данный образ (в принципе не нужно, т.к. информация уже сгруппирована, но оставил на всякий случай)
picture_url | Фотография образа, которая будет показываться пользователю




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

