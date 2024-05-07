# dApp

## Address

The address consists of a 32-byte BLAKE3-256 hash used as the identifier of the cryptographic public key, which is usually represented in HEX format with a `0x` prefix.

## Auth Header

### Auth Header Structure

| Field | Type                     |
| ----- | ------------------------ |
| `sch` | [Schema](dapp.md#schema) |
| `pub` | base64 string            |
| `sig` | base64 string            |

### Schema

| Schema | Algorithm |
| ------ | --------- |
| `0x0`  | ED25519   |

## Event

### Event Structure

| Field    | Type                                        |
| -------- | ------------------------------------------- |
| `id`     | uuid                                        |
| `author` | [Address](dapp.md#address)                  |
| `body`   | [EventBody](dapp.md#event-body)             |
| `auth`   | [AuthHeader](dapp.md#auth-header-structure) |

### Event Body

The event body defines a data format that simplifies cryptographic authentication and reduces data reuse. Each body contains a version, which is always located in the first byte and serves as an identifier of the format in which the data was recorded.

#### Event Body JSON

The event body is defined by version `0` and consists of at least 5 bytes of useful information and N number of input data in JSON format.

```
[0: version, 1, 1, 1, 1: event type: 1, ..., 1: json data]
```

### Event Type

The event type consists of 4 bytes, each of which is predefined by the protocol.

```
[0: event, 0: aggregate, 0: version, 0: protocol]
```

### Get Events

<mark style="color:blue;">`GET`</mark> `/dapp/v1/events`

**Response**

```json
[
  {
    "id": "00000000-0000-0000-0000-000000000000",
    "author": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "body": "base64",
    "auth": {
      "sch": 0,
      "pub": "base64",
      "sig": "base64"
    }
  }
]
```

### Get Event

<mark style="color:blue;">`GET`</mark> `/dapp/v1/events/{event.id}`

**Response**

```json
{
  "id": "00000000-0000-0000-0000-000000000000",
  "author": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "body": "base64",
  "auth": {
    "sch": 0,
    "pub": "base64",
    "sig": "base64"
  }
}
```

### Create Event

<mark style="color:green;">`POST`</mark> `/dapp/v1/events`

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

| Name   | Type                                        |
| ------ | ------------------------------------------- |
| `body` | [EventBody](dapp.md#event-body)             |
| `auth` | [AuthHeader](dapp.md#auth-header-structure) |

**Response**

```json
{
  "id": "00000000-0000-0000-0000-000000000000"
}
```
