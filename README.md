⚡ PyFuse

The Unified Python Toolchain.

PyFuse is the end of fragmentation. It replaces pip, virtualenv, poetry, pip-tools, twine, and conda with a single, blazing-fast, Rust-powered binary that just works.

🚀 Features at a Glance

Feature

PyFuse

Legacy Tools

Speed

Rust Core (~15ms resolution)

Python (Secs to Mins)

Environment

Smart Auto-Detection

Manual activation hell

Storage

Global Deduplication

duplicated per venv

Security

Real-time CVE Scanning

External plugins needed

Migration

1-Command Import

Manual refactoring

🛠 Installation

curl -fsSL [https://pyfuse.dev/install.sh](https://pyfuse.dev/install.sh) | sh


💡 Quick Start

1. Create a Project
PyFuse intelligently scaffolds based on your intent.

pyfuse new data-analysis
# Auto-installs Jupyter, Pandas, and sets up high-mem config


2. Smart Install
Add packages with parallel downloads and instant resolution.

cd data-analysis
pyfuse add numpy seaborn


3. Run
No source venv/bin/activate needed. Ever.

pyfuse run start


🧠 The "Smart Environment"

PyFuse scans your code structure.

See a manage.py? We tune for Django.

See uvloop? We enable async optimizations.

See a Dockerfile? We sync the build context.

🕰 Time Machine

Broke production? Go back to exactly how the world looked yesterday.

pyfuse install --date="2023-10-27"


🏗 Architecture

Core: Rust (using pyo3 bindings) for constraint solving and disk I/O.

CLI: Python (Typer/Rich) for developer experience and plugin capability.

PyFuse: Stop managing environments. Start building
