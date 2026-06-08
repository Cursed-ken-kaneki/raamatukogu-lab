# Raamatukogu

Raamatukogu rakendus on veebipõhine süsteem raamatute ja nende laenutuste haldamiseks. Kasutajad saavad registreeruda, sisse logida ning laenata ja tagastada raamatuid. Rakendus pakub otsingute tegemist ja raamatute kategoriseerimist žanrite järgi.

## Tehnoloogiad

- **Node.js** — Backenд runtime
- **Express.js** — Veebiserver ja API raamistik
- **CORS** — Cross-origin request handling
- **Docker** — Konteineriseerimiseks
- **Docker Compose** — Konteinerite orkestreering

## Käivitamine

### Lokaalselt

```bash
# Paigalda sõltuvused
npm install

# Käivita rakendus
node src/server.js

# Käivita testid
node src/test.js
```

Rakendus jookseb aadressil **http://localhost:3000**

### Docker-iga

```bash
# Ehita ja käivita konteinerid
docker compose up
```

## Testikasutajad

| Kasutajanimi | Parool | Nimi |
|---|---|---|
| mari | 1234 | Mari Maasikas |
| jaan | 1234 | Jaan Jansen |

## API endpointid

### Kasutajad

| Meetod | URL | Kirjeldus |
|--------|-----|-----------|
| POST | /api/users/signup | Loo uus kasutaja |
| POST | /api/users/login | Logi sisse |
| POST | /api/users/logout | Logi välja |
| GET | /api/users/me | Tõmbade enda kasutajaandmed |

### Raamatud

| Meetod | URL | Kirjeldus |
|--------|-----|-----------|
| GET | /api/books | Tõmbake kõik raamatud |
| GET | /api/books/:id | Tõmbake üks raamat ID järgi |
| GET | /api/books/search | Otsi raamatuid (title ja author) |
| GET | /api/books/genres | Tõmbake kõik žanrid |
| GET | /api/books/genre/:genre | Tõmbake raamatud žanri järgi |

### Laenud

| Meetod | URL | Kirjeldus |
|--------|-----|-----------|
| POST | /api/loans | Laena raamat |
| POST | /api/loans/:id/return | Tagasta raamat |
| GET | /api/loans | Tõmbake kõik laenud |
| GET | /api/loans/me | Tõmbake enda laenud |

## Testid

Automaaattestide käivitamine:

```bash
# Veendu, et server käib
node src/server.js &

# Oota 3 sekundit ja seejärel käivita testid
node src/test.js
```

Testid kontrollitakse ka GitHub Actions-iga iga commit pushimise ajal.

## GitHub Actions

<!-- TODO: Kirjelda mis toimub automaatselt -->
