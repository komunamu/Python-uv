# UV: Modern Python Package Management

[![GitHub stars](https://img.shields.io/github/stars/astral-sh/uv?style=social)](https://github.com/astral-sh/uv)
[![PyPI version](https://img.shields.io/pypi/v/uv.svg)](https://pypi.org/project/uv/)
[![Python Versions](https://img.shields.io/pypi/pyversions/uv.svg)](https://pypi.org/project/uv/)

UV is an extremely fast Python package installer and resolver, designed as a drop-in replacement for pip and pip-tools. Built in Rust, UV offers significant performance improvements for Python dependency management.

## ✨ Features

- 🚀 **Lightning Fast**: Dramatically faster installation and dependency resolution
- 🔄 **Pip Compatible**: Familiar interface for pip users
- 🔒 **Reproducible**: Generate lock files for consistent environments
- 💻 **Cross-Platform**: Works on Windows, macOS, and Linux
- 🧠 **Smart Caching**: Optimized caching for repeated installations
- 🛠️ **Virtual Environment Support**: Built-in management of virtual environments

## 📦 Installation

```bash
# Install using pip
pip install uv

# Or using pipx for isolated installation
pipx install uv
```

## 🚀 Basic Usage

### Package Installation

```bash
# Install a package
uv pip install requests

# Install multiple packages
uv pip install pandas matplotlib numpy

# Install specific version
uv pip install django==4.2.0

# Install from requirements file
uv pip install -r requirements.txt

# Install in development mode
uv pip install -e .
```

### Virtual Environment Management

```bash
# Create a virtual environment in the default location
uv venv

# Create with specific Python version
uv venv --python=python3.10

# Create with custom name
uv venv .venv
```

### Package Listing and Information

```bash
# List all installed packages
uv pip list

# Show detailed information about a package
uv pip show requests

# List outdated packages
uv pip list --outdated
```

### Dependency Management

```bash
# Generate lock file from requirements
uv pip compile requirements.in -o requirements.txt

# Install from lock file with exact versions
uv pip sync requirements.txt
```

### Uninstallation

```bash
# Uninstall a package
uv pip uninstall requests

# Uninstall multiple packages
uv pip uninstall requests pandas
```

### Cache Management

```bash
# Clean package cache
uv cache clean
```

## 🔄 Migration from pip

UV is designed to be a drop-in replacement for pip. Most pip commands work with UV by simply prefixing them with `uv`:

```bash
# Instead of:
pip install -r requirements.txt

# Use:
uv pip install -r requirements.txt
```

## 📋 Requirements Files

UV supports traditional `requirements.txt` files as well as the following modern formats:

- `pyproject.toml`
- `setup.py`/`setup.cfg`
- Poetry, PDM, and Hatch project files

## 🔄 CI/CD Integration

UV can significantly speed up your CI/CD pipelines. Example GitHub Actions usage:

```yaml
- name: Install dependencies
  run: |
    pip install uv
    uv pip install -r requirements.txt
```

## 📚 Additional Resources

- [Official Documentation](https://github.com/astral-sh/uv)
- [GitHub Repository](https://github.com/astral-sh/uv)
- [PyPI Project](https://pypi.org/project/uv/)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📜 License

UV is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
