# YouTube Automated Posting Pipeline for n8n

An end-to-end n8n workflow for a technology-explainer channel: topic research, fact checking, scripting, video production, quality checks, and controlled YouTube upload preparation.

## What it does

- Starts manually or on a weekly research schedule.
- Collects current technology signals and selects a topic.
- Produces a research package, verifies claims, plans content, and writes a script.
- Runs a script quality gate before creating a production brief.
- Sends approved narration and assets to a MoneyPrinterTurbo-compatible local video service.
- Keeps publishing disabled by default so uploads remain reviewable.

## Requirements

- An n8n instance with the AI/agent nodes used by the workflow.
- An LLM credential configured in n8n for the research and writing agents.
- A reachable MoneyPrinterTurbo-compatible video API, or replacement production nodes.
- Google/YouTube OAuth credentials configured directly in n8n for any upload nodes.
- Your own licensed or generated visual assets and music.

## Import and configure

1. In n8n, choose **Workflows → Import from File** and select `n8n-youtube-automation-workflow.json`.
2. The file contains one workflow in an exported array; select the included workflow if n8n prompts you.
3. Replace all `__REPLACE_*__` values and attach your own n8n credentials.
4. Set channel settings, topic niche, asset paths, video-service URL, and YouTube privacy level.
5. Test each stage manually. Enable scheduling only after reviewing the generated research, script, and video output.

## Security

OAuth credentials, webhook identifiers, and private service URLs have been removed. Store those values only in n8n credentials or environment variables. Do not commit them to this repository.

## Publishing safety

The pipeline is intentionally configured for human review and private publishing. Confirm copyright permissions, factual claims, metadata, and YouTube settings before enabling public uploads.
