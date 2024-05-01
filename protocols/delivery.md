# Delivery

## Channel

### Channel Structure

| Field   |                                                             |
| ------- | ----------------------------------------------------------- |
| `id`    | uuid                                                        |
| `name`  | string                                                      |
| `owner` | [Address](https://pletyvo.osyah.com/protocols/dapp#address) |

### Get Channel

<mark style="color:blue;">`GET`</mark> `/delivery/v1/channels/{channel.id}`

**Response**

```json
{
  "id": "00000000-0000-0000-0000-000000000000",
  "name": "Захоплення Світу",
  "owner": "0x0000000000000000000000000000000000000000000000000000000000000000"
}
```

### Create Channel

<mark style="color:red;">`TYPE`</mark> `[0, 1, 0, 2]`

**Input**

| Field  | Type   |
| ------ | ------ |
| `name` | string |

### Update Channel

<mark style="color:red;">`TYPE`</mark> `[1, 1, 0, 2]`

**Input**

| Field     | Type   |
| --------- | ------ |
| `channel` | uuid   |
| `name`    | string |

## Message

### Message Structure

| Field     | Type                                                        |
| --------- | ----------------------------------------------------------- |
| `id`      | uuid                                                        |
| `channel` | uuid                                                        |
| `author`  | [Address](https://pletyvo.osyah.com/protocols/dapp#address) |
| `content` | string                                                      |

### Get Messages

<mark style="color:blue;">`GET`</mark> `/delivery/v1/channels/{channel.id}/messages`

**Response**

```json
[
  {
    "id": "00000000-0000-0000-0000-000000000000",
    "channel": "00000000-0000-0000-0000-000000000000",
    "author": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "content": "Монада — це моноїд в категорії якогось там..."
  }
]
```

### Get Message

<mark style="color:blue;">`GET`</mark> `/delivery/v1/channels/{channel.id}/messages/{message.id}`

**Response**

```json
{
  "id": "00000000-0000-0000-0000-000000000000",
  "channel": "00000000-0000-0000-0000-000000000000",
  "author": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "content": "І день іде, і ніч іде. І голову схопивши в руки, Дивуєшся, чому не йде Апостол правди і науки!"
}
```

### Create Message

<mark style="color:red;">`TYPE`</mark> `[0, 2, 0, 2]`

**Input**

| Field     | Type   |
| --------- | ------ |
| `channel` | uuid   |
| `content` | string |

### Update Message

<mark style="color:red;">`TYPE`</mark> `[1, 2, 0, 2]`

**Input**

| Field     | Type   |
| --------- | ------ |
| `channel` | uuid   |
| `message` | uuid   |
| `content` | string |
