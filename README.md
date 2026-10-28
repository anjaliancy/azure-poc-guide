# Building a proof of concept on Azure (guide website)

A single static page (`index.html`): no build step, no dependencies, no data, no secrets.
It has a plain-language mode and a "with technical detail" mode, a decision-matrix tool, a rough
cost estimator and a tickable checklist. Everything runs in the browser; ticks and matrix edits
are saved in the visitor's own browser only.

## Run it locally
Open `index.html` in a browser, or:

    npx serve .

Add `?mode=builder` to the address to open the technical view.

## Deploy to Vercel
Deploy this folder as its own project.

    cd azure-poc-guide
    npx vercel            # first time: log in, accept the defaults ("Other" framework, no build command)
    npx vercel --prod     # publish

Or in the Vercel dashboard: New Project, import the repository, set **Root Directory** to
`azure-poc-guide`, framework preset **Other**, leave build and output settings empty.

`vercel.json` adds security headers and a strict content-security-policy (the page loads nothing
from other sites).

## Before you share it
- The cost figures are rounded planning figures, not quotes. Re-check them against the Azure
  pricing calculator and update the `ITEMS` list in the script at the bottom of `index.html`.
- The example (LeaveLoop) is fictional. Add your organisation's own IT contacts and policies if
  you want to make it an internal guide.
- Keep the page free of real data, names and credentials.

## PDF copies
`Azure-POC-Guide-plain.pdf` and `Azure-POC-Guide-technical.pdf` are print exports of the two
views. Regenerate them after any content change (print from the browser with the mode you want,
background graphics on).

## Font
The page uses Nunito (SIL Open Font License, see `fonts/OFL.txt`), served from `fonts/` so the page still loads nothing from other sites.
