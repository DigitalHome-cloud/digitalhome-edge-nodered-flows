# digitalhome-flows

Node-RED flows for [digitalhome-edge](https://github.com/DigitalHome-cloud/digitalhome-edge).

## Tabs

| Tab | Endpoints | Description |
|-----|-----------|-------------|
| State | `/api/state/all`, `/api/state/:room`, `/api/heating/status` | Device and room state queries |
| Lights | `/api/lights/:room/{on,off,dim,color-temp}` | Per-room light control via Hue Bridge |
| Scenes | `/api/scene/{morning,evening,night,away,welcome}` | Predefined scene activation |
| Heating | `/api/heating/:room/set`, `/api/heating/{eco,comfort}` | Thermostat control via Homematic CCU |
| Cloud Sync | `/api/cloud/sync` | Push state to digitalhome.cloud |

## Device hostnames

Flows use DNS hostnames (resolved via `/etc/hosts`), never hardcoded IPs:

- `homematic-ccu` — Homematic CCU
- `hue-bridge` — Philips Hue Bridge

## Credentials

`flows_cred.json` is encrypted by Node-RED and gitignored. The encryption key
is stored in the config cache at `nodered.credential_secret`.
