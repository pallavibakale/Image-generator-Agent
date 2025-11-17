# Image-generator-Agent — Day 2: Agent Tool Patterns & MCP Best Practices

This repository contains example code and a Kaggle notebook that demonstrates how to integrate an ADK-based agent with external tools using the Model Context Protocol (MCP). The focal notebook, `day-2b-agent-tools-best-practices.ipynb`, walks through connecting an agent to MCP servers, running long-running/human-in-the-loop operations, and building resumable workflows.

This material was created as part of a Kaggle Agents course and is intended for learning and experimentation.

## Contents

- `day-2b-agent-tools-best-practices.ipynb` — Hands-on Kaggle notebook demonstrating:
  - Using the Google ADK (Agent Development Kit) and Gemini LLM
  - Connecting to MCP servers via the ADK `McpToolset`
  - Running the Everything MCP server (`@modelcontextprotocol/server-everything`) to produce a tiny test image
  - Decoding and displaying base64 image data returned from MCP tools
  - Patterns for resumability, retry configs, and long-running operations

## Features Highlighted

- MCP integration (stdio and HTTP connection examples)
- Using ADK tools and toolsets in an LLM agent
- Configuring retry options for robust LLM calls
- Example of human-in-the-loop / long-running workflows
- Displaying base64 images returned by tools

## Prerequisites

- Python 3.8+ (notebook used Python 3.11 in Kaggle environment)
- Node.js and npm (for running MCP servers locally via `npx`)
- (Optional) Kaggle account if using notebook on Kaggle
- Google AI / Gemini API Key for model access (when running code that calls Gemini)
- `google-adk` package when running outside Kaggle:
  - pip install google-adk

## Quick start — On Kaggle (recommended for the course)

1. Open the notebook `day-2b-agent-tools-best-practices.ipynb` on Kaggle.
2. Click "Copy and Edit" to create your own editable copy.
3. Add your Gemini API key as a Kaggle secret named `GOOGLE_API_KEY`:
   - In the notebook editor: Add-ons → Secrets → create `GOOGLE_API_KEY`.
4. Run the notebook cells sequentially (avoid "Run all" to reduce rate-limit risk).

## Quick start — Locally

1. Ensure Python and Node.js/npm are installed.
2. Install ADK and dependencies:
   - pip install google-adk
3. Ensure you have a valid Gemini API key and set it as an environment variable:
   - export GOOGLE_API_KEY="your_key_here"
4. Run the notebook using JupyterLab / Jupyter Notebook, or inspect/convert the notebook to scripts.

Note: The notebook uses `npx -y @modelcontextprotocol/server-everything` to start a demo MCP server. Running this locally requires internet access and Node.js.

## Security & Privacy

- Do not commit API keys to the repository.
- Use environment variables or platform secrets (Kaggle secrets) to provide credentials.
- The Everything MCP server is a demo tool: do not use it for production.

## Troubleshooting

- If you run into rate limits or transient errors when calling the Gemini model, increase or tune the retry configuration present in the notebook.
- If MCP server fails to start via `npx`, verify your Node/npm installation and network access.
- On Kaggle, if you see "Waiting for the next available notebook", wait a short time and retry — the environment queue is shared.

## Contributing

Contributions, bug reports, and suggestions are welcome. For changes to examples or to add more MCP server demos, please open a pull request or an issue in this repository.

## License

Licensed under the Apache License, Version 2.0. See the LICENSE file for details.

## Maintainer

pallavibakale