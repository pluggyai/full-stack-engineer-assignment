# Pluggy Full-Stack coding challenge
This is Pluggy's official full-stack engineer challenge that allows any developer that want to work with us to apply. We appreciate the time you're taking to give us a chance! We're anxious to see what's next. 

## Background
A really important part of our business is based on the collection, normalization, analysis, and showcase of information available on the web. To that end, the following challenge will cover all that. Please, take the time to read all the documents at once before starting, and remember: It's so much better DONE than PERFECT, so focus primarily on must-have features and leave nice-to-have's to the end!

### Business Logic

For regional purposes, candidates from Brazil will generate a USD to BRL dashboard, while candidates from Argentina will do a USD to ARS comparison.

## Task
The whole project consists of delivering a full-stack application, this involves frontend, backend, infrastructure, and everything to leave the application up and running. We're defining the Backend and Frontend, the rest is up to the tools you feel comfortable using:

### 1. Backend
Create an HTTP server (using `Node.js`) that exposes three different endpoints:

#### 1.a Quotes
GET `/quotes`: It returns an array of objects with USD quotes (or "dollar citations") retrieved from 3 different sources:

ARS:
- https://www.ambito.com/contenidos/dolar.html
- https://www.dolarhoy.com
- https://www.cronista.com/MercadosOnline/moneda.html?id=ARSB

BRL:
- https://wise.com/es/currency-converter/brl-to-usd-rate
- https://nubank.com.br/taxas-conversao/
- https://www.nomadglobal.com

The objects must have the following minimum structure/attributes (you can add new useful attributes and/or insights)
```json
{
  "buy_price": 140.3,
  "sell_price": 144,
  "source": "https://www.ambito.com/contenidos/dolar.html"
}
```

#### 1.b Average
GET `/average`: It returns an object with the average positions of all the quotes.

The objects must have the following minimum structure/attributes (you can add new useful attributes and/or insights)
```json
{
  "average_buy_price": 142.3,
  "average_sell_price": 147.4
}
```

#### 1.c Slippage 
GET `/slippage `: It returns an array objects with the information of how much slippage percentage there is between each source and the average.

The objects must have the following minimum structure/attributes (you can add new useful attributes and/or insights)
```json
{
  "buy_price_slippage": 0.04,
  "sell_price_slippage": -0.06,
  "source": "https://www.ambito.com/contenidos/dolar.html"
}
```

There is no requirement of _how_ to collect the information (you can either use web scrapping techniques, reverse engineering, just HTTP requests, etc.)

Must-have requeriments:
- Always retrieve fresh information (max time between last update is 60s)
- Deploy the project and make it available in some public URL (If no clue of doing this, we suggest using [Heroku](https://heroku.com))

Nice-to-have requeriments:
- TypeScript
- Serverless functions (you can easily use [Vercel](https://vercel.com) or [Serverless Framework](https://serverless.com) if you're new to this, but any serverless environment of your comfort does the job).
- Create a system caché that shows information no older than 60 seconds (could use Upstash or Supabase if needed)

### 2. Frontend
Create a frontend (using `React`) which displays the information of each backend endpoint, and automatically refreshes the data at least every `15 seconds`:

Must-have requeriments:
- Deploy the project and make it available in some public URL (If no clue of doing this, we suggest using [Vercel](https://vercel.com))

Nice-to-have requeriments:
- TypeScript
- Use [SWR](https://swr.now.sh) or [Redux](https://redux.js.org/) (and [Redux-Saga](https://redux-saga.js.org/)) or [React-Query](https://tanstack.com/query) or [Zustand](https://github.com/pmndrs/zustand)
- Use any UI framework that is your comfort. 

## Design
No guidelines here, but we'd love to be impressed 🤩 (With AI, You have no excuses!)
