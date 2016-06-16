# Calibre Buildkite Plugin

A Buildkite plugin allowing you to create [Calibre](https://calibreapp.com/) snapshots.

## Example

```yml
steps:
  - command: deploy.sh
  - wait
  - name: ":calibre:"
    plugins:
      calibre:
        snapshot: my-site
```

## Configuring

### `CALIBRE_API_KEY`

Your Calibre API key should be set to this environment variable, either in your pipeline’s environment variable settings or exposed in an environment hook. If you need different keys for different parts of your pipeline use `api-key-from` instead.

## Options

### `api-key-from`

Specifies the environment variable containing the calibre API key, useful if you need to create snapshots for different Calibre sites (with different API keys) from within the same pipeline. For example:

```yml
steps:
  - name: ":calibre: Other Site"
    plugins:
      calibre:
        snapshot: other-site
        api-key-from: CALIBRE_OTHER_SITE_API_KEY
```

Default: `CALIBRE_API_KEY`

## License

MIT (see [LICENSE](LICENSE))
