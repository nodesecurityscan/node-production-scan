# 🛡️ Node Production Scan

Stop wasting time on false positives from npm audit.

This tool helps you understand:

- which vulnerabilities are реально exposed in production
- and which ones are just noise (dev dependencies, tooling, non-runtime paths)

---

## Example (Express)

- Critical: 1
- High: 3
- Runtime exposure: 0

👉 npm audit says "high risk"  
👉 production reality: no runtime exposure

---

This is the gap this tool solves.
---

## 🎯 Purpose

Most automated tools (like `npm audit`) report **all known vulnerabilities**, without context.

This often leads to:

- inflated results  
- unnecessary panic  
- wasted time on non-critical issues  

👉 This project focuses on **what actually matters in production**.

---

## 🧠 Approach

The analysis distinguishes between:

### 🔴 Effective Vulnerabilities
Issues that are:
- present in runtime dependencies  
- reachable in production code paths  
- realistically exploitable  

### 🟡 Noise (Non-Effective Vulnerabilities)
Issues that are:
- in devDependencies  
- not executed in production  
- not reachable  
- theoretical or non-exploitable  

---

## ⚡ Key Idea

> npm audit tells you what is vulnerable  
> this tool tries to tell you what is actually exploitable

---

## 📦 Input Required

For a first analysis, you don’t need the full project.

Only:

- `package.json`
- lock file (`package-lock.json` or `yarn.lock`)

---

## 📊 Output

The report includes:

- Raw vulnerabilities (from audit tools)  
- Effective vulnerabilities (filtered)  
- Risk score (0–100)  
- Production risk assessment  
- Actionable recommendations  

---

## Sample report

👉 [View Express report](./reports/express-healthcheck.pdf)

Real example where:
- npm audit reports critical/high
- but runtime exposure = 0

---

## 🚀 Status

Work in progress — currently validating the approach on real-world projects.

---

## 💬 Feedback

If you have a Node.js project and want a quick analysis:

👉 feel free to reach out or share your `package.json` + lock file

---

## ⚠️ Disclaimer

This is not a replacement for full security audits.  
The goal is to provide **a quick, realistic view of production risk**.

---
