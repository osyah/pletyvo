# Reference

## Network Identify

Some API gateway addresses can provide access to multiple networks simultaneously. Therefore, in order to correctly server execute an incoming request, clients need to add an HTTP header with the name `Network` and the network ID as a value.

## Query Option

Sorting by options is available only in endpoints that return any array of objects.

| Option   | Type                        |
| -------- | --------------------------- |
| `after`  | uuid                        |
| `before` | uuid                        |
| `limit`  | uint (default: 25; max: 50) |
| `order`  | asc \| desc (default)       |

**Example**

* `{url}/api/dapp/v1/events?after={event.id}&order=asc`
* `{url}/api/dapp/v1/events?limit=10`

## SDK

| Name                                                                 | Language   |
| -------------------------------------------------------------------- | ---------- |
| [`osyah/go-pletyvo`](https://github.com/osyah/go-pletyvo) (official) | Go         |
| [`osyah/js-pletyvo`](https://github.com/osyah/js-pletyvo) (official) | JavaScript |

