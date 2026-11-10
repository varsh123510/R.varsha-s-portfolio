# Varsha Rajmohan · Portfolio

Live: https://r-varsha-s-portfolio.vercel.app/
Recruiter link (everything on one page): https://r-varsha-s-portfolio.vercel.app/#quick

Same "drive through" site as before, now driven by **data.json**. You never edit `index.html` to add things.

## Folder
```
index.html      the site (design + code)
data.json       ALL the content: profile, internships, projects, wins, research, certificates
images/         profile.jpg
certificates/   certificate images
sitemap.xml, robots.txt   for Google
```

## Add something new (3 steps)
1. Drop the image into `certificates/`. Use a simple name with no spaces, e.g. `aws-cloud-practitioner.jpg`.
2. Open `data.json` and copy an existing entry in the right list, then change the text.
3. Commit and push to GitHub. Vercel redeploys in about a minute.

### Examples
New certificate (list: `certificates`). `kind` must be one of: Internship, Training, Course, Prize, Research, Hackathon, Event (or a new word, which creates a new filter button):
```json
{ "title": "AWS Cloud Practitioner", "issuer": "Amazon Web Services", "date": "Dec 2026",
  "kind": "Course", "note": "Credential ID ABC123", "image": "certificates/aws-cloud-practitioner.jpg" }
```
New internship (list: `experience`, sorted newest-first automatically; `type` is Internship or Training):
```json
{ "role": "Software Engineer Intern", "org": "Company name", "type": "Internship",
  "start": "2027-01-05", "end": "2027-03-31",
  "summary": "One or two lines on what you built.", "tags": ["React", "Node.js"],
  "certificate": "certificates/company-internship.jpg" }
```
New project (list: `projects`). A green **Live demo** and a **Preview** button appear when `demo` is filled; a **Code** button when `code` is filled. `category` creates the filter buttons:
```json
{ "name": "My App", "category": "Web apps", "tag": "React · API",
  "summary": "What it does in one or two lines.", "stack": ["React", "Firebase"], "badge": "",
  "links": { "demo": "https://my-app.vercel.app", "code": "https://github.com/varsh123510/my-app" } }
```
New prize or hackathon (list: `wins`). Add `"rank"` (1st, 2nd, Winner, Finalist…) to show it as a big card; leave it `""` to list it under Hackathons & ideathons.

- Paper ISBN: fill `"isbn"` in the first `research` entry and it appears on the paper card.
- Résumé: put `resume.pdf` in the folder and set `"resume": "resume.pdf"` in `profile`. A Résumé button appears.
- Numbers in `stats` like `{internships}`, `{projects}`, `{certificates}` count themselves.
- Empty fields (`""`) are hidden on the page.

## Preview on your computer
Double-clicking `index.html` will not load `data.json` (browsers block it). In VS Code, install "Live Server", right-click `index.html` → Open with Live Server.

## Get found on Google
1. Google Search Console → Add property → URL prefix → `https://r-varsha-s-portfolio.vercel.app/`.
2. Verify with "HTML tag": paste the tag Google gives you into the `<head>` of `index.html`, push, then click Verify.
3. Sitemaps → submit `sitemap.xml`. Then URL Inspection → paste the home URL → Request indexing.
4. Put the link in LinkedIn (Featured + Contact info) and in the GitHub profile bio. Those links help Google find the site sooner.
Indexing usually takes a few days to two weeks.
