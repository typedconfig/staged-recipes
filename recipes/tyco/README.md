# Tyco Python

[![PyPI version](https://badge.fury.io/py/tyco.svg)](https://badge.fury.io/py/tyco)
[![Python Version](https://img.shields.io/pypi/pyversions/tyco.svg)](https://pypi.org/project/tyco/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A Python library for parsing and working with Tyco configuration files - a modern, type-safe configuration language designed for clarity and flexibility.

## 🚀 Quick Start

### Installation

```bash
pip install tyco
```

### Basic Usage

```python
import tyco

# Load the bundled example.tyco file (included in the package)
with tyco.open_example_file() as f:
  context = tyco.load(f.name)

# Access global configuration values
globals = context.get_globals()
environment = globals.environment
debug = globals.debug
timeout = globals.timeout

# Get all instances as dictionaries
objects = context.get_objects()
databases = objects['Database']  # List of Database instances
servers = objects['Server']      # List of Server instances

# Access individual instance fields
primary_db = databases[0]
db_host = primary_db.host
db_port = primary_db.port
