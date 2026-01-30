# skills-npm

[![npm version][npm-version-src]][npm-version-href]
[![npm downloads][npm-downloads-src]][npm-downloads-href]
[![bundle][bundle-src]][bundle-href]
[![JSDocs][jsdocs-src]][jsdocs-href]
[![License][license-src]][license-href]

A CLI that discovers [agent skills](https://agentskills.io) shipped inside npm packages and creates symlinks for coding agents (Cursor, Claude Code, Codex, etc.) to consume.

## Why?

Current skill distribution approaches have friction:

- **Version mismatch** - Skills and tools update separately, causing compatibility issues
- **Manual management** - Cloning skills from git repos requires extra steps per project
- **Sharing overhead** - Teams must commit cloned files or repeat setup on each machine

This project proposes a convention: **ship skills inside npm packages**. When you `npm install` a tool, its skills come bundled. Run `skills-npm` to symlink them for your agent.

**Read the full proposal: [PROPOSAL.md](./PROPOSAL.md)**

## Usage

```bash
npm i -D skills-npm
```

Add a `prepare` script to your `package.json` so the skills are symlinked automatically for your agent whenever you install dependencies:

```json
{
  "private": true,
  "scripts": {
    "prepare": "skills-npm"
  }
}
```

## For Package Authors

Include a `skills/` directory in your package:

```
my-tool/
├── package.json
├── dist/
└── skills/
    └── my-skill/
        └── SKILL.md
```

See [PROPOSAL.md](./PROPOSAL.md#for-package-authors) for detailed instructions.

## Sponsors

<p align="center">
  <a href="https://cdn.jsdelivr.net/gh/antfu/static/sponsors.svg">
    <img src='https://cdn.jsdelivr.net/gh/antfu/static/sponsors.svg'/>
  </a>
</p>

## License

[MIT](./LICENSE) License © [Anthony Fu](https://github.com/antfu)

<!-- Badges -->

[npm-version-src]: https://img.shields.io/npm/v/skills-npm?style=flat&colorA=080f12&colorB=1fa669
[npm-version-href]: https://npmjs.com/package/skills-npm
[npm-downloads-src]: https://img.shields.io/npm/dm/skills-npm?style=flat&colorA=080f12&colorB=1fa669
[npm-downloads-href]: https://npmjs.com/package/skills-npm
[bundle-src]: https://img.shields.io/bundlephobia/minzip/skills-npm?style=flat&colorA=080f12&colorB=1fa669&label=minzip
[bundle-href]: https://bundlephobia.com/result?p=skills-npm
[license-src]: https://img.shields.io/github/license/antfu/skills-npm.svg?style=flat&colorA=080f12&colorB=1fa669
[license-href]: https://github.com/antfu/skills-npm/blob/main/LICENSE
[jsdocs-src]: https://img.shields.io/badge/jsdocs-reference-080f12?style=flat&colorA=080f12&colorB=1fa669
[jsdocs-href]: https://www.jsdocs.io/package/skills-npm
