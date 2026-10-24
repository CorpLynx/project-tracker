# project-tracker

A static GitHub Pages site that tracks how far along each of my projects is.

Live at <https://corplynx.github.io/project-tracker/>.

## Updating it

All the data is in [`projects.json`](projects.json). Each project has a list of milestones, and each
milestone has a `state` of `todo`, `doing` or `done`. Completion is done milestones plus half of the
in-progress ones, divided by the total.

You can edit the file directly, or:

1. Open the live page and click the milestone boxes to change their state. The edits are saved in
   your browser only.
2. Click **Export projects.json** in the banner that appears.
3. Replace `projects.json` in this repo with the downloaded file and push.

Last-pushed dates and stars come from the public GitHub API when the page loads, so only public repos
show activity.

## Running it locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Opening `index.html` straight from disk won't work, because the browser blocks `fetch("projects.json")`
on `file://` URLs.
