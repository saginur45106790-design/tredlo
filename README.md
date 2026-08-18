# Tredlo — Real-Market Production Starter

This repository is a production-oriented architecture for a regulated/authorized real-market trading product.

It deliberately uses PROVIDER ADAPTERS rather than fake live execution. You must connect a licensed broker/exchange, licensed market-data provider, KYC/AML provider and payment/custody provider appropriate to the jurisdictions you serve.

## Included
- Next.js professional terminal starter
- Express API
- Provider interfaces for market data, execution, KYC and payments
- PostgreSQL/Prisma schema
- Double-entry ledger schema
- Orders, fills, positions
- Risk-check service skeleton
- Audit log
- Admin API skeleton
- WebSocket market-feed adapter
- Docker and Render deployment templates
- Production checklist

## Not included
- Broker credentials
- Payment credentials
- KYC vendor credentials
- Regulatory licence
- Customer-fund custody
- Real-money execution without an authorized provider

## Run
1. `cp apps/api/.env.example apps/api/.env`
2. `docker compose up -d db`
3. `npm install`
4. `npm run db:generate`
5. `npm run db:push`
6. `npm run dev:api`
7. `npm run dev:web`

Web: http://localhost:3000
API: http://localhost:4000

## Regulatory note
If operating from Bangladesh, obtain professional legal/regulatory advice before accepting customer funds or providing brokerage/foreign-exchange services. Bangladesh Bank regulates foreign-exchange activity and BSEC registers/regulates stock brokers and other securities-market intermediaries. See the official sources in `docs/REGULATORY.md`.
