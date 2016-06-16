# Calibre Buildkite Plugin

A Buildkite plugin allowing you to create [Calibre](https://calibreapp.com/) snapshots.

## Example

```yml
steps:
  - command: test.sh
    plugins:
      calibre:
        snapshot: your-site-slug
```

## Configuring

### `CALIBRE_API_KEY`

Your Calibre API key should be set to this environment variable, either in your pipeline’s environment variable settings or exposed in an environment hook.

## License

MIT (see [LICENSE](LICENSE))
