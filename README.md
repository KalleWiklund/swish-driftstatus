# Swish driftstörningar

Statisk sajt som visar driftstörningar för Swish, hämtade live från det publika API:t på `status.swish.nu` (Atlassian Statuspage).

## Funktioner

- Incidenter de senaste 10 dagarna, eller de 50 senaste
- Sortera på allvarlighetsgrad eller drabbad bank
- Filtrera på bank
- Banner för pågående störningar

## Köra lokalt

Öppna inte `index.html` direkt via `file://` – webbläsaren blockerar då anropet till API:t. Starta en enkel server i mappen:

```bash
python3 -m http.server 8777
```

Gå sedan till <http://127.0.0.1:8777>.

## Datakälla

`https://status.swish.nu/api/v2/incidents.json` – returnerar de 50 senaste incidenterna med fälten `name`, `impact`, `status`, tidsstämplar, `incident_updates` och `components`.
