# 📝 Quick Notes

A simple, lightweight notes app built with **vanilla HTML, CSS, and JavaScript**. Create, edit, and delete notes right in your browser. Everything is saved locally, so your notes are still there when you come back.

> 🎓 **This is a learning project.** It was built to practice core front-end fundamentals, so the design is intentionally simple and there are known security limitations (see [Known Issues](#-known-issues--limitations)).

🔗 **Live Demo:** [YOUR_LIVE_LINK_HERE](YOUR_LIVE_LINK_HERE)

---

## ✨ Features

- **Add notes**: create a note with a title and content through a modal dialog
- **Edit notes**: update any existing note; the dialog is pre-filled with its content
- **Delete notes**: remove a note with one click
- **Persistent storage**: notes are saved in the browser's `localStorage`
- **Dark / Light theme**: toggle between themes; your choice is remembered
- **Responsive grid layout**: note cards adapt to the screen size
- **Empty state**: a friendly message and call-to-action when there are no notes
- **Quality-of-life details**: hover actions on cards, click outside the dialog to close it, auto-focus on the title field

---

## 🧠 How It Works

The app has three small parts:

| File | Responsibility |
| --- | --- |
| `index.html` | Page structure: header, notes container, and the `<dialog>` used for adding/editing notes |
| `style.css` | Styling, CSS variables for theming (light/dark), grid layout, and the dialog design |
| `app.js` | App logic: state, rendering, CRUD operations, theme handling, and `localStorage` persistence |

**Flow:**

1. On page load, notes are read from `localStorage` into an in-memory `notes` array.
2. `renderNotes()` turns that array into note cards (or the empty state).
3. Adding or editing opens the native `<dialog>` element. On submit, the `notes` array is updated, saved to `localStorage`, and re-rendered.
4. Deleting filters the note out of the array, then saves and re-renders.
5. The theme toggle switches a `dark-theme` class on `<body>`. Colors are driven by CSS variables, and the choice is stored in `localStorage`.

---

## 🛠️ Tech Stack

- HTML5 (including the native `<dialog>` element)
- CSS3 (Grid, Flexbox, CSS variables, transitions)
- Vanilla JavaScript (ES6+)
- Browser `localStorage`
- [Poppins](https://fonts.google.com/specimen/Poppins) font via Google Fonts

---

## 🚀 Getting Started

No build tools or dependencies required.

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# 2. Go into the project folder
cd YOUR_REPO_NAME

# 3. Open index.html in your browser
```

You can also use a local server such as the VS Code **Live Server** extension.

### 🌐 Deploy with GitHub Pages

1. Push the project to a GitHub repository (make sure `index.html` is in the root folder).
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`.
4. Choose the `main` branch and the `/ (root)` folder, then click **Save**.
5. After a minute or so, your site will be live at `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`.

---

## 📁 Project Structure

```
quick-notes/
├── index.html
├── style.css
├── app.js
└── README.md
```

---

## ⚠️ Known Issues & Limitations

This project is for learning, so please don't treat it as production-ready:

- **XSS vulnerability**: note titles and content are inserted using `innerHTML` without sanitization, so malicious HTML/JS typed into a note could be executed. A fix would be using `textContent` or escaping user input before rendering.
- **Inline event handlers**: `onclick="..."` attributes are used in the HTML templates, which is not best practice (event delegation would be cleaner).
- **Simple ID generation**: IDs use `Date.now()`, which could collide in rare cases.
- **Local-only storage**: notes live only in your browser, with no sync across devices and no backup.
- **Basic design**: the UI is intentionally minimal.

---

## 🔮 Future Improvements

- [ ] Fix the XSS vulnerability (sanitize/escape user input)
- [ ] Replace inline handlers with event listeners / event delegation
- [ ] Search and filter notes
- [ ] Tags or categories
- [ ] Better, more polished UI/UX
- [ ] Export / import notes
- [ ] Backend or cloud sync

---

## 🙏 Acknowledgements

Inspired by the tutorial content from **[Coding2Go](https://www.youtube.com/@coding2go)**. Thank you for the great learning resource!

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

Made with ☕ while learning. Feedback and suggestions are welcome!
