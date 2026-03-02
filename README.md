# instruct-sync-registry

Community registry of GitHub Copilot instruction packs for [instruct-sync](https://github.com/zekariasasaminew/instruct-sync).

## What is this?

This repo is the community index of reusable Copilot instruction packs. When you run `npx instruct-sync add react`, it looks up `react` in this registry and fetches the instructions from the source listed here.

## Adding your pack

1. Fork this repo
2. Add your `.md` instruction file to `packs/`
3. Add an entry to `registry.json`
4. Open a PR

### registry.json entry format

```json
{
  "name": "your-pack-name",
  "description": "One line description",
  "source": "github:zekariasasaminew/instruct-sync-registry/packs/your-pack.md",
  "author": "your-github-username",
  "tags": ["tag1", "tag2"]
}
```

## Available packs

| Name | Description | Tags |
|------|-------------|------|
| react | React 18+ best practices and patterns | react, frontend, javascript |
| nextjs | Next.js App Router conventions and patterns | nextjs, react, fullstack |
| typescript | TypeScript strict mode guidelines | typescript, javascript |
| python | Python 3.10+ best practices | python, backend |
| go | Go idiomatic patterns and conventions | go, backend |

## License

MIT
