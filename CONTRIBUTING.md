# Contributing plugin releases

`agena-marketplace.json` is generated. Do not hand-edit plugin/version records.

1. Publish the plugin from its own GitHub repository.
2. Add its `agena-plugin-release.json` with `agena-plugin marketplace add`.
3. Never modify an existing `releases/<plugin-id>/<version>.json`; publish a new
   plugin version instead.
4. Rebuild with `agena-plugin marketplace build releases --output agena-marketplace.json --github-only`.
5. Open a focused pull request.

Reviewers inspect source provenance, requested capabilities, dependencies,
licensing, security posture, and stable plugin identity.
