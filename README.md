# kubectl-secret-d

A kubectl plugin that helps decode Kubernetes secrets in a human-readable format.

## Description

`kubectl-secret-d` is a kubectl plugin that makes it easy to decode and view the contents of Kubernetes secrets. It automatically decodes base64-encoded secret values and presents them in a readable format.

## Installation

### Using Homebrew (Recommended)

```bash
brew tap karpulix/kubectl-plugins
brew install karpulix/kubectl-plugins/kubectl-secret-d
```

### Manual Installation

1. Make the script executable:
```bash
chmod +x kubectl-secret_d
```

2. Move the script to a directory in your PATH:
```bash
sudo mv kubectl-secret_d /usr/local/bin/kubectl-secret_d
```

## Usage

```bash
kubectl secret-d <secret-name> [-n namespace] [-o yaml]
```

### Arguments

- `<secret-name>`: Name of the Kubernetes secret (required)
- `-n, --namespace`: Kubernetes namespace (optional)
- `-o, --output`: Output format (optional, supports 'yaml')

### Examples

1. Decode a secret in the default namespace:
```bash
kubectl secret-d my-secret
```

2. Decode a secret in a specific namespace:
```bash
kubectl secret-d my-secret -n my-namespace
```

3. Get the secret in YAML format:
```bash
kubectl secret-d my-secret -o yaml
```

## Output

By default, the plugin displays decoded key-value pairs in the format:
```
key1: value1
key2: value2
```

When using the YAML output format (`-o yaml`), it converts the secret data to a YAML format with `stringData` instead of base64-encoded `data`.

## Requirements

- kubectl
- yq (for YAML processing)
- base64 (usually pre-installed on Unix-like systems)

## License

This project is open source and available under the MIT License. 