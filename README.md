# Intelligent Registration System


> A polished, responsive registration form built with plain HTML, modern CSS, and vanilla JavaScript. Focused on UX: inline validation, password strength meter, dependent country/state/city selects and an accessible layout.

---

## ✨ Highlights (what makes it attractive)

* **Beautiful UI**: soft glassy card, subtle gradient background and gentle shadows.
* **Progressive validation**: errors only show after user interaction or attempt to submit — friendly and non-intrusive.
* **Smart UX**: auto-format DOB, age auto-calculation, country → state → city cascading selects, country code auto-update.
* **Password strength meter** and confirm-password checks.
* **No build tools** — drop the files on any static host (GitHub Pages, Netlify) and it works.

---

## 🔧 Files in this repo

* `index.html` — the complete registration page (HTML, inline CSS, and JS).
* `README.md` — (this file) usage notes and customization tips.
* `LICENSE` — MIT license (optional).

---

## 🚀 Quick demo (run locally)

1. Clone the repo:

```bash
git clone https://github.com/<your-username>/intelligent-registration.git
cd intelligent-registration
```

2. Open `index.html` in your browser (double-click or run a local server):

```bash
# simple python server
python -m http.server 8000
# then open http://localhost:8000 in your browser
```

3. Try the form: choose a country, state, city and fill required fields.

---

## 🧩 Main features & behavior

* **Required field handling** — shows friendly messages next to fields when user touches them or tries to submit without completing.
* **Disposable email blocking** — blocks a small list of throwaway domains.
* **Phone validation** — country-aware validation (`+91` expects 10 digits starting 6–9; `+1` expects 10 digits).
* **DOB auto-format** — formats to `YYYY-MM-DD` while typing and calculates age.
* **Password strength meter** — visually shows strength and enforces minimum length.
* **Reset behavior** — clears touched state, hides errors and resets meter.

---

## ♿ Accessibility & UX

* Form uses semantic inputs and labels (screen-reader friendly).
* Error text is placed directly after the related control for easier navigation with assistive tech.
* Large hit targets and clear focus styles help keyboard users.

---

## 🎨 Customization tips

* **Colors & theme**: tweak CSS `:root` variables at top of the stylesheet (`--bg-start`, `--bg-end`, `--accent`, etc.).
* **Add more countries/states**: edit the `locationData` object in the script.
* **Validation rules**: modify regex patterns in the JS validators to match your rules.
* **Server integration**: replace the fake `setTimeout` submission with a `fetch()` POST to your API endpoint.

---

## ✅ Example: quick attach point for server (pseudo)

> Replace the `setTimeout` in the `submit` handler with a `fetch` call. Example (pseudo):

```js
// gather payload
const payload = {
  firstName: document.getElementById('firstName').value.trim(),
  lastName: document.getElementById('lastName').value.trim(),
  email: document.getElementById('email').value.trim(),
  // ... more fields
};

fetch('https://api.yoursite.com/register', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify(payload)
})
.then(r => r.json())
.then(res => { /* show success */ })
.catch(err => { /* show error */ });
```

---

## 🧪 Testing & QA suggestions

* Test phone validation by switching countries and entering non-digit characters.
* Test DOB edge cases (future dates, extreme ages).
* Try disabling JS — the form still renders; consider server-side validation for security.

---

## 🙌 Contribution

Feel free to open issues or PRs. Small ideas:

* Add locale-based date picker.
* Extract CSS into a separate `styles.css` and add theming toggle (light/dark).
* Replace manual location data with a remote API.

---

## 📜 License

This repository is free to use under the **MIT License** — see `LICENSE`.

