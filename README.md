# Mono Calculator

A lightweight currency calculator that uses [Monobank](https://monobank.ua) (Ukraine) exchange rates. Convert between EUR, USD, UAH, RON, and PLN in real time.

**Live demo:** [https://kvlvitalii.github.io/mono-converter](https://kvlvitalii.github.io/mono-converter)

## Features

- **Calculator** — Enter amount in EUR and get instant conversion to UAH, USD, RON, and PLN
- **Live rates** — Fetches buy/sell rates from Monobank API on page load
- **Currency converter** — Convert between any supported currencies
- **Rates table** — View current EUR, USD, RON, and PLN rates against UAH
- **Rate limit handling** — 60-second cache to avoid Monobank's request limit (1 req/min)

## Supported Currencies

| Currency | Code |
|----------|------|
| Euro | EUR |
| US Dollar | USD |
| Ukrainian Hryvnia | UAH |
| Romanian Leu | RON |
| Polish Zloty | PLN |

## Usage

### Web (HTML)

1. [Open live demo](https://kvlvitalii.github.io/mono-converter) in browser
2. Or open `index.html` locally
3. Enter amount in EUR and click **Розрахувати** (Calculate)
4. Use the converter at the bottom for custom conversions

### Python CLI

```bash
pip install -r requirements.txt
python calculator.py
```

Enter amount in EUR and press Enter. Multiple conversions per session use cached rates (60 sec).

## Project Structure

```
monocalculator/
├── index.html      # Web app (single file, no build step)
├── calculator.py   # CLI version
├── requirements.txt
└── README.md
```

## API

Uses [Monobank Bank API](https://api.monobank.ua/docs/) — public endpoint, no auth required.

- Endpoint: `https://api.monobank.ua/bank/currency`
- Rate limit: 1 request per 60 seconds (per IP)

## License

MIT
