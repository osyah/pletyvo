# Reference

## Query Option

Sorting by options is available only in endpoints that return any array of objects.

| Option   | Type                  |
| -------- | --------------------- |
| `after`  | uuid                  |
| `before` | uuid                  |
| `limit`  | int (default: 20)     |
| `order`  | asc \| desc (default) |

**Example**

* `{url}/api/dapp/v1/events?after={event.id}&order=asc`
* `{url}/api/dapp/v1/events?limit=10`

## SDK

| Name                                                                 | Language |
| -------------------------------------------------------------------- | -------- |
| [`osyah/go-pletyvo`](https://github.com/osyah/go-pletyvo) (official) | Go       |

