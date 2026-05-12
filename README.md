# LA Calc

A focused max-dose calculator for the four local anaesthetics most used in UK plastic surgery: lidocaine 1%, lidocaine 2%, bupivacaine 0.25%, and bupivacaine 0.5%, each with and without adrenaline (1:200,000).

Single-file Progressive Web App (PWA). No data leaves the device. Add to your home screen and it opens like a native app.

## What it shows

Input patient weight → it calculates max safe dose (mg) and max volume (ml) for each LA, and indicates which limit is binding (mg/kg, absolute cap, or — for adrenaline-containing solutions — the adrenaline 250 µg cap). Rows where the adrenaline cap bites are highlighted in amber.

## Doses used

| Drug                 | mg/kg        | Absolute cap |
|----------------------|--------------|--------------|
| Lidocaine plain      | 3            | 200 mg       |
| Lidocaine + adr      | 7            | 500 mg       |
| Bupivacaine plain    | 2            | 175 mg       |
| Bupivacaine + adr    | 3            | 225 mg       |

Adrenaline 1:200,000 = 5 µg/ml. Total adrenaline cap = 250 µg → volume cap of 50 ml of solution.

**Note on bupivacaine + adrenaline.** The values used (3 mg/kg, 225 mg cap) follow local trust protocol. BNF is more conservative at 2 mg/kg, citing cardiotoxicity (not absorption) as rate-limiting. If you move trusts and the local protocol differs, edit the `bupi025` and `bupi05` `adrMgKg` / `adrCap` values at the top of the script block in `index.html`.

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
