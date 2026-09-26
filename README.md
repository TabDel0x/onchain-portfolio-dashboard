# Onchain Portfolio Dashboard

A dashboard concept for visualizing wallet holdings, token exposure, network activity, and simple portfolio movement across EVM networks.

## Product Idea

The dashboard is built around one question: what does this wallet actually hold and do? Instead of starting with price charts, it starts with wallet state: native balance, token distribution, network exposure, recent transfers, approvals, and contract interactions.

## Features

- Wallet balance overview
- Token allocation cards
- Network activity timeline
- Base-first portfolio view
- Simple PnL model experiments

## Data Flow

```txt
wallet address
  -> validate address
  -> fetch native balance
  -> fetch token balances
  -> normalize decimals
  -> attach token metadata
  -> calculate allocation
  -> render dashboard
```

## Dashboard Modules

| Module | Description |
| --- | --- |
| Wallet Summary | Native balance, token count, last activity |
| Allocation | Token exposure by percentage |
| Network Activity | Recent transfers and contract calls |
| Token Detail | Balance, metadata, and movement notes |
| Risk Hints | Approval reminders and unknown-token warnings |

## Technical Notes

- Token balances must be normalized with each token's `decimals`.
- USD values should be optional because price APIs can fail or lag.
- Unknown tokens should be shown cautiously, not hidden.
- Portfolio math should separate realized PnL from simple balance movement.
- Address input should be validated before making network calls.

## Roadmap

- Base-only MVP
- Multi-wallet comparison
- ERC-20 token metadata resolver
- CSV export
- Optional price adapter
- Approval exposure panel

## Stack

- React / Next.js
- TypeScript
- EVM data APIs
- Tailwind CSS

## Status

UI experiment and learning project.
