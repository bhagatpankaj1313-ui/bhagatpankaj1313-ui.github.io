# SafeCampus AI — PromptWars x Techverse Solutions

**Theme:** Defence & Security
**One line:** Don't click blind — check it first.

SafeCampus AI is a GenAI campus safety shield for students. One fake link
can drain a bank account or steal an Instagram account, and students are
the easiest target: fake KYC messages, "you won a prize" links, lookalike
login pages. SafeCampus checks the danger *before* you click, reply, or
reuse a password.

## What it does

| Tool | What works |
|---|---|
| **🔗 Phishing URL Checker** | Paste any link → Safe / Suspicious / Dangerous verdict + risk score 0–100, with a reason for every point (http not https, IP address, URL shortener, lookalike brand / typosquat, suspicious TLD, too many subdomains, `@` trick, long URL, suspicious words). 3 one-tap test examples: safe (google.com), suspicious (lookalike), phishing (IP link). |
| **💬 Scam Message Checker** | Paste an SMS / WhatsApp message → score + flags for urgency pressure, fake prize, fake bank/KYC, OTP requests, links, money/UPI demands, fake jobs. 3 one-tap test examples: safe class notice, suspicious prize, bank-KYC + OTP scam. |
| **🔐 Password Strength Checker** | Live entropy (bits), crack-time estimates (online vs offline attack), breach-pattern warnings (common passwords, sequences, repeats, one character type), and a 16-character strong password generator with copy button. Passwords never leave the browser. |
| **🚨 Campus Safety Alerts** | Sample alert feed with High / Medium / Low severity and filters. "Report a scam" form saves to localStorage and appears in the feed instantly. |
| **🤖 Gemini AI (optional)** | Paste your own Gemini API key in Settings (stored only in localStorage, never in code). The app calls `generativelanguage.googleapis.com/v1beta` with model `gemini-pro-latest` and a safety-analyst prompt for a second AI verdict on a link or message. **Without a key, everything still works** — offline heuristic checks give full verdicts and the app says "Demo mode" clearly. |
| **🌐 Hindi / English** | Header toggle translates the whole UI. Mobile-first — works at 360px wide. |

## Who it helps

BTech / college students in India — the group most targeted by KYC,
prize, job and Instagram phishing scams, and least likely to have any
security training. Also useful for parents and first-time smartphone users.

## Run it

No build, no install, no login, no server needed:

```bash
cd promptwars-techverse
python3 -m http.server 8000
# open http://localhost:8000
```

Or just double-click `index.html`. Everything works offline except the
optional Gemini call.

## AI part

- Offline heuristics do the first verdict (fast, private, always available).
- Gemini (`gemini-pro-latest`) gives a second opinion when the user adds
  their own key in Settings. The key is stored only in the browser's
  localStorage and sent only to Google's API — it is never written into
  the code or the repo.

## Judging — Impact / Creativity / Design / Execution

- **Impact:** a real, daily problem for every student with a phone.
- **Creativity:** three safety tools + live alerts + AI second opinion in
  one page, in English and Hindi.
- **Design:** dark navy, green/red verdicts, mobile-first, every button
  works.
- **Execution:** no login, no key required, no broken sections — judges
  open it and it just works.
