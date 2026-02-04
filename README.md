⚡ PyFuse

PyFuse is a high-performance, unified Python toolchain and library organizer. It is designed to be significantly faster than standard tools by offloading heavy directory operations and package scanning to a Rust-powered core engine.

Beyond just installing packages, PyFuse acts as a "Library Manager," allowing you to isolate, move, and toggle libraries across different project folders with ease.

🚀 Key Features

Turbo-Charged Scanning: Uses a Rust-based parallel directory scanner (rayon) to list and verify libraries instantly.

Portable Installation: Install any library into a specific folder of your choice using --target logic, making your project dependencies truly portable.

Library Organizer:

Move/Copy: Quickly migrate libraries from one folder to another.

Disable/Enable: Temporarily "hide" a library from Python without deleting it (renames to .disabled).

Built-in Scaffolding: Create new library containers or structured project folders with one command.

Zero-Config Venvs: Handles virtual environment creation automatically when needed.

🛠 Architecture

PyFuse uses a Hybrid Architecture:

The Turbo Core (src/lib.rs): A native Rust extension that handles performance-critical IO operations using multi-threading.

The CLI (pyfuse/cli.py): A modern interface built with Typer and Rich for a premium developer experience.

The Smart Layer (pyfuse/smart.py): Logic for managing file-system level library toggling and directory management.

💻 Usage Guide

1. Installation

If you have built the .whl file using the setup_project.py script:

pip install pyfuse-0.1.0-cp310-abi3-win_amd64.whl


2. Creating a Library Container

Create a dedicated folder to hold specific sets of libraries:

pyfuse create my_libs


3. Super-Fast Installation

Install a library directly into your custom folder:

pyfuse install requests my_libs


4. Organizing Libraries

List all libraries in a folder (utilizing the Rust parallel engine):

pyfuse list-libs my_libs


Move a library to a different project:

pyfuse move requests my_libs other_project_libs


5. Toggling Libraries

Disable a library to test fallback logic or resolve conflicts without uninstalling:

pyfuse disable requests my_libs
# Re-enable it later:
pyfuse enable requests my_libs


🛠 Development & Building

To compile the Rust core and generate a Windows Wheel on your machine:

Ensure Rust is installed.

Run the automated builder:

python setup_project.py


The wheel will be located in PyFuse/target/wheels/.

📄 License

This project is licensed under the MIT License.

Built for speed and organization.
