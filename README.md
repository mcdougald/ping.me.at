<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/hero-dark.png">
    <img src=".github/assets/hero.png" alt="ping.me.at landing page" width="880">
  </picture>
</p>

<h1 align="center">ping.me.at</h1>

<p align="center"><strong>A status page that only reports what it saw.</strong></p>

<p align="center">
  <img src="https://img.shields.io/badge/status-in%20development-171717?style=flat-square" alt="Status: in development">
  <img src="https://img.shields.io/badge/license-source--available-404040?style=flat-square" alt="License: source-available">
  <img src="https://img.shields.io/badge/self--host-supported-525252?style=flat-square" alt="Self-host: supported">
  <img src="https://img.shields.io/badge/part%20of-me.at-737373?style=flat-square" alt="Part of me.at">
</p>

<p align="center">
  <a href="#features">Features</a> ·
  <a href="#how-it-works">How it works</a> ·
  <a href="#screenshots">Screenshots</a> ·
  <a href="#built-with">Built with</a>
</p>

Most status pages stay green until someone remembers to change them. I built ping.me.at so the page is the measurement: it checks each service with a real request and shows the result live, and when it cannot tell, it says **unknown** instead of guessing. Sign in and host status pages for your own services, publish incidents on your own domain, and keep a public history your users can trust. It also runs the network status board for the `*.me.at` family.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/overview-dark.svg">
    <img src=".github/assets/overview.svg" alt="ping.me.at at a glance: real checks, four states, honest about itself, your page on your domain" width="880">
  </picture>
</p>

## Why ping.me.at

| The usual status page | ping.me.at |
| --- | --- |
| Shows what someone last typed in | Shows what a real request just saw |
| Up or down | Operational, unreachable, unknown or late |
| Hides its own gaps | Lists its blind spots, with dates |
| "99.99% uptime" with no denominator | Every figure says how much of the period it covers |

## Features

- **Live, uncached checks**: every visit sends one real request to each service, with a timeout, and a failing check cannot break the rest of the page.
- **Four states, not two**: operational, unreachable, unknown and late, with every row labelled with where it was checked from.
- **Honest about itself**: ping shows its own row as unknown, states its check interval, and keeps a dated list of its blind spots on the board.
- **Scheduled checks with bounded history**: a scheduled prober keeps raw samples and rolled-up daily totals, and every uptime figure shows how much of the period it covers.
- **A second view from outside**: regional readings from outside the network are combined by strict majority, and a split shows as unknown.
- **Hosted status pages**: public or private pages at their own address, on a custom hostname verified by DNS record, each with its own monitors, history and incidents.
- **Heartbeats and scripted browser checks**: scheduled jobs check in to their own URL (a missed check-in shows as late), and short browser scripts run on a schedule against a runner you provide.
- **Double opt-in email updates and open formats**: subscribers confirm before anything is sent, and the status document is also served as JSON, RSS and static HTML.

## How it works

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/flow-dark.svg">
    <img src=".github/assets/flow.svg" alt="How ping.me.at works: probe, confirm, record, publish, notify" width="880">
  </picture>
</p>

A check is one real request with a timeout. Readings from outside the network are combined by strict majority, so a split vote becomes unknown rather than a guess. Samples are kept raw and rolled up into daily totals, then published as a page, JSON, RSS and static HTML, with email going only to subscribers who confirmed.

## Screenshots

<table>
  <tr>
    <td width="50%"><picture><source media="(prefers-color-scheme: dark)" srcset=".github/assets/hero-dark.png"><img src=".github/assets/hero.png" alt="Landing page"></picture><br><sub>The landing page: what ping checks and how it reports.</sub></td>
    <td width="50%"><picture><source media="(prefers-color-scheme: dark)" srcset=".github/assets/pricing-dark.png"><img src=".github/assets/pricing.png" alt="Pricing"></picture><br><sub>Pricing: the free and Pro plans for hosted status pages, and how a self-hosted instance is licensed.</sub></td>
  </tr>
</table>

## Built with

<p>
  <img src="https://img.shields.io/badge/Next.js-16-000000?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js 16">
  <img src="https://img.shields.io/badge/React-19-171717?style=flat-square&logo=react&logoColor=white" alt="React 19">
  <img src="https://img.shields.io/badge/TypeScript-5-262626?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Tailwind%20CSS-4-404040?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS 4">
  <img src="https://img.shields.io/badge/Drizzle-Postgres-525252?style=flat-square&logo=drizzle&logoColor=white" alt="Drizzle ORM and Postgres">
  <img src="https://img.shields.io/badge/Cloudflare-Workers-737373?style=flat-square&logo=cloudflare&logoColor=white" alt="Cloudflare Workers">
</p>

- Next.js 16 (App Router), React 19, TypeScript
- Tailwind CSS 4
- Drizzle ORM + Postgres
- Better Auth
- oRPC
- Cloudflare Workers via OpenNext (`@opennextjs/cloudflare`)
- Resend for subscriber email

## Part of the me.at family

ping.me.at is one of my [`*.me.at`](https://me.at) apps. They share one design system, one account, and one app shell. Development happens in a private monorepo; this repository is the project's public-facing home.

## License

Source-available. See [LICENSE](LICENSE).
