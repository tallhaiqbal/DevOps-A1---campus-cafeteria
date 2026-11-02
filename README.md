# Campus Bites — Cafeteria Information Website

A five-page informational website for a fictional university cafeteria. Built with plain HTML5 and one shared CSS file. No JavaScript or backend is used.

## Project structure

```text
Campus-Bites/
├── index.html
├── menu.html
├── specials.html
├── ordering.html
├── feedback.html
├── styles/
│   └── style.css
└── README.md
```

## Run locally

Open `index.html` in a browser. All pages share `styles/style.css` and link to one another through the navigation menu.

## Suggested team responsibilities

| Contributor | Page / task | Suggested feature branch |
|---|---|---|
| Team Lead | Repository setup, shared CSS, integration and review | `main` / `develop` |
| Member 1 | Home page | `feature/home-page` |
| Member 2 | Menu page | `feature/menu-page` |
| Member 3 | Specials page | `feature/specials-page` |
| Member 4 | Ordering page | `feature/ordering-page` |
| Member 5 | Feedback and contact page | `feature/feedback-page` |

If the team has fewer members, one person can take more than one page. Agree on the shared navigation and CSS class names before parallel work begins.

## Git and GitHub workflow

### 1. Team Lead: initialize repository

```bash
mkdir Campus-Bites
cd Campus-Bites
git init
# Add the starter files and folders
git add .
git commit -m "chore: initialize Campus Bites website"
git branch -M main
git remote add origin https://github.com/USERNAME/Campus-Bites.git
git push -u origin main
```

Optionally create a `develop` integration branch:

```bash
git switch -c develop
git push -u origin develop
```

### 2. Each member: clone and create a feature branch

```bash
git clone https://github.com/USERNAME/Campus-Bites.git
cd Campus-Bites
git switch develop
git pull origin develop
git switch -c feature/your-page
```

Work only on the page assigned to you. Keep the common navigation links and stylesheet path consistent with the other pages.

### 3. Commit and push your work

```bash
git status
git add your-page.html
git commit -m "feat: add your page"
git push -u origin feature/your-page
```

Use meaningful commit messages. Examples: `feat: add menu categories`, `style: improve mobile navigation`, `fix: correct page links`.

### 4. Update your feature branch using rebase

Before opening or updating your pull request:

```bash
git fetch origin
git switch feature/your-page
git rebase origin/develop
```

If Git reports conflicts:
1. Run `git status` to identify conflicted files.
2. Open each conflicted file and decide which changes should remain.
3. Remove conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`) and save the file.
4. Stage the resolved files and continue:

```bash
git add path/to/resolved-file
git rebase --continue
```

To cancel the rebase and return to the pre-rebase state:

```bash
git rebase --abort
```

If the feature branch was already pushed, update it after a successful rebase:

```bash
git push --force-with-lease
```

Use `--force-with-lease`, not plain `--force`, and coordinate with the team so nobody else is committing to your feature branch.

### 5. Create a pull request

On GitHub, create a pull request from `feature/your-page` into `develop` (or into `main` if the team is not using `develop`). Include:
- What page or feature you added.
- A short summary of the changes.
- Screenshots if requested by your instructor.
- Confirmation that links and the shared stylesheet work.

Ask another member or the Team Lead to review it. Merge only after approval and after resolving requested changes.

### 6. Keep your local integration branch current

After a pull request is merged:

```bash
git switch develop
git pull origin develop
```

Then create your next feature branch from the updated `develop`.

### 7. Final release

After all five pages are reviewed and tested, merge `develop` into `main` and push:

```bash
git switch main
git pull origin main
git merge --no-ff develop
git push origin main
```

## Final testing checklist

- [ ] All five HTML pages exist and open in a browser.
- [ ] Every page links to all other pages through the navigation.
- [ ] Every page loads `styles/style.css`.
- [ ] Navigation and content are readable on desktop and mobile.
- [ ] No broken links or missing files.
- [ ] No JavaScript or backend dependency is required.
- [ ] Each member's work was submitted through a pull request.
- [ ] Feature branches were updated with rebase where required.
- [ ] Conflicts, if any, were resolved and documented.
- [ ] Final `main` branch contains the reviewed website.

## Notes

The menu, prices, contact details and opening hours are fictional sample content. Replace them if your instructor provides specific details. The feedback page uses an email link rather than a form because this project has no backend to receive form submissions.
