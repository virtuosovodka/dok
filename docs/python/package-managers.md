# Python Package Managers

Python has several package managers, each with different approaches and trade-offs. This guide covers the most commonly used tools.

## pip

The default package manager for Python, included with most Python installations.

**Install a package:**
```bash
pip install package_name
```

**Install specific version:**
```bash
pip install package_name==1.2.3
```

**Install from requirements file:**
```bash
pip install -r requirements.txt
```

**Generate requirements file:**
```bash
pip freeze > requirements.txt
```

**Upgrade a package:**
```bash
pip install --upgrade package_name
```

**Uninstall a package:**
```bash
pip uninstall package_name
```

## Poetry

A modern dependency management and packaging tool that uses `pyproject.toml` for configuration.

**Initialize a new project:**
```bash
poetry new my_project
```

**Add a dependency:**
```bash
poetry add package_name
```

**Add a dev dependency:**
```bash
poetry add --group dev package_name
```

**Install dependencies from lock file:**
```bash
poetry install
```

**Update dependencies:**
```bash
poetry update
```

**Build and publish:**
```bash
poetry build
poetry publish
```

**Key benefits:**
- Deterministic builds via `poetry.lock`
- Better dependency resolution
- Integrated project scaffolding and publishing
- Clear separation of dev and production dependencies

## uv

A fast Python package installer and resolver written in Rust, created by the Astral team.

**Install packages:**
```bash
uv pip install package_name
```

**Create virtual environment:**
```bash
uv venv
```

**Install from requirements file:**
```bash
uv pip install -r requirements.txt
```

**Compile requirements:**
```bash
uv pip compile requirements.in -o requirements.txt
```

**Key benefits:**
- Significantly faster than pip (10-100x)
- Drop-in replacement for pip
- Better error messages
- Efficient lock file management

## Conda

A cross-platform package manager from Anaconda, useful for scientific computing and data science.

**Install a package:**
```bash
conda install package_name
```

**Create environment:**
```bash
conda create -n env_name python=3.11
```

**Activate environment:**
```bash
conda activate env_name
```

**Export environment:**
```bash
conda env export > environment.yml
```

**Create environment from file:**
```bash
conda env create -f environment.yml
```

**Key benefits:**
- Handles non-Python dependencies (C libraries, system packages)
- Excellent for scientific/data science workflows
- Pre-built binaries for complex packages
- Environment management built-in

## Comparison

| Feature | pip | Poetry | uv | Conda |
|---------|-----|--------|-----|-------|
| Speed | Slow | Medium | Very Fast | Medium |
| Dependency Resolution | Basic | Advanced | Advanced | Advanced |
| Lock Files | No | Yes | Yes | Yes |
| Virtual Envs | External | Built-in | Built-in | Built-in |
| Scientific Packages | Good | Good | Good | Excellent |
| Learning Curve | Easiest | Medium | Easy | Medium |

## When to Use What

- **pip**: Simple projects, scripts, when dependencies are straightforward
- **Poetry**: Modern Python projects needing reproducible builds and publishing
- **uv**: When speed matters and you want pip compatibility
- **Conda**: Scientific/data science work, complex non-Python dependencies

## Best Practices

1. **Always use virtual environments** to isolate project dependencies
2. **Commit lock files** (poetry.lock, uv.lock) to version control for reproducibility
3. **Keep requirements/dependencies up to date** but test before upgrading
4. **Specify Python version** in your configuration (pyproject.toml or environment.yml)
5. **Separate dev dependencies** from production ones
6. **Use a requirements.txt fallback** if distributing to users who don't use Poetry/uv
