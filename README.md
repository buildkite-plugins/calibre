# Calibre Buildkite Plugin

A [Buildkite](https://buildkite.com/) plugin to easily create create [Calibre](https://calibreapp.com/) snapshots from deloy pipelines.

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
  - name: ":calibre: Site 1"
    plugins:
      calibre:
        snapshot: site-1
        api-key-from: CALIBRE_SITE_1_API_KEY
  - name: ":calibre: Site 2"
    plugins:
      calibre:
        snapshot: site-2
        api-key-from: CALIBRE_SITE_2_API_KEY
```

Default: `CALIBRE_API_KEY`

## License

MIT (see [LICENSE](LICENSE))
