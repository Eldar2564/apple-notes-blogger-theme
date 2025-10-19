# AppleNotes Blogger Theme (applenotes.xhtml)

This repository contains a single Blogger theme template file: `applenotes.xhtml` by @muddassirhq. An Apple Notes Inspired custom theme for blogger.com / A rare find in this era ;)

## why did I create this?

Blogger.com is the first platform I was introduced to the world of web development. It was my desire to create a custom theme from past 10 years, finally I was able to do, credits to God.

It also serves as a proof of concept that how blogger.com site can be (minimally?) beautiful, if not modern, enough for a individual blogger who just wants to blog old school, someone who is not concerned about earning money through wrting online and just wants to blog old school or maintain a digital garden.

## What this file is

`applenotes.xhtml` is a complete Blogger (XML/XHTML) theme template designed to emulate an Apple Notes-like interface for a Blogger blog. It uses Blogger template tags (`<b:...>`) and includes CSS (inside a `<b:skin>` block) that implements a three-column layout: a left sidebar (folders/labels), a middle notes list, and a main editor/view area.

The template is intended to be uploaded to Blogger (https://www.blogger.com) as a theme (template) XML file.

## Features

- Responsive three-column layout (sidebar / notes list / editor)
- Styled components for folders, notes list, and editor with modern system fonts
- Mobile responsive behaviours: collapses columns on smaller screens
- Uses Blogger widgets such as `Label` and `BlogArchive` and built-in `<b:widget>` sections for posts & comments
- Ready-made UI components (buttons, icons, search input, empty state)

## Installation (Upload to Blogger)

1. Sign in to your Blogger account and go to the blog you want to use.
2. In the left menu choose `Theme`.
3. Click the three-dot menu (⋮) near the top-right of the theme preview and choose `Restore` (or the "Backup/Restore" option).
4. Use the `Upload` option to upload `applenotes.xhtml` or paste its contents into the theme editor.
5. Save and apply the theme.

Notes:
- Backup your current theme before restoring a new one.
- Blogger expects an XML/XHTML theme file. Ensure the file encoding is UTF-8.

## Customization

Key places to customize in `applenotes.xhtml`:

- Theme colors and fonts: edit the `<b:skin>` CSS block near the top of the file. Example variables you can change:
  - `background` and `color` under `body`
  - `.notes-header` background color (currently `#FFCC00`)
  - Sidebar borders and button colors
- Layout widths: `.container` uses `grid-template-columns: 280px 360px 1fr;`. Adjust the widths to suit your content.
- Widget display: The template includes Blogger widgets (`Label`, `BlogArchive`, `Blog` widget). Modify or remove `<b:widget>` sections if you don't want specific widgets.
- Post metadata and settings: Within the `<b:widget id='Blog1'>` section there are multiple `<b:widget-setting>` tags that control blog behaviour (show timestamp, comments, author, etc.). Change as needed.

## Important CSS classes

- `.container` — top-level grid wrapper
- `.sidebar` — left column wrapper
- `.notes-section` — middle notes list area
- `.editor-section` — right editor/post view area
- `.folder-item`, `.note-item`, `.note-item-content` — list items and hover/active states
- `.btn-toolbar`, `.btn-new-folder` — buttons used in toolbar and footer

## Mobile behaviour

- Breakpoints are provided at 1024px and 767px. At smaller widths the sidebar hides and columns collapse into a single column layout. There are helper classes `.mobile-visible` used to control which sections show on small screens.

## Troubleshooting

- Blank or broken layout after upload: make sure the file encoding is UTF-8 and that you uploaded the entire file contents. Blogger can be sensitive to invalid XML/HTML introduced when pasting.
- CSS not applying: The template uses a `<b:skin>` block which Blogger converts to the theme stylesheet — ensure you did not accidentally remove or truncate it when editing.
- Widgets missing: Verify the `<b:section>` and `<b:widget>` blocks were preserved during edits. Some editors strip `b:` namespaced tags.

## License & Credits

This file is provided as-is. Modify and use it for personal or commercial projects. If you redistribute or publish a theme based on this template, please include appropriate attribution if required.

## Where to go next

- Edit colors and spacing in `<b:skin>` to match your branding.
- Remove or add Blogger widgets via the `Theme` -> `Customize` UI after applying the template.

---

File: `applenotes.xhtml` — last saved with this repository. If you want, I can also:

- Extract the inline CSS into a separate `styles.css` and update the template to reference it (Blogger requires inline skin sections, so this would be for local development only).
- Add a minimal `preview.html` that renders the static layout outside Blogger for design tweaks.

## License

This project is licensed under the GNU General Public License v3.0 (GPL-3.0). By using or contributing to this repository you agree that derivative works and distributions of this theme remain compatible with the GPLv3 terms.

Full license text: https://www.gnu.org/licenses/gpl-3.0.en.html

If you redistribute a modified version of the theme, please include a copy of the GPLv3 license and retain this copyright notice.

## Contributing

Contributions, issues, and pull requests are welcome! If you'd like to help, here are some ways to get involved:

- Report bugs or suggest features by opening an issue.
- Send pull requests for fixes, features, or improved documentation.
- Improve accessibility and responsive behaviors.
- Add UI to expose the comment system and comment controls to users (see note below).

Preferred workflow:

1. Fork the repository.
2. Create a feature branch (e.g., `feature/comment-ui`).
3. Commit your changes and open a pull request describing the change.

Please keep changes focused and include a short description and screenshots (if relevant) in your PR.

## Note: Comment system UI

Currently the comment system is present in the template (comment include blocks and iframe hooks are included), but the comment controls and composer are not exposed via a visible UI in the editor view. This was left intentionally minimal and requires contribution to:

- Surface the comment composer and comment list in the editor UI for desktop & mobile.
- Add toolbar controls for moderating (delete/edit) comments for authenticated blog admins.
- Ensure the comment iframe and threaded comment scripts load safely and gracefully when comments are disabled or blocked by browser settings.

If you want to tackle this, consider editing the `<b:includable>` blocks for `comment-form`, `comments`, and `threaded_comments` in `applenotes.xhtml` and adding the UI elements in the `.editor-footer` or `.editor-inner` areas. Tests or a simple local preview will help reviewers.

# Special thanks

There are some resources I want to mention which helped me in writing code for this 15 year old platform.

https://support.google.com/blogger/answer/176245?hl=en&ref_topic=6321969&sjid=10366444348212617623-NC (official help page)
https://www.youtube.com/watch?v=hyWLsqdsuoY (Just Part 1, it has 3 more videos)
https://github.com/livebloggerofficial/Custom-Blogger-Theme (source code of the youtube tutorial)
https://bloggercode.orbiona.com/ (Maybe this person was/is a developer of blogger.com, this website is the bible of blogger.com syntax)
