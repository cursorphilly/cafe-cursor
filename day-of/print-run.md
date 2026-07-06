# Print run — July 16, 2026

Checklist for batch-printing Cafe Cursor Issue 1 AR zines.

## Before you print

1. Confirm latest deploy: https://zine-ar-lemon.vercel.app
2. Open print view: https://zine-ar-lemon.vercel.app/print
3. Test one copy: print 3 landscape sheets → staple → scan cover QR → verify AR on spreads 1–2
4. Test in lighting similar to Percy Diner (bright, even — avoid glare)

## Quantity

```text
copies = Luma RSVPs + 20% buffer
sheets = copies × 3
```

Check RSVPs: https://luma.com/tkx269iu

| RSVPs | Copies (+20%) | Total sheets |
|-------|---------------|--------------|
| 20 | 24 | 72 |
| 30 | 36 | 108 |
| 40 | 48 | 144 |
| 50 | 60 | 180 |

Re-run this table with your actual RSVP count before printing.

## Print settings

- **Paper:** matte cardstock or heavy matte paper (avoid glossy)
- **Orientation:** landscape, one page per sheet
- **Quality:** best / photo quality for tracking detail
- **Finish:** staple upper-left corner or binder clip

## Day-of

- Credits: distribute individual links at check-in — not printed on zine ([CREDITS.md](../CREDITS.md))
- Table prompt: "Fork zine-ar, add page 3" — see [project-ideas.md](../inspiration/project-ideas.md)

## Regenerate artwork (if copy changes)

From the [zine-ar](https://github.com/luiscielak/zine-ar) repo:

```bash
npm run make-cafe-pages
npm run compile-targets
vercel --prod
```

Then reprint from `/print`.
