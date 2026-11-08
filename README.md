# Angular Starter Template

A ready-to-use **Angular 17** starter (standalone components) with **Angular Material** and the **Bootstrap 5 grid + utilities** already wired up. Clone it, rename it, and start building.

## What's included

| Feature | Details |
| --- | --- |
| Angular 17.3 | Standalone components, `app.config.ts` + `app.routes.ts` setup |
| Angular Material 17 | `deeppurple-amber` prebuilt theme, async animations (`provideAnimationsAsync`) |
| Typography & icons | Roboto font + Material Icons loaded in `index.html`, `mat-typography` on `<body>` |
| Bootstrap 5.3 | **Grid and utilities only**, imported in `src/styles.scss` (no Bootstrap components/reboot, so it won't clash with Material) |
| Styling | SCSS by default |
| Testing | Karma + Jasmine |

## Prerequisites

- Node.js 18.13+ or 20.9+
- npm
- (Optional) Angular CLI globally: `npm install -g @angular/cli@17`

## Start a new project from this template

### Option A: GitHub "Use this template" (recommended)

1. Open this repo on GitHub and click **Use this template → Create a new repository**.
2. Clone your new repository:
   ```bash
   git clone https://github.com/<your-username>/<new-project>.git
   cd <new-project>
   npm install
   npm start
   ```

### Option B: Clone directly

```bash
git clone https://github.com/saroj8455/starter-template.git my-new-project
cd my-new-project

# Start a fresh git history
rm -rf .git            # PowerShell: Remove-Item -Recurse -Force .git
git init
git add .
git commit -m "Initial commit from starter-template"

npm install
npm start
```

Then open http://localhost:4200/.

## Rename the project

The name `starter-template` appears in a few places. Search and replace it with your project name:

- `package.json`: `"name"`
- `angular.json`: the project key under `"projects"`, plus `"buildTarget"` references such as `starter-template:build:production`
- `src/index.html`: `<title>`
- `README.md`: this file

Tip: search the project for `starter-template` and `StarterTemplate` to catch everything.

## Common commands

| Command | Description |
| --- | --- |
| `npm start` | Dev server at http://localhost:4200 with live reload |
| `npm run build` | Production build into `dist/` |
| `npm run watch` | Development build in watch mode |
| `npm test` | Run unit tests with Karma |
| `ng generate component features/my-page` | Create a standalone component |
| `ng generate service core/services/api` | Create a service |

## Using Angular Material

Components are standalone, so import the Material modules you need right in the component:

```ts
import { Component } from '@angular/core';
import { MatButtonModule } from '@angular/material/button';
import { MatIconModule } from '@angular/material/icon';

@Component({
  selector: 'app-example',
  standalone: true,
  imports: [MatButtonModule, MatIconModule],
  template: `
    <button mat-raised-button color="primary">
      <mat-icon>home</mat-icon> Home
    </button>
  `,
})
export class ExampleComponent {}
```

**Changing the theme:** in `angular.json`, replace `@angular/material/prebuilt-themes/deeppurple-amber.css` (in both the `build` and `test` `styles` arrays) with another prebuilt theme, such as `indigo-pink.css`, `pink-bluegrey.css` or `purple-green.css`, or with your own custom SCSS theme.

## Using the Bootstrap grid and utilities

Only `bootstrap-grid` and `bootstrap-utilities` are imported (see `src/styles.scss`). You can use the layout and spacing classes:

```html
<div class="container">
  <div class="row g-3">
    <div class="col-12 col-md-6 p-2">Left</div>
    <div class="col-12 col-md-6 p-2 d-flex justify-content-end">Right</div>
  </div>
</div>
```

To use full Bootstrap (buttons, cards, and so on), replace those imports with `@import "bootstrap/scss/bootstrap";`. Expect some style overlap with Material.

## Project structure

```
src/
├── app/
│   ├── app.component.*      # Root component
│   ├── app.config.ts        # App providers (router, animations)
│   └── app.routes.ts        # Route definitions
├── assets/                  # Static assets
├── index.html               # Fonts, Material Icons, mat-typography
├── main.ts                  # Bootstrap entry point
└── styles.scss              # Global styles + Bootstrap grid/utilities
```

## Suggested first steps in a new project

1. Rename the project (see above).
2. Replace the placeholder in `src/app/app.component.html` with your layout, for example a `mat-toolbar` and `<router-outlet />`.
3. Add routes in `src/app/app.routes.ts`.
4. Pick your Material theme.
5. Update this README for your project.

## Further help

- [Angular docs](https://angular.dev)
- [Angular Material components](https://v17.material.angular.io/components/categories)
- [Bootstrap grid](https://getbootstrap.com/docs/5.3/layout/grid/) and [utilities](https://getbootstrap.com/docs/5.3/utilities/api/)
