# Kition kit CI runners

CI runners for the public Kition kits. No source lives here: each workflow in
`.github/workflows/` checks out one commit of a public kit repository and runs Kition's
reusable kit CI on it
([`KitionAI/kition` .github/workflows/kit-ci.yml](https://github.com/KitionAI/kition/blob/main/.github/workflows/kit-ci.yml),
always at `main`). The runs use this organization's GitHub Actions runners, which adds to the
concurrent jobs of the KitionAI organization.

The kits' code, issues and pull requests live in their own repositories:

| Kit | Repository | Workflow |
| --- | --- | --- |
| board | [KitionAI/kition-board](https://github.com/KitionAI/kition-board) | `.github/workflows/board.yml` |
| cad | [KitionAI/kition-cad](https://github.com/KitionAI/kition-cad) | `.github/workflows/cad.yml` |
| design | [KitionAI/kition-design](https://github.com/KitionAI/kition-design) | `.github/workflows/design.yml` |
| doc | [KitionAI/kition-doc](https://github.com/KitionAI/kition-doc) | `.github/workflows/doc.yml` |
| film | [KitionAI/kition-film](https://github.com/KitionAI/kition-film) | `.github/workflows/film.yml` |
| html | [KitionAI/kition-html](https://github.com/KitionAI/kition-html) | `.github/workflows/html.yml` |
| layout | [KitionAI/kition-layout](https://github.com/KitionAI/kition-layout) | `.github/workflows/layout.yml` |
| motion | [KitionAI/kition-motion](https://github.com/KitionAI/kition-motion) | `.github/workflows/motion.yml` |
| note | [KitionAI/kition-note](https://github.com/KitionAI/kition-note) | `.github/workflows/note.yml` |
| pdf | [KitionAI/kition-pdf](https://github.com/KitionAI/kition-pdf) | `.github/workflows/pdf.yml` |
| photo | [KitionAI/kition-photo](https://github.com/KitionAI/kition-photo) | `.github/workflows/photo.yml` |
| scene | [KitionAI/kition-scene](https://github.com/KitionAI/kition-scene) | `.github/workflows/scene.yml` |
| sheet | [KitionAI/kition-sheet](https://github.com/KitionAI/kition-sheet) | `.github/workflows/sheet.yml` |
| slide | [KitionAI/kition-slide](https://github.com/KitionAI/kition-slide) | `.github/workflows/slide.yml` |
| table | [KitionAI/kition-table](https://github.com/KitionAI/kition-table) | `.github/workflows/table.yml` |
| vector | [KitionAI/kition-vector](https://github.com/KitionAI/kition-vector) | `.github/workflows/vector.yml` |

A run is started by Kition's `scripts/kit-ci.sh` (`gh workflow run <kit>.yml -f sha=<commit>`)
and is named `<kit> <commit>`; the plan job's artifact `tested` (`tested.json`) names the
repository and the commit that were tested. Do not edit these files by hand: they are written by
`node scripts/kit-ci-runner-repo.mjs <dir>` in [KitionAI/kition](https://github.com/KitionAI/kition),
whose `docs/kits.md` (section 4c, Kit CI) explains runner pools.

## License

Apache-2.0, as Kition: see [LICENSE](LICENSE).
