# Api

**URL:** `https://web-app-papatomatoe.herokuapp.com/`

## Ресурсы:

- `/posts` Посты
- `/sections` Разделы

## Роуты:

- **GET** [`/posts`](https://web-app-papatomatoe.herokuapp.com/posts) - Получить все посты
- **GET** [`/posts/1`](https://web-app-papatomatoe.herokuapp.com/posts/1) Получить один пост по id
- **GET** [`/sections`](https://web-app-papatomatoe.herokuapp.com/sections) Получить все разделы
- **POST** `/posts` Сохранить пост

## Структуры данны:

### Пост (Post)

| название поля  | тип      |                                      описание |
| -------------- | :------- | --------------------------------------------: |
| `id`           | `number` |                                      id поста |
| `title`        | `string` |                               заголовок поста |
| `content`      | `string` |                              содержание поста |
| `sectionId`    | `number` |        id раздела к которому принадлежит пост |
| `sectionTitle` | `string` | заголовок раздела к которому принадлежит пост |
| `createDate`   | `string` |                           дата создания поста |

Пример:

```json
{
  "id": 1,
  "title": "Post 1",
  "content": "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.",
  "sectionId": 1,
  "sectionTitle": "Posts",
  "createDate": "2021-12-30T08:06:57.892Z"
},
```

### Все посты

| название поля | тип           |               описание |
| ------------- | :------------ | ---------------------: |
| -             | `Array<Post>` | массив объектов постов |

Пример:

```json
[
	{
		"id": 7,
		"title": "Post 1",
		"content": "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.",
		"sectionId": 1,
		"sectionTitle": "Posts",
		"createDate": "2021-12-30T08:06:57.892Z"
	},
	{
		"id": 8,
		"title": "Post 2",
		"content": "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.",
		"sectionId": 1,
		"sectionTitle": "Posts",
		"createDate": "2021-12-30T09:53:57.821Z"
	},
	{
		"id": 9,
		"title": "Post_3",
		"content": "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.",
		"sectionId": 1,
		"sectionTitle": "Posts",
		"createDate": "2021-12-30T09:55:39.165Z"
	}
]
```

### Раздел (Section)

| название поля | тип      |          описание |
| ------------- | :------- | ----------------: |
| `id`          | `number` |        id раздела |
| `title`       | `string` | заголовок раздела |

Пример:

```json
{
	"id": 1,
	"title": "Posts"
}
```

### Все разделы

| название поля | тип              |                 описание |
| ------------- | :--------------- | -----------------------: |
| -             | `Array<Section>` | массив объектов разделов |

Пример:

```json
[
	{
		"id": 1,
		"title": "Posts"
	},
	{
		"id": 2,
		"title": "Links"
	}
]
```

## Сохранение поста

Для создания поста необходимо отправить в теле запроса объект содержащий обязательные поля `title`, `content`, `sectionId`. В ответ приходит объект поста.

| название поля | тип      |                               описание |
| ------------- | :------- | -------------------------------------: |
| `title`       | `string` |                        заголовок поста |
| `content`     | `string` |                       содержание поста |
| `sectionId`   | `number` | id раздела к которому принадлежит пост |

Пример тела запроса:

```json
{
	"title": "Save test title",
	"content": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).",
	"sectionId": 1
}
```

Пример ответа:

```json
{
	"id": 3,
	"title": "Save test title",
	"content": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).",
	"sectionId": 1,
	"sectionTitle": "Posts",
	"createDate": "2021-12-30T12:46:55.994Z"
}
```
