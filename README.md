⚡ PyFuse

PyFuse is a high-performance, unified Python development toolchain built for the modern era. By combining a core engine written in Rust with a developer-friendly Python CLI, PyFuse provides the speed of native code with the flexibility of the Python ecosystem.

🚀 Key Features

Blazing Fast Core: Dependency resolution and security scanning handled by a native Rust extension (pyfuse_core).

Smart Environments: Automatic virtual environment management (.venv) with heuristic project detection.

Security First: Built-in vulnerability scanner that prevents the installation of known malicious or insecure packages.

Intelligent Scaffolding: Create production-ready project structures with optimal pyproject.toml configurations based on project type.

Seamless Fallback: Works out of the box even if the Rust engine isn't compiled, falling back to a pure-Python logic engine.

🛠 Architecture

PyFuse uses a Hybrid Architecture:

The Iron Core (src/lib.rs): A Rust library exposed to Python via PyO3. It handles performance-critical tasks like calculating dependency graphs and checking security hashes.

The Brain (pyfuse/smart.py): Heuristic logic that detects whether you are building a Django app, a Data Science project, or a Microservice, and adjusts settings accordingly.

The Interface (pyfuse/cli.py): A beautiful Command Line Interface built with Typer and Rich for a premium developer experience.

📦 Installation

If you have downloaded the .whl (wheel) file:

pip install pyfuse-0.1.0-py3-none-any.whl


Once installed, the pyfuse command will be available in your terminal.

💻 Usage Guide

1. Create a New Project

Initialize a structured project with all the necessary files (src/, tests/, .gitignore, pyproject.toml):

pyfuse new my-awesome-app
cd my-awesome-app


2. Setup the Environment

PyFuse manages your virtual environments automatically. No more python -m venv .venv:

pyfuse env create


3. Install Packages

Install packages with an integrated security check:

pyfuse install requests
# Or install multiple packages
pyfuse install pandas numpy matplotlib


4. Security Scanning

If you attempt to install a package known to have critical vulnerabilities (like older versions of log4j), PyFuse will block the installation:

pyfuse install log4j
# Output: 🚨 Security Block: log4j is unsafe.


🛠 Development & Building

If you are contributing to PyFuse and want to compile the Rust core yourself, you need the maturin build tool:

Install Build Tools:

pip install maturin


Build the Package:

maturin build --release


The compiled wheel will be located in target/wheels/.

📝 Configuration

PyFuse generates a pyproject.toml for every project. It uses modern standards (PEP 517/518) and is compatible with other tools like pip, hatch, and ruff.

📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

Built with ❤️ for the Python community.
