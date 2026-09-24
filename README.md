# Multi-site booking automation

End-to-end automation of the same hotel-booking journey across three different booking sites, to check whether one use case can be validated against three completely different interfaces.

Built with **WebdriverIO** (JavaScript, Node.js).

## Why

Booking flows look the same to a user and are completely different underneath: different DOM structures, different date pickers, different navigation.
The interesting question isn't "can I automate one site", it's how much of the test can be shared before each site forces you to fork the logic.

## What it covers

| Site | Flow |
|---|---|
| <sitio 1> | Search → select dates → pick a hotel → booking form |
| <sitio 2> | " |
| <sitio 3> | " |

## Stack

- WebdriverIO — test runner and browser automation
- Node.js / npm

## Running it

```bash
npm install
npx wdio run wdio.conf.js
```

## What I took from it

- Date pickers are where cross-site automation breaks down: every site implements them differently, and they are the least stable part of the flow.
- Loading indicators forced a different waiting strategy on each site: one showed a single loader for the whole page, another rendered one loader per component. There is no generic "wait until the page is loaded", therefore I wait for the element I am about to use.

---

*Originally built as a technical exercise; it led to my SDET role at Mil Mas 8 SL.*
