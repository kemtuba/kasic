# Light that listens — feed prototype

A single static page (`index.html`): a vertical swipe feed of four pieces, a generated-light canvas that follows a Web Audio synth, a sound toggle and a next button. No build step, no dependencies beyond Google Fonts.

## Deploy to Vercel

Either route gives you a `*.vercel.app` URL in about a minute.

**From GitHub (recommended, redeploys on every push)**

1. Push this folder to a repo.
2. On https://vercel.com/new import the repo. Framework preset: **Other**. Leave build command and output directory empty. Deploy.

**From your machine**

```sh
cd kasic-feed
npx vercel --prod
```

Accept the defaults when the CLI asks (no build command, output directory `.`).

## Attach kasic.xyz

1. In the Vercel project: **Settings → Domains → Add Domain**, enter `kasic.xyz`, accept the suggested `www.kasic.xyz` redirect.
2. If you bought the domain through Vercel, you're done.
3. If you bought it elsewhere, add the records the domain card shows at your registrar:
   - `kasic.xyz` → **A** record, value as shown on the card (commonly `76.76.21.21`; newer projects may be given a different address)
   - `www` → **CNAME** record, the per-project target shown on the card (looks like `xxxx.vercel-dns-017.com`)

   Or, simpler, point the domain's nameservers at `ns1.vercel-dns.com` and `ns2.vercel-dns.com`.

Vercel issues the certificate once the records resolve; the card turns green.

CLI equivalent after `npx vercel --prod`:

```sh
npx vercel domains add kasic.xyz
npx vercel domains inspect kasic.xyz   # shows the exact records to set
```
