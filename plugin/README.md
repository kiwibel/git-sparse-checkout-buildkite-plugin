# Git sparse checkout Buildkite plugin

Perform a blobless git clone and sparse checkout

## Example

Add the following to your `pipeline.yml` if you want to only checkout:
 - all files in the top level directory
 - all files at any depth under .buildkite/

```yml
steps:
  - command: <your command>
    plugins:
      - kiwibel/git-sparse-checkout:
          pattern: '.buildkite'
```

## Configuration

### `pattern` (Required, string)

Pattern for git [sparse checkout](https://git-scm.com/docs/git-sparse-checkout).
Supports cone mode only i.e. lets you specify only what _directories to include_. 

## Developing

To run the tests:

```shell
docker-compose run --rm tests
```

## Contributing

1. Fork the repo
2. Make the changes
3. Run the tests
4. Commit and push your changes
5. Send a pull request