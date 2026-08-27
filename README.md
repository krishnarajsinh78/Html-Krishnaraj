# School Bookstore Survey

A simple HTML survey form for collecting student feedback on book-buying habits, intended for use by a school bookstore.

## Overview

This is a static HTML page (`index.html`) containing a form that collects basic respondent information along with their preferences and habits related to buying books.

## Features

- **Basic Information section**
  - Name
  - Address
  - City
  - ZIP Code
  - Email

- **Survey Questions section**
  1. Preferred place to buy books (radio buttons): School Bookstore, Local Bookstore, Online Store, Friends/Relatives, Other
  2. Frequency of buying books (dropdown): Daily, Weekly, Monthly, Yearly
  3. Types of books usually bought (checkboxes): Textbooks, Fiction, Spiritual, Autobiography, Other
  4. Typical amount spent on books (radio buttons): <₹500, ₹500–₹1000, ₹1000–₹2000, above ₹2000
  5. Main reason for choosing a place to buy books (dropdown): Variety, Low Price, Convenient Location, Other
  6. Open-ended suggestions for the school bookstore (textarea)

- Submit and Reset buttons

## Usage

1. Open `index.html` in any web browser.
2. Fill out the form fields.
3. Click **Submit Survey** to submit (note: the form currently has no `action`/`method` attribute or backend, so submission needs to be wired up — see Known Issues).

## Known Issues / Suggested Fixes

- The `<form>` tag has no `action` or `method` attribute, so submissions won't go anywhere yet. Add a backend endpoint or a service like Google Forms/Formspree to actually collect responses.
- The **Address** input incorrectly reuses `id="name"` and `name="name"` (duplicate of the Name field). This should be changed to `id="address"` / `name="address"` to match its label and avoid conflicting with the Name field.
- The `<label1>` tag used throughout is not a valid HTML element — it should be `<label>`.
- The `<br></br>` self-closing pattern is invalid HTML for `<br>`, which is a void element; use `<br>` alone.
- The "Online Store" radio button's `id` contains a space (`id="online store"`), which is invalid; its `label for="online"` also doesn't match. Use a matching, space-free id (e.g. `id="online"`).
- Several `id`/`name`/`value` attributes contain spaces or inconsistent casing (e.g. `less 500`, `5001000`), which should be normalized (e.g. `less-than-500`, `500-1000`) for cleaner data handling.
- Duplicate `id="other"` is used for both the "buy_place" and "book_type" checkbox/radio options — IDs must be unique across the page.
- Typos: "Basic Infomations" → "Basic Information", "Spritual" → "Spiritual", "frecuency" → "frequency".

## File Structure

```
.
└── index.html   # The survey form
```

## License

No license specified — for internal/school use.
