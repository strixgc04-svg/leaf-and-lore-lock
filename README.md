# Leaf & Lore store lock

Remote on/off switch for the Leaf & Lore Shopify theme (BLU X LEAF).

The theme reads [`lock.json`](lock.json) from this repo on every page load:

```json
{
  "locked": false,
  "message": "Store access denied. Please contact the developer.",
  "contact": ""
}
```

| Field     | What it does |
| --------- | ------------ |
| `locked`  | `true` covers the storefront with the message below. `false` shows the store normally. |
| `message` | Text shown on the lock screen. |
| `contact` | Optional email, phone or URL shown under the message (an email becomes a mailto link). |

## Turning it on or off

Edit `lock.json` on GitHub (pencil icon), change `locked`, and commit. Shoppers see the change within about
5 minutes (GitHub's raw file cache).

## Good to know

- The theme code lives in `snippets/ll-store-lock.liquid` and is rendered from `layout/theme.liquid`.
- If GitHub can't be reached or the file is invalid, the store stays **open** (fails safe for shoppers).
- It's a storefront overlay, not access control: checkout links, the Shopify admin and APIs are not affected.
- This repo must stay **public** so shoppers' browsers can read `lock.json`. Keep nothing secret here.
