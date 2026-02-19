# 67lab n8n Automated Marketing Engine

This project contains the blueprint and resources for the 67lab Automated Marketing Engine, designed to run on n8n.

## Structure

- `workflow.json`: The main n8n workflow file (import this into n8n).
- `prompts/`: Contains the system prompts for the specific AI agents.
    - `x_hype_man.md`: Prompt for X (Twitter) content.
    - `linkedin_leader.md`: Prompt for LinkedIn content.
    - `reddit_contributor.md`: Prompt for Reddit content.

## Setup

## Setup

1.  **Import Workflow**:
    - Open your n8n dashboard.
    - Click "Workflows" -> "Import from..." -> "File".
    - Select the `workflow.json` file from this project.

2.  **Configure Credentials**:
    - **Perplexity API**:
        - Open the "Perplexity Research" node.
        - Create a new "Header Auth" credential.
        - Name: `Perplexity API`
        - Header Name: `Authorization`
        - Value: `Bearer YOUR_PERPLEXITY_API_KEY`
    - **AI Agents**:
        - Open each "AI Agent" node (Product Logic, X, LinkedIn, Reddit, Critic).
        - Configure the "Model" to use your preferred LLM (e.g., OpenAI GPT-4o or Anthropic Claude 3.5 Sonnet).
        - Ensure you have the corresponding credentials set up in n8n for OpenAI/Anthropic.

3.  **Load System Prompts**:
    - The `workflow.json` has placeholder system prompts. For best results, copy the content from the files in the `prompts/` directory:
        - `prompts/x_hype_man.md` -> X Hype-Man Agent
        - `prompts/linkedin_leader.md` -> LinkedIn Leader Agent
        - `prompts/reddit_contributor.md` -> Reddit Contributor Agent
    - *Advanced*: You can replace the hardcoded system prompts in the Agent nodes with a "Read Binary File" node if you want to keep them synced with the files on disk (requires n8n to have access to the file system).

## Dependencies

- **n8n Version**: Ensure you are running a recent version of n8n that supports the `AI Agent` node type.
- **Perplexity API Key**: Required for the research phase.
- **LLM API Key**: OpenAI (gpt-4o) or Anthropic (claude-3-5-sonnet) recommended for best reasoning.
