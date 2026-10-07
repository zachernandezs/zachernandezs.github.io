# Dotdesk

A dot-matrix pin board for organizing your day, with floating widgets and a bridge to Obsidian. It's a single HTML file with no build step and no server.

## What's on the desk

- **Pin board.** Draw with a pen or highlighter, write text, and pin post-its and Markdown cards. Pan by dragging, zoom with Ctrl + scroll.
- **Desks.** Add more boards with the **+** in the left bar. Each desk has its own name and accent color.
- **Notepad.** Write in Obsidian-flavored Markdown, including tasks, `[[links]]`, highlights, tags and callouts. From here you can append to today's daily note, save a new note, or open any note in your vault.
- **Pomodoro.** Set your own focus and break lengths and pick one of four chimes.
- **Tasks.** Daily, weekly and bi-weekly lists that reset on their own when the period rolls over.
- **Day plan.** Block out your day in half-hour slots by dragging on the timeline.
- **Clock and calendar.** Days that have a daily note get a dot, and clicking a day opens its note.

## Publish it on GitHub Pages

1. Put `index.html` (and this README) in a repository.
2. In the repository, open **Settings → Pages**, choose **Deploy from a branch**, then pick your branch and the `/ (root)` folder.
3. Open `https://<your-user>.github.io/<repository>/`.

You can also just open `index.html` from your computer.

## Where your data lives

Everything you add is stored in your own browser's local storage. Nothing is uploaded anywhere. The only exception is that when you connect Obsidian, Dotdesk talks to Obsidian on your own computer (`127.0.0.1`). Visitors to the published page only ever see the example content.

Each browser, and each address (the local file and the GitHub Pages URL count separately), keeps its own copy. To move your desks, notes and tasks, use **Settings → Export backup** in one place and **Import backup** in the other.

## Connecting Obsidian

Click the gem in the left bar.

| Browser | How it connects |
| --- | --- |
| Chrome, Edge, Opera | **Vault folder**: pick your vault's top folder and Dotdesk reads and writes it directly. The Local REST API also works. |
| Firefox, Safari | **Local REST API plugin**, since these browsers can't open folders from a web page. |

### Local REST API setup

1. In Obsidian, open **Settings → Community plugins**, install **Local REST API** (by Adam Coddington) and turn it on.
2. Copy the **API key** from the plugin's settings.
3. The plugin serves `https://127.0.0.1:27124` with a self-signed certificate. Open that address in a new tab once and accept the warning (in Firefox: **Advanced → Accept the Risk and Continue**). Alternatively, turn on the plugin's non-encrypted server and use `http://127.0.0.1:27123`.
4. In Dotdesk, open **Settings**, choose **Local REST API plugin → Set up**, paste the key and click **Connect**.
5. If the browser asks whether the page may reach apps or services on your device, choose **Allow**.

The plugin keeps Obsidian's own settings folder private by default, so check that **Daily notes folder** and **Daily note format** in Dotdesk's settings match your Daily notes settings in Obsidian. Obsidian has to be open while you use the connection.

Without a connection, Dotdesk sends notes to Obsidian through `obsidian://` links, so the Obsidian app opens and adds the text itself.

## Keyboard shortcuts

| Keys | Action |
| --- | --- |
| V · P · H · E · T · N · C | Select · pen · highlighter · eraser · text · post-it · card |
| 1–7 · [ ] | Ink color · smaller / bigger |
| Space + drag, Ctrl + scroll | Pan, zoom |
| Ctrl+Z · Ctrl+Shift+Z | Undo · redo |
| Alt+1 … Alt+5 | Notepad, Pomodoro, tasks, day plan, clock |
| Alt+P | Start or pause the Pomodoro |
| Alt+↑ · Alt+↓ | Previous · next desk |
| Ctrl+Enter · Ctrl+S | In the notepad: append to today's note · save |

## Credits

- Fonts: [Poppins](https://fonts.google.com/specimen/Poppins), [Caveat](https://fonts.google.com/specimen/Caveat) and [JetBrains Mono](https://www.jetbrains.com/lp/mono/), all under the SIL Open Font License 1.1, embedded in the file.
- Icons adapted from [Lucide](https://lucide.dev) (ISC License).
- Obsidian integration through the [Local REST API](https://github.com/coddingtonbear/obsidian-local-rest-api) community plugin.