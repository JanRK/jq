# jq

A lightweight Docker image with [jq](https://jqlang.github.io/jq/) JSON processor based on Alpine Linux.

## Description

This image provides the `jq` command-line JSON processor in a minimal Alpine Linux container. Perfect for processing JSON in CI/CD pipelines, scripts, or anywhere you need a lightweight JSON manipulation tool.

## Usage

### Basic Usage

```bash
# Process JSON from stdin
echo '{"name":"John","age":30}' | docker run --rm -i ghcr.io/janrk/jq '.name'

# Read from a file
docker run --rm -i ghcr.io/janrk/jq '.' < input.json

# With a mounted volume
docker run --rm -v $(pwd):/data ghcr.io/janrk/jq '.' /data/input.json
```

### Using in CI/CD

```yaml
- name: Process JSON
  run: |
    docker run --rm -i ghcr.io/janrk/jq '.version' < package.json
```

## Tags

- `latest` - Latest build from main branch
- `$alpine_version` - Based on Alpine version
- `alpine-$alpine_version` - Based on Alpine version
- `YYYYMMDD-RUN_NUMBER` - Date-based builds

## License

This Docker image packaging is provided as-is. See [jq's license](https://github.com/jqlang/jq/blob/master/COPYING) for the jq tool itself.
