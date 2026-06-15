# Launchpad

A personal dashboard for launching your saved job searches fast. It's one HTML file. Open it in a browser and it runs. No install, no server, no account.

If you keep bookmarks for the same searches across LinkedIn, Google, Indeed, and other sites, digging through browser folders every day gets old. Launchpad stages those searches in one place so you can fire off the ones you want, alone or in batches, and it adjusts the time window on LinkedIn and Google searches so you mostly see what's posted since your last check.

## Privacy

Everything lives in your browser. Your searches save to that browser's local storage, and nothing is sent anywhere. There's no backend and no tracking. The only outside request is to Google Fonts for the typeface.

## How it's organized

Three levels:

- **Group** is the source: LinkedIn, Google, or Custom (anything else).
- **Subgroup** is a search term or role, like Accountant or Storage Admin.
- **Link** is one saved search, tagged with a city or location shown as a badge.

So "LinkedIn → Accountant → Raleigh, NC" is one search. You can stack several cities under one term with no extra clicks.

## Time windows

This is the part that saves real time. Each link tracks when you last opened it and shows that on the row ("5h ago", "2.3d ago"). What happens when you launch depends on the group type:

- **LinkedIn** rewrites the `f_TPR` value in the URL. The default, "since last opened," sets the window to the exact gap since your last click, padded by 10 minutes so a posting on the boundary doesn't slip through. You also get presets (6h, 12h, 24h, 2d, 3d) and a custom value in hours or days.
- **Google** rewrites the "in the last N days" phrase in the search. Google filters only by whole days, so you read the timer and pick a bucket (1, 2, 3, 5 days, 1 week, 2 weeks, 1 month).
- **Custom** launches the link as saved and tracks when you last opened it. No window rewriting, since other sites each handle dates their own way.

## Opening searches

Check the boxes on the rows you want and click "Open selected." Check the box next to a term name to grab all of its searches at once.

Opening several tabs at once needs pop-ups allowed for the page. If only the first tab opens, allow pop-ups for the site (or turn the blocker off for it) and try again. A note at the top of the page reminds you.

## Backup

Use the Backup menu to export everything to a JSON file, named `backup_yyyy_mm_dd.json` with the current date. That file holds every group, subgroup, link, and setting. Import reads it back, so it's also how you move your setup to another computer.

Your searches auto-save to whichever browser you're using, but that's one browser only. Export gives you a real backup and a way to carry it across machines.

## Import bookmarks

Starting from a pile of existing bookmarks? You can bring them in. A web page can't read your live browser bookmarks directly, so export them first: open your browser's bookmark manager and choose Export bookmarks to an HTML file. Then in Launchpad, click "Import bookmarks," pick that file, browse the folders, and check the ones you want. Finally, choose where they land: an existing group and term, or new ones you name on the spot.

## Color schemes

Six themes in the "Color scheme" dropdown: Default (warm paper), Midnight (deep navy), Sea glass (teal), Terminal (green on black), Sunset (terracotta), and Berry (plum). Your pick is remembered.

## Good to know

- This opens your saved searches in their real sites. It can't pull the listings into one page: browsers block a page from reading another site's content (a rule called CORS), and LinkedIn's terms forbid scraping. So a launcher is the right shape, and you click through to each site's results.
- LinkedIn's window can be precise to the minute. Google's goes by whole days, since that's all its search phrase understands.
- A link needs to start with `https://`. If you paste or type one without it, the app adds it on save.
- In a sandboxed preview, browser storage and multi-tab opening can be limited. A downloaded or hosted copy behaves normally.

## Running it

Download the file and double-click it, or host it for free on GitHub Pages, Netlify, or Cloudflare Pages. It's plain HTML, CSS, and JavaScript, with no build step and nothing to install.

## License

MIT License. Free to use, copy, modify, and share, just keep the copyright notice.
See the `LICENSE` file, and put your name in the copyright line.
