# Agena Plugin Marketplace Template

Template repository for curated GitHub-first Agena plugin marketplaces.

This is a GitHub-first Agena plugin marketplace. Reviewed release manifests
under `releases/<plugin-id>/<version>.json` are the source of truth;
`agena-marketplace.json` is deterministic generated output.

## Use this marketplace

```bash
agena plugin sync --registry canxin121/agena-plugin-marketplace-template
agena plugin search --registry canxin121/agena-plugin-marketplace-template QUERY
agena plugin install PLUGIN.ID --registry canxin121/agena-plugin-marketplace-template
```

## Add a published plugin release

Publish the plugin from its own GitHub repository first. Download that
release's `agena-plugin-release.json`, then run:

```bash
agena-plugin marketplace add /path/to/agena-plugin-release.json \
  --releases releases \
  --project agena-marketplace.toml \
  --index agena-marketplace.json \
  --github-only
```

The command stores a new immutable version manifest and rebuilds the catalog.
Existing plugin-id/version files cannot be replaced with different content.

CI verifies source repository/tag/commit provenance, immutable GitHub Release
asset URLs, SHA-256 declarations, rename graph validity, and deterministic
catalog generation.
