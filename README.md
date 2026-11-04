# Todo App

A TypeScript todo app for the KW and TBMH exams.

Based on the
[starter project by Kristian Wittrup](https://github.com/kristian-wittrup/2024-todo-TS-app-bde).

Website address after the first successful deployment:

https://olga-pas-easv.github.io/todo-typescript-exam/

## Features

- Add, edit and remove tasks.
- Mark tasks as completed or active.
- Filter tasks by All, Active and Completed.
- Show task completion progress.
- Save tasks in Local Storage.
- Change the page background colour.

Tasks are saved in the current browser. They are not shared between devices.

## Tools

TypeScript, Vite, HTML and CSS. Vitest for unit tests and TestCafe for browser
tests. GitHub Actions for automated checks and deployment.

## Run locally

Use Node.js 22, which is also used in GitHub Actions.

Install dependencies:

```bash
npm ci
```

Start the app:

```bash
npm run dev -- --port 5173 --strictPort
```

Open http://localhost:5173.

## Build

```bash
npm run build
```

The built files are saved in the dist folder.

## Unit tests

Check the progress calculation:

```bash
npx vitest run src/progress.test.ts
```

The five tests cover an empty list, no completed tasks, half completed tasks,
all completed tasks and rounding.

## Browser tests

Start the app using the command above. Keep it running and open a second
terminal:

```bash
npx testcafe chrome "test/*.js"
```

Google Chrome must be installed.

The eight tests cover task completion, filters, progress and Local Storage.

## GitHub workflow

Work is tracked with Issues and developed in separate branches. Pull requests
bring changes into develop. A release branch prepares the app for main.

GitHub Actions runs the build, unit tests and browser tests for pull requests
into develop and main, and for pushes to these branches.

## Deployment

The deployment workflow publishes the app to GitHub Pages after changes reach
main. It runs the build and tests before publishing.

Website address after the first successful deployment:

https://olga-pas-easv.github.io/todo-typescript-exam/
