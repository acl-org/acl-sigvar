This code is extremely heavily based on [Maruan Al-Shedivat](https://maruan.alshedivat.com/)'s [al-folio](https://github.com/alshedivat/al-folio) theme, which is based on [Lia Bogoev](https://liabogoev.com)'s [\*folio theme](https://github.com/bogoli/-folio).
All of these themes are available as open source under the terms of the [MIT License](https://github.com/alshedivat/al-folio/blob/master/LICENSE).

## Updating this website

### Building the website locally

Changes pushed to the main branch of this repo will automatically appear on the website (unless they break something or there is a more general problem with the deployment).

In order to preview changes locally, you need to first [install Jekyll](https://jekyllrb.com/docs/installation/), clone this repo, and install the required Ruby Gems (`bundle install`).
Then you can generate a preview via `bundle exec jekyll serve` ([http://127.0.0.1:4000](http://127.0.0.1:4000)).
The local preview is automatically updated when you update make changes to (most) files (except `_config.yml` or the install Gems).

### Adding SIGVAR pages

Create a new markdown file in `_pages`. It should start with a header such as:
```
---
layout: page
permalink: /insert-page-link
title: Insert Page Title
nav: true
nav_order: 3
---
```
If the page should show up in the navigation bar, set `nav: true` and update `nav_order` according to where it should appear. You might need to edit the `nav_order` values for other pages.


### Adding/updating workshop pages

Create a subfolder in `_pages` for the workshop (e.g., `vardial2027`). Within this folder, create a file (e.g., `dropdown.md`) that looks like this:
```
---
layout: page
title: VarDial 2027
nav: true
nav_order: 5
dropdown: true
children:
  - title: About
    permalink: /vardial2027
  - title: Programme
    permalink: /vardial2027/programme
  - title: Call for Papers
    permalink: /vardial2027/cfp
  - title: Shared Task
    permalink: /vardial2027/shared-task
  - title: Programme Committee
    permalink: /vardial2027/programme-committee
---
```
Update the values accordingly (including `nav_order`).
The `title`s in this file are the navigation bar entries that will be shown in the dropdown menu for the workshop.
The `permalink`s need to match the permalinks you set for the individual pages.
Any entry in the list of `children` needs to have its own markdown page.

Create a `home.md` file for the workshop, e.g.:
```
---
layout: page
title: About VarDial 2027
permalink: /vardial2027
subtitle:
---

(Insert general workshop info here.)
```
The `title` here is the page title shown in, e.g., the browser tab (and not the dropdown entry title).

Likewise, create the other workshop-related pages, e.g.:
```
---
layout: page
title: CfP (VarDial 2027)
permalink: /vardial2027/cfp
subtitle:
---

(Insert CfP here.)
```

The CfP should be in accordance with the [ethical considerations](https://aclsigvar.org/constitution#ethical-considerations) in SIGVAR's constitution.

Any page that should appear in the dropdown bar needs to be listed in `dropdown.md`.
The filename does not technically need to match the permalink or the title in the dropdown menu, but it makes managing the website a bit easier.

Once the general workshop website is set up, you can announce it in the news section of the SIGVAR start page (`_pages/home.md`) and in the list of SIGVAR-affiliated events (`_pages/events.md`)

To remove an old workshop from the navigation bar, set `nav: false` in the corresponding `dropdown.md` file.
Make sure the main page (e.g., `/vardial2027`) is linked in SIGVAR's list of events (`_pages/events.md`), and that all subpages (e.g., `/vardial2027/cfp`) are linked on the Workshop's main page, so that the information on this workshop remains findable.
