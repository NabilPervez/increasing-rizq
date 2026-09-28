# Increasing Our Rizq

A daily Islamic checklist of eleven practices connected to *rizq* (provision), each paired with a
dhikr or du'a. Single self-contained HTML page — no build step, no framework, no dependencies
beyond the Google Fonts stylesheet.

> Provision is appointed, yet it may be increased by our actions, with the permission of God.

## The eleven practices

God-consciousness (*taqwā*) · Reliance on God (*tawakkul*) · Prayer · Faith and good deeds ·
Helping others · Keeping family ties · Thankfulness · Istighfar and repentance (*tawbah*) ·
Charity · Reciting Qur'an · Migrating for the sake of God

Each one carries the Qur'anic verse or hadith it rests on, linked to
[quran.com](https://quran.com) or [sunnah.com](https://sunnah.com), and expands to a dhikr or du'a
in Arabic with transliteration, meaning, and its own source reference.

## How it works

- **Daily checklist.** Tick a practice to mark it done; the progress bar tracks 0 → 11.
- **Tap counters.** Each dhikr has a circular tap counter with a goal. Where the sources give a
  number, that number is the default — istighfar defaults to 70 ("more than seventy times a day",
  Bukhārī 6307) and the du'a of thankfulness to 5 (once after each prayer). Everything else
  defaults to 1 with a note saying no set number is given in the sources.
- **Adjustable goals.** The − and + buttons change a goal; goals persist across days.
- **Reaching a goal** ticks the practice automatically and fires a short haptic buzz on devices
  that support `navigator.vibrate`.
- **Resets each day.** Checks and counts are keyed to the local date, so a new day starts clean.
  Goals are deliberately kept.

## Storage

Everything stays in `localStorage` on the device. Nothing is sent anywhere — there is no backend,
no analytics, and no accounts.

| Key | Holds | Lifetime |
| --- | --- | --- |
| `rizq-v2-<YYYY-MM-DD>` | practices ticked that day | that day only |
| `rizq-v2-<YYYY-MM-DD>-counts` | tap counts for that day | that day only |
| `rizq-targets` | your per-practice goals | kept |

Keys from previous days are pruned automatically on load.

## Running it

Open `index.html` in a browser. That's the whole thing.

To serve it locally instead:

```bash
python -m http.server 8000
```

## Notes

- Dark mode follows the system setting via `prefers-color-scheme`; motion is reduced under
  `prefers-reduced-motion`.
- Arabic is set in [Amiri](https://fonts.google.com/specimen/Amiri) with
  `Noto Naskh Arabic` and `Geeza Pro` as fallbacks; the interface is set in Inter. The fonts load
  from the Google Fonts CDN, so offline the page falls back to system faces and stays fully usable.
- Installable to a phone home screen — it carries the Apple and Android web-app meta tags and a
  theme colour.

## Credits

Ways summarized from Sheikh Rātib al-Nabulsī, Sheikh Māhir Muqaddim and Sheikh Ṣafwān Ḥanūf.
