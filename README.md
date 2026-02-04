⚡ PyFuse v0.1.1

PyFuse is an ultra-fast Python library organizer and installer. It solves the "messy environment" problem by allowing you to install libraries into isolated folders and switch between them instantly.

🚀 Key Features

Folder-Based Isolation: Install libraries into any folder and use the use command to ensure your code only sees that specific folder.

Rust-Powered Speed: High-speed directory scanning via native Rust extensions.

Smart Moving: Moves libraries and their associated metadata (dist-info) across folders.

Toggle State: Enable or disable libraries without deleting them.

💻 Commands Guide

1. Installation into Folders

Use the --folder or -f flag to target a specific library container.

# Create a folder for your data science libs
pyfuse create ds_libs

# Install into that specific folder
pyfuse install pandas --folder ds_libs
pyfuse install numpy -f ds_libs


2. Organizing & Moving

PyFuse ensures that when you move a library, all its parts (including hidden metadata) go with it.

# Move 'requests' from one folder to another
pyfuse move requests old_libs new_libs


3. Activating a Folder (Isolation)

To make your script use only the libraries in a specific folder:

pyfuse use ds_libs


4. Managing States

Disable libraries to test your code without them, or re-enable them later.

# Disable 'requests' in the current folder
pyfuse disable requests --folder my_libs

# List libraries to see their status
pyfuse list-libs -f my_libs


🛠 Advanced Building

To rebuild the Rust core for your Windows machine:

Run python setup_project.py.

Install the generated wheel from PyFuse/target/wheels/.

PyFuse: Organize, Move, and Isolate your Python libraries at Rust-speed.
