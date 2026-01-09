# Finora

Finora is an intelligent fintech platform built for MEIs and micro-businesses, created to solve the lack of financial predictability that small entrepreneurs face every day.

As a SaaS platform, Finora connects to financial data via Open Finance and through Finora’s own APIs for direct integration with banks and financial institutions. This gives small businesses bank-level technology with more control, flexibility, and scalability.

Finora automatically organizes income and expenses, generates intelligent cash-flow forecasts, and delivers actionable insights powered by predictive AI. Entrepreneurs can understand their current financial situation, anticipate future scenarios, and make better decisions without needing advanced financial knowledge.

With a modern, clear, and jargon-free experience, Finora brings clarity, autonomy, and financial peace of mind to small businesses.

---

## Project overview

This repository contains the backend foundations and documentation for the Finora fintech SaaS platform. It is focused on architecture, configuration, and planning for an API-first backend that will serve:

- Micro-entrepreneurs (MEIs) and micro/small businesses
- Embedded banking integrations via Open Finance and proprietary banking APIs
- Predictive AI services for cash-flow forecasting and financial insights

> Note: this MVP repository currently contains documentation and configuration only. Core backend services and APIs should be implemented following the architecture described here.

## Main features (planned)

- **User authentication & tenants** – secure, multi-tenant login for business owners and collaborators.
- **Bank connections** – integrations with Brazilian Open Finance and proprietary Finora banking APIs.
- **Transactions & categorization** – automatic import and categorization of income and expenses.
- **Predictive cash-flow engine** – forecasts of future balances, runway, and risk scenarios.
- **AI insights** – clear, actionable suggestions (cash shortage alerts, expense optimization, revenue trends).
- **Dashboards** – real-time view of cash flow, revenues, and key indicators for small businesses.

## Getting started (local setup)

Because this repository is in an architecture/documentation stage, there is no runnable backend server yet. You can still prepare your environment as follows:

1. **Clone the repository** (after you push it to GitHub):
   - `git clone https://github.com/<your-org>/finora.git`
   - `cd finora`
2. **Install Node.js dependencies (when backend code is added):**
   - `npm install` or `yarn install` or `pnpm install`
3. **Create your local environment file:**
   - Copy `.env.example` to `.env` and adjust values (database URL, JWT secret, etc.).
4. **Run the backend (to be implemented):**
   - Once a server entrypoint is added (e.g. `src/main.ts`), define scripts in `package.json` like:
     - `npm run dev` – start development server
     - `npm test` – run tests

Until the backend code is added, `package.json` only contains placeholder scripts and no runtime code.

## Planned folder structure

A suggested structure for the future backend implementation is:

```text
src/
  app/                  # NestJS/Express/Spring-style application bootstrap
  modules/
    auth/               # user auth, tenants, roles
    bank-connections/   # Open Finance + proprietary bank integrations
    transactions/       # transaction storage and categorization
    dashboards/         # aggregated metrics for UI
    insights/           # AI-powered financial insights
  config/               # configuration and environment loading
  common/               # shared utilities, middleware, guards
```

This structure is not yet created in the repository to avoid generating code; it serves as a guide for future development.

## API overview (high level)

The Finora backend is designed as an API-first service with the following main areas:

- `Auth` – registration, login, refresh tokens, and user profile.
- `Bank connections` – manage Open Finance consents, proprietary banking connections, and manual sync.
- `Transactions` – list, filter, and import bank transactions.
- `Dashboards` – summarized cash-flow and revenue metrics for the UI.
- `Insights` – AI-driven insights generated from transactions, forecasts, and cash-flow signals.

Typical future endpoints (illustrative only):

- `POST /api/v1/auth/login`
- `GET  /api/v1/bank-connections`
- `GET  /api/v1/transactions`
- `GET  /api/v1/dashboards/overview`
- `GET  /api/v1/insights`

These endpoints are **not yet implemented** in this repository.

## Environment variables

All configuration is expected to be provided through environment variables. See `.env.example` for a complete list. Common variables include:

- `FINORA_APP_ENV` – runtime environment (development, staging, production)
- `FINORA_APP_PORT` – HTTP port for the backend server
- `FINORA_DATABASE_URL` – PostgreSQL connection string
- `FINORA_JWT_SECRET` – secret used to sign access tokens
- `FINORA_OPEN_FINANCE_CLIENT_ID` – client ID for Open Finance integrations

## License

This project is licensed under the MIT License – see the [`LICENSE`](LICENSE) file for details.
