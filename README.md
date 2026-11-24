# Prism

Color long text with your own regex rules.

Paste a log, alert, command line or JSON dump and every rule colors its matches. Hover any hit to see the match, its capture groups, where it sits and the text around it; click to pin it and step through that rule's hits. Rules have their own colors, styles and notes. Save them as named sets in your browser, or to a `.prism.json` file to share.

**Good for:** Triage of long logs, spotting indicators in pasted alerts, and building a reusable set of patterns for a case.

- Optional starter DFIR rules (Sets → Add the starter DFIR rules): suspicious tooling, URLs, IPv4, email, domains, SHA-256/SHA-1/MD5, Windows paths, registry keys, timestamps, Base64 blobs (defanged forms included)
- Top rule wins where hits overlap; drag to reorder
- Show only lines with hits, wrap long lines, choose how much context the hover shows
- Render markdown with the highlights intact: links aren't clickable and show where they really go, images are never loaded, raw HTML is shown as text
- **Download** saves Prism as one HTML file to run offline
- Make a rule from selected text
- Matching runs in a worker; a runaway pattern is paused instead of freezing the page
- Save rules as named sets in the browser, to a `.prism.json` file, or as a shareable link
- Export hits as CSV, the highlighted text as HTML, or the rules as JSON; send indicators to Tessera, timed hits to Recap, hits to Shifu
- Keys: `N` next hit, `Shift+N` previous, `Esc` closes a pinned hit

**Live:** https://jon.glass/prism/

Links: `?sample=1` opens the sample log (`?sample=md` the sample markdown), `?src=<https URL>` loads a file (repeat it to load several), and `#rules=…` (from **Sets → Copy a link to these rules**) loads a rule set.

A single self-contained page with no build step. Open `index.html` or serve the folder over HTTPS. Nothing you paste leaves your browser, and pasted text is gone when you close the tab unless you turn on **Text → Keep text between visits**.

Uses the shared suite script at `/assets/suite/handoff.js` from [jon.glass](https://jon.glass) to send indicators to Tessera, timed hits to Recap and the hits table to Shifu, so cross-tool handoff only works when served from jon.glass.

## License

MIT © 2026 [Jon Glass](https://jon.glass/). Use it however you like; just keep the copyright notice. See [LICENSE](LICENSE).
