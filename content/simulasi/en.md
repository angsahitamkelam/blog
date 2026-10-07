---
title: About Angsa Hitam
description: Tax simulation software for Indonesian individual taxpayers.
enableToc: false
tags:
  - simulasi
---

**Angsa Hitam** builds tax simulation software for employees and individual taxpayers in Indonesia.

## The problem

Every year Indonesian employers hand out a withholding certificate (bukti potong 1721-A1) that almost no employee can read. The rules are dense, the terminology is unfamiliar, and the calculators on the market ask for numbers the user does not have.

Harder still is the "what if" question. What if my PTKP (non-taxable income) status changes? What if I have additional income mid-year? What if I change employers? There is no way to try the answers without recalculating from scratch.

## What we're building

A simulation tool that works from the document you already have.

1. Upload a payslip or bukti potong 1721-A1.
2. The income components are read out of that document and become your simulation inputs.
3. Run scenarios: change your PTKP status, add income, change the employment period.
4. Each scenario returns a PPh 21 (personal income tax) figure, a plain-language explanation, and the rule behind each step.

No manual arithmetic, and no need to learn the terminology first.

## How it works

Two layers, deliberately separated:

**A deterministic calculation engine.** All arithmetic and rate application runs in our own rules-based engine. The same scenario always produces the same output, and every step of the calculation is inspectable.

**Claude for the language work.** We build on the Claude API from Anthropic for the parts that are genuinely language problems: reading income components out of payslips that differ in layout between employers, normalising them into a structured form, and generating the plain-language explanation with its legal basis.

**The model never performs the calculation.** For a tax tool this is a correctness requirement, not a preference: a simulated figure that cannot be reproduced or audited is worthless.

## What the simulation is not

Simulation output is a tool for understanding and planning. It is not an official computation, not a substitute for the withholding certificate issued by your employer, and not professional tax advice.

## Status

Prototype stage. The calculation engine is in development and the Claude API integration is being built. Not yet open to the public.

## Why Claude

- Long-context reading of messy Indonesian documents — payslips and withholding certificates are not consistent between employers, and the same field appears under many different labels.
- Reliable structured extraction through tool use, so document data lands in a typed schema rather than free text, ready to feed the calculation engine directly.
- Indonesian-language output clear enough for a taxpayer who is not an accountant.

## Company

- **Website:** https://angsahitam.com
- **Contact:** hanung@angsahitam.com
