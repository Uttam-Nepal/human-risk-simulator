Human Risk Simulator

A standalone, single-file interactive artifact 

It accompanies the group report on Scenario B (Online Retail Business) and
simulates three of the human-factor failures described in that report:

1. **Inbox: Invoice Fraud** — spot the phishing email among six inbox items,
   modelled on the fake-invoice attack described in the report.
2. **Password & Hashing Lab** — live SHA-256 hashing (via the browser's native
   Web Crypto API), an entropy/crack-time calculator, and a salt demonstration.
3. **MFA Fatigue Test** — a burst of six login-approval prompts with a shrinking
   response window, one of which is the attacker.

A running **Human Risk Index** and a full **Case Log** (with a session restart
button) tie the three modules together.

All data — names, emails, addresses, passwords — is fictional, generated for
this coursework demonstration. No real accounts, breach data, or personal
information are used, per the assessment's safety rule.

## Running it locally

No build step, no dependencies. Just open `index.html` in any modern browser.

```bash
open index.html      # macOS
start index.html      # Windows
xdg-open index.html   # Linux
```

## Deploying

This repo is set up to deploy as-is on [Vercel](https://vercel.com):

1. Push this repo to GitHub.
2. On vercel.com, **Add New → Project**, import this repo.
3. Framework preset: **Other** (static HTML, no build settings needed).
4. Deploy.

`index.html` sits at the project root, so Vercel serves it directly at the
deployment's root URL.

## Editing

Everything — markup, styles, and logic — lives in the single `index.html`
file. There are three data arrays near the top of the `<script>` block worth
knowing about if you want to change the scenario content:

- `emails` — the six inbox items in Module 1 (sender, subject, body, whether
  it's phishing, and the explanation flags shown after a decision).
- `mfaPrompts` — the six MFA push notifications in Module 3 (device, location,
  whether it's the attacker, and how long the response window is).

The Human Risk Index starting value (`RISK_START`) and the initial log entry
(`INITIAL_LOG`) are also defined near the top of the script if you want to
change the baseline.

## Academic integrity note

Built with AI assistance (Claude) for the interactive demonstration only. The
scenario analysis, threat/human-factor reasoning, and recommendations in the
accompanying report are the group's own work — see the report's AI Use
Acknowledgement.
