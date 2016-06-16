# Calibre Buildkite Plugin

A Buildkite plugin allowing you to create [Calibre](https://calibreapp.com/) snapshots.

## Example

```yml
steps:
  - command: test.sh
    plugins:
      calibre:
        snapshot: my-site
```

## Configuring

### `CALIBRE_API_KEY`

Your Calibre API key should be set to this environment variable, either in your pipeline’s environment variable settings or exposed in an environment hook.

## Options

### `api-key`

You can use this to specify a different API key from the standard `CALIBRE_API_KEY`, useful if you want to create snapshots for different Calibre sites (with different API keys) from the same pipeline. For example:

```yml
steps:
  - command: test.sh
    plugins:
      calibre:
        snapshot: my-site
        api-key: $$SOME_ENV_VAR
```

## License

MIT (see [LICENSE](LICENSE))
