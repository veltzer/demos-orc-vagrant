# TOFIX

Findings from a code scan on 2026-10-04.

## Medium

- `README.md:1-5` - the repo describes itself as "Demos for the hashicorp vagrant tool", but contains no demos at all (no `Vagrantfile` or any other content anywhere in git history); add at least one demo `Vagrantfile` (and a checker for it, e.g. `vagrant validate`), or state in the README that it is a placeholder.
- `tera.templates/.github/dependabot.yml.tera` - never rendered: `rsconstruct.toml` has no `[processor.tera]` and the repo has no `config/personal.lua`/`config/version.lua`, so `.github/dependabot.yml` is a hand-kept copy. Add the standard `[processor.tera]` stanza and the config files it needs.

## Low

- `README.md:4-5` - bare URL under `## Links`; make it a markdown link, and consider generating the README from the fleet `tera.templates/README.md.tera`.
