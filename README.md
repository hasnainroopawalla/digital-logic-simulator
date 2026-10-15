# ⚡️ Flux — Digital Logic Simulator

A fast, playful digital-circuit sandbox.

Visually build logic circuits, compose custom chips, and experiment freely in real time. Save your designs as blueprints, share them with friends, or grow your own library of reusable components.

<p align="center">
    <img src="assets/latch.png" alt="SR LATCH"/>
</p>

## 🚀 Live demo

http://hasnainroopawalla.github.io/flux

## 🛠️ Quick Start

### Tech Stack

- TypeScript
- React + Vite + Tailwind CSS
- WebGPU (custom render engine)

### Instructions

Requires Node.js 22.13+ (22.x) or 24+, and npm 11+.

Run all commands from the repository root.

1. Install dependencies:

```bash
npm install
```

2. Run the app:

```bash
npm run dev
```

`npm start` is also available as an alias.

### Repository structure

This repository uses npm workspaces with one shared `package-lock.json`:

```text
apps/
  web/            React + Vite application
packages/
  render-engine/  WebGPU rendering
  shared-types/   Shared TypeScript types
  simulator/      Circuit simulation
```

### Commands

| Command             | Description                                           |
| ------------------- | ----------------------------------------------------- |
| `npm run dev`       | Start the web app's development server                |
| `npm run build`     | Build the web app into the root `dist/` directory     |
| `npm run preview`   | Build and preview the production app locally          |
| `npm test`          | Run tests across all workspaces once                  |
| `npm run lint`      | Run Biome lint and formatting checks                  |
| `npm run typecheck` | Check every workspace and the root test configuration |

Use `npm ci` for reproducible installs from the committed lockfile, as CI does.
To target a workspace, use commands such as
`npm run test --workspace=@digital-logic-sim/simulator`.

### Workspace tooling

- TypeScript and Vitest are shared development tools installed at the root.
- Workspaces extend `tsconfig.base.json` and provide their own `typecheck` scripts.
  Checks cover source files, public entry points, and tests; the web app also
  checks its Vite and Vitest configuration.
- Tests use Vitest globals. Web tests run in jsdom with React Testing Library,
  Vitest-compatible DOM matchers, and cleanup configured in `apps/web/tests/setup.ts`.
- Library workspaces expose their TypeScript entry points through `exports` and
  `types`. They are private, source-only packages consumed by Vite, not standalone
  JavaScript distributions.

## 📦 Blueprints

Looking for inspiration?
Check out the [/blueprints](https://github.com/hasnainroopawalla/flux/tree/master/packages/simulator/src/blueprints) directory to explore a growing collection of prebuilt circuits—from simple logic gates to more complex compositions.

You can load these blueprints directly into the simulator, modify them, or use them as a starting point for your own designs.

## 🧩 Contributing

- Found a bug or have a feature idea? Open an issue on GitHub: https://github.com/hasnainroopawalla/digital-logic-simulator/issues
- To contribute: fork, make changes on a branch, and open a pull request against `master`.

## 📄 License

- This project and all workspaces are licensed under the MIT License — see
  [LICENSE](./LICENSE) for details.
