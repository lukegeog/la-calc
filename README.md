# LA Calc

A focused max-dose calculator for the four local anaesthetics most used in UK plastic surgery: lidocaine 1%, lidocaine 2%, bupivacaine 0.25%, and bupivacaine 0.5%, each with and without adrenaline (1:200,000).

Single-file Progressive Web App (PWA). No data leaves the device. Add to your home screen and it opens like a native app.

## What it shows

Input patient weight → it calculates max dose (mg) and volume (ml) for each LA from pure mg/kg, plus total adrenaline (µg) per row for awareness.

## Doses used

| Drug                 | mg/kg |
|----------------------|-------|
| Lidocaine plain      | 3     |
| Lidocaine + adr      | 7     |
| Bupivacaine plain    | 2     |
| Bupivacaine + adr    | 3     |

**No caps applied.** The calculator outputs pure mg/kg dosing — no absolute mg ceiling and no enforced adrenaline ceiling. The conventional 250 µg adrenaline limit is *displayed* per row (1:200,000 = 5 µg/ml) but not auto-clamped; that judgement is yours to make.

**Note on bupivacaine + adrenaline.** The 3 mg/kg used follows local trust protocol. BNF is more conservative at 2 mg/kg, citing cardiotoxicity (not absorption) as rate-limiting. If you move trusts and the local protocol differs, edit the `bupi025` and `bupi05` `adrMgKg` values at the top of the script block in `index.html`.

## Disclaimer

Personal reference tool. Not authoritative. Always check the vial label, BNF, and your local / AAGBI protocols before dosing. Numbers above are based on BNF maximums and the assumptions stated; your trust may differ.

## Deployment

This is a separate single-file PWA from Pedicle. Two options:

**Option A — separate GitHub repo.** Easiest to keep apps cleanly separated.

```bash
cd "/Users/lukegeog/Documents/Claude/Projects/Clinical work/la-calc"
git init -b main
git add .
git commit -m "Initial commit: LA Calc"
# Create a new private repo at github.com/new (e.g. 'la-calc'), then:
git remote add origin https://github.com/<your-username>/la-calc.git
git push -u origin main
# Then on GitHub: Settings → Pages → Branch: main → Save.
```

URL will be `https://<your-username>.github.io/la-calc/`. Open in Safari, Share → Add to Home Screen, and it sits next to Pedicle on your home screen.

**Option B — same repo as Pedicle.** Add `la-calc/` as a subdirectory of the existing pedicle repo. The app will be accessible at `https://<your-username>.github.io/pedicle/la-calc/`. Less clean but fewer repos to manage.

## File layout

```
la-calc/
├── index.html      # the entire app (HTML + CSS + JS)
├── README.md       # this file
└── icon/           # source assets for the icon (if present)
```

## License

MIT.
