# StudyBridge

StudyBridge helps students find and apply to colleges in India, Nepal and Bangladesh. A student picks a course, a city and a budget, gets a shortlist of colleges, and can ask a current student or a counsellor for help.

**Live site:** https://studybridge-rosy.vercel.app/

> This is a demo front end. College costs, exchange rates and mentor profiles are sample data, and the counselling form is not connected to a server yet (see [Current limits](#current-limits)).

---

## Features

### College finder
- Filter by country, course, branch, level, city and yearly budget.
- The shortlist updates as each filter changes.
- Every college shows its yearly cost including living, and is marked **Within budget**, **Stretch** (up to 25% over) or **Above budget**.

| Filter | Options |
|---|---|
| Country | India, Nepal, Bangladesh |
| Course | Medical, Engineering, Management, Law, Journalism, Political Science |
| Branch | Depends on the course, for example MBBS, Computer Science, Finance |
| Level | Undergrad, Masters, PhD |
| City (India) | Bangalore, Chennai, Dehradun, Chandigarh, Delhi |
| City (Nepal) | Kathmandu, Pokhara, Biratnagar |
| City (Bangladesh) | Dhaka, Chittagong, Sylhet, Rajshahi |
| Budget | 1,000 to 25,000 USD per year, shown in the chosen currency |

### Currency switch
- Costs can be shown in INR, NPR, BDT or USD.
- Rates are fixed approximations set in `app.js`.

### Mentor connect
- Cards for student mentors, each with their home country, course, city and the topics they can help with.
- **Request a call** fills in the counselling form with the mentor's name.

### Free counselling form
- Collects name, phone or WhatsApp number, home country and what the student wants to study.
- **Ask about this** on any college card fills in the message with that college.

### Information sections
- A comparison of a local agent, a college website and StudyBridge.
- Three steps from plan to campus.
- Nine services grouped as Admission, Money and Arrival.

---

## Current limits

- **Sample data.** The college names are real, but the yearly costs, exchange rates and mentor profiles are placeholders. They must be replaced with verified figures before the site is used with real students.
- **No backend.** The counselling form saves each request in the visitor's own browser (`localStorage`, key `sb-leads`). Nobody receives it.
- **No accounts.** There is no sign-in, application tracking or payment.

---

## Tech stack

- Plain HTML, CSS and JavaScript. No framework and no build step.
- Fonts from Google Fonts: Archivo Black and DM Mono.
- Hosted on Vercel as a static site.

## Project structure

| File | Purpose |
|---|---|
| `index.html` | Page markup: hero, finder, comparison, steps, services, mentors, counselling form |
| `styles.css` | Pinboard design: sticky notes, tape, pins and section tags |
| `app.js` | Sample data, finder filtering, currency conversion, mentor cards and form handling |

## Run it locally

Open `index.html` in a browser. No install is needed.

To serve it over a local address instead:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Editing the data

All data lives at the top of `app.js`:

- `CITIES`: cities per country.
- `COURSES`: branches per course.
- `COLLEGES`: one row per college, as name, country, city, courses, levels and yearly cost in USD.
- `MENTORS`: one row per mentor card.
- `FX`: exchange rates from USD.

## Deployment

The site is deployed on Vercel from this repository with Framework Preset "Other", no build command and the default root directory. It redeploys on every push to `main`.

## Roadmap

1. Connect the counselling form to a backend so requests reach a counsellor.
2. Replace the sample data with verified college fees and real mentor profiles.
3. Add student accounts, a document checklist and application tracking.
4. Add mentor booking and payments.
