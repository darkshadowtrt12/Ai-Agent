# Virtual Anime friend AI Agent

A sophisticated AI agent built with Microsoft Agent Framework and Foundry, designed to act as a virtual anime friend with advanced features.

## Features

- **Conversational AI**: Powered by Foundry models for natural, engaging conversations
- **Knowledge Integration**: Access to Wikipedia information for factual queries
- **Emotional Intelligence**: Human-like emotional responses - praises good actions, handles negatives calmly
- **Command Execution**: Safe execution of laptop commands only on explicit user request
- **Music Integration**: Play any Spotify song when requested
- **Personalization**: Tailored responses for the user
- **Safety Features**: Built-in safeguards to prevent misuse and harmful actions
- **Avatar Support**: Foundation for physical virtual form with lip syncing (extensible)
- **HTTP Server**: Deployable as a web service for production use

## Project Structure

```
.
├── src/
│   └── agent.py          # Main agent implementation
├── .env.template         # Environment variables template
├── requirements.txt      # Python dependencies
├── .vscode/
│   ├── launch.json       # Debug configurations
│   └── tasks.json        # VS Code tasks
└── README.md            # This file
```

## Setup

1. **Clone/Create the project** and navigate to the directory

2. **Create virtual environment**:
   ```bash
   python -m venv venv
   ```

3. **Activate virtual environment**:
   - Windows: `venv\Scripts\activate`
   - Linux/Mac: `source venv/bin/activate`

4. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

5. **Configure environment variables**:
   - Copy `.env.template` to `.env`
   - Fill in your Foundry project details:
     - `FOUNDRY_PROJECT_ENDPOINT`: Your Foundry project endpoint URL
     - `FOUNDRY_MODEL_DEPLOYMENT_NAME`: Your deployed model name
   - Set up Spotify API (for singing feature):
     - Get credentials from [Spotify Developer Dashboard](https://developer.spotify.com/dashboard)
     - `SPOTIFY_CLIENT_ID` and `SPOTIFY_CLIENT_SECRET`
   - Set `USER_NAME` for personalization

## Usage

### Console Mode (Development)

Run the agent in terminal for interactive chat:

```bash
python src/agent.py
```

Type your messages and press Enter. Type 'quit' to exit.

### HTTP Server Mode (Production)

Run as a web service:

```bash
python src/agent.py --server
```

The agent will be available as an HTTP API endpoint.

### Debugging

Use VS Code debugger:

1. Open the project in VS Code
2. Go to Run and Debug panel
3. Select "Debug Local Agent HTTP Server" or "Debug Local Agent in Terminal"
4. Click run

This enables debugging with AI Toolkit Agent Inspector for advanced monitoring.

## Extensibility

### Adding Avatar and Lip Sync

For physical virtual form with perfect lip syncing:

1. **TTS Integration**: Use `pyttsx3` or Azure Speech Services for text-to-speech
2. **Lip Sync Libraries**:
   - `rhubarb-lip-sync`: Open-source lip sync tool
   - Integrate with 3D avatar engines like Unity or Unreal Engine
3. **Avatar Rendering**: Use libraries like `pyrender` or external services

Example TTS addition:
```python
import pyttsx3

def speak_text(text: str) -> str:
    engine = pyttsx3.init()
    engine.say(text)
    engine.runAndWait()
    return "Spoken aloud"
```

### Emotional State Management

Enhance emotions with state tracking:
- Sentiment analysis on user input
- Mood persistence across sessions
- Dynamic response adjustment

### Additional Safety

- Input sanitization
- Rate limiting
- Content filtering
- Audit logging

### Multi-Agent Workflows

Extend to multi-agent systems for complex interactions.

## Deployment to Foundry

Once ready for production:

1. Ensure HTTP server mode works
2. Use AI Toolkit to deploy to Foundry
3. Configure RBAC and monitoring

## Requirements

- Python 3.10+
- Azure subscription with Foundry access
- Spotify Developer account (optional for music)
- VS Code with AI Toolkit extension (recommended)

## Contributing

This is a scaffolded project. Extend features as needed while maintaining safety and best practices.

## License

[Add your license here]
