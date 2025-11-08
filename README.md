Wolf CLI
Wolf CLI is a powerful, AI-driven command-line assistant designed for seamless interaction with your local environment. It leverages Large Language Models (LLMs) to understand natural language prompts, execute local tools and commands, and even interpret images.
Features
Natural Language Interface: Interact with your system using plain English.
Local Tool Execution: Run local commands and scripts securely.
Vision Capabilities: Analyze images and screenshots directly from the command line.
Multiple LLM Providers: Supports Ollama for local LLMs and OpenRouter for a wide range of models.
Configurable Safety Levels: Choose between safe, interactive, and auto-execution modes.
Extensible Tool Registry: Easily add new tools and capabilities.
Installation
To install Wolf CLI on another machine, you first need to build the package from the source directory.

Build the package:

# Make sure you have the build package installed

pip install build

# Build the wheel

python -m build

This will create a .whl file in the dist/ directory.

Install the wheel: Copy the generated .whl file to the target machine and install it using pip:

pip install /path/to/wolf_cli-0.2.0-py3-none-any.whl

This will install the wolf command and all its dependencies, making it globally available.
Usage
Basic Usage
To use Wolf CLI, simply type wolf followed by your prompt:

wolf "list all the files in the current directory"
Command-Line Options
Option
Description
-h, --help
Show the help message and exit.
--safe
Enable safe mode (strict permissions, read-only).
--auto
Allow automatic tool execution (permissive, no confirmations).
--image <path>
Path to an image for vision input. Can be used multiple times.
--provider <name>
LLM provider to use (ollama or openrouter). Default: ollama.
--model <name>
LLM model to use (overrides the configuration).
-v, --verbose
Enable verbose logging for debugging.
--list-tools
List available tools and exit.

Examples
Chat with the assistant:

wolf "hi there"

List files in the current directory:

wolf "list all python files in the current directory"

Analyze an image:

wolf --image screenshot.png "what's in this image?"

Create a file:

wolf --auto "create a file named test.txt with the content 'hello world'"
Configuration
Wolf CLI stores its configuration and logs in a .wolf directory in your home folder.

Configuration File: ~/.wolf/config.json
Log File: ~/.wolf/logs/wolf-cli.log

The configuration file is created with default values on the first run. You can edit this file to change the default model, provider, and other settings.

