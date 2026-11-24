# STACKR: Smart Credit Card Recommendations for India

STACKR is a full-stack fintech web app that recommends and compares credit cards for Indian users from their spending, income and credit score. It estimates the yearly value (₹) of each card, ranks the cards, and explains why each one fits.

## Features

- **Personalized ranking.** A recommendation engine scores cards on your spending profile (travel, cashback, fuel, and so on)
- **Compare and calculate.** Side-by-side comparison, a rewards calculator and a spending simulator
- **Timing intelligence.** Uses historical offer data to suggest whether to apply now or wait for a better offer
- **Insights.** Rule-based, plain-language explanations of why the top card fits your spending
- **Accounts and subscriptions.** JWT auth and a premium plan through Razorpay (test mode)

## Tech stack

| Layer | Tech |
|---|---|
| Frontend | Next.js (App Router), TypeScript, Tailwind CSS |
| Backend | Node.js, Express, JWT, bcrypt |
| Data | PostgreSQL, Redis (caching) |
| Payments | Razorpay |
| Dev infra | Docker Compose |

## Quick start

**Requirements:** Node.js 18+, Docker Desktop

**Windows (one click):**

```bat
run_all.bat
```

**Manual:**

```bash
docker-compose up -d                         # Postgres + Redis
cd backend  && cp .env.example .env && npm install && node src/server.js
cd frontend && npm install && npm run dev    # in a second terminal
```

Open http://localhost:3000.

> Fill in your own Razorpay **test** keys in `backend/.env`. Never commit real keys.

## Project structure

```
backend/
  src/routes/     auth, cards, subscription, timing
  src/services/   recommendation, timingIntelligence, cron
frontend/
  src/app/        cards, compare, calculator, simulator, timing, profile, upgrade ...
  src/components/ AIInsights, RazorpayCheckout, TimingIntelligence ...
docker-compose.yml
run_all.bat
```

## License

[MIT](LICENSE)
