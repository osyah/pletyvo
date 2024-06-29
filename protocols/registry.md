# Registry

## Network

### Network Structure

| Field    | Type                       |
| -------- | -------------------------- |
| `id`     | uuid                       |
| `author` | [Address](dapp.md#address) |
| `name`   | string                     |

### Get Network

<mark style="color:blue;">`GET`</mark> `/registry/v1/network`

**Response**

```json
{
  "id": "00000000-0000-0000-0000-000000000000",
  "author": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "name": "Криївка"
}
```

### Create Network

<mark style="color:red;">`TYPE`</mark> `[0, 1, 0, 1]`

**Input**

| Field  | Type   |
| ------ | ------ |
| `name` | string |

### Update Network

<mark style="color:red;">`TYPE`</mark> `[1, 1, 0, 1]`

**Input**

| Field  | Type   |
| ------ | ------ |
| `name` | string |
