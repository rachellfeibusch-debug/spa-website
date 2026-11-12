# Prompts for Claude Code

These are the guide's Part 3 prompts, adapted for this site. Paste them into Claude Code one at a time, after `cd ~/GitHubRepos/spa-website` and `claude`.

## Step 1: plan first (guide 3.2)

```
This folder is a project to rebuild the Strategic Pause Advisory website,
replacing an existing Wix site. Read CLAUDE.md first, then content/spa-website.md
for all the copy, and look at /images, /fonts, /files and brand/SPA Brand Guidelines.
Before building anything: (1) tell me how you'd structure and style the site,
including the home page layout, (2) propose which images go on which page,
(3) list every TODO in the content file and anything else you need from me.
Don't write any files yet.
```

Read the plan and answer its questions.

## Step 2: build (guide 3.3)

```
Now build it as a multi-page responsive static website using HTML and CSS,
following CLAUDE.md exactly: the page addresses, the brand colours and fonts,
and the logo rules. It must look great on both mobile phones and desktop computers.
There is no contact form. The "Book a call" button goes to Calendly.
Keep all images referenced from the /images folder. When you've finished,
open the home page in my browser.
```

## Step 3: review (guide 3.4)

Check every page on desktop and with the window dragged narrow. Then ask for changes in plain English. For example:
- "Make the hero taller on desktop."
- "Swap the images on About and Services."
- "Use the Calendly embed on the Contact page instead of a button."

## Step 4: before going live (guide Part 6)

```
Check every page for broken links and missing images, check that every page
has a unique title, meta description and Open Graph tags, and make sure
sitemap.xml lists all the page addresses on https://www.strategicpauseadvisory.com.
```
