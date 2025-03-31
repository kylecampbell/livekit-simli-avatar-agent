# LiveKit Simli AI Avatar Agent

This is an example of a Simli avatar that uses LiveKit to create an AI agent that can be used in a LiveKit room.

## Installation

```console
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### NOTE

The `simli` package is not currently compatible. Until this is fixed, in Simli's `utils.py` file, change the `layout` value from `1` to `"mono"`. To do this... while in this project's python environment (venv), we need to git clone Simli's python client repo, edit the `utils.py` file, then pip install the repo with the `-e` flag:

```console
git clone https://github.com/simliai/simli-client-py.git
cd simli-client-py
```

Edit the `utils.py` file, changing the `layout` value from `1` to `"mono"`.

```console
pip install -e .
```

## Setup

In this project's directory, run the following command to copy the `.env.example` file to `.env`:

```console
cp .env.example .env
```

Edit the `.env` file with your own values.

### Simli

Visit https://simli.com to get your `SIMLI_API_KEY` and `SIMLI_FACE_ID`.

### Deepgram

Visit https://deepgram.com to get your `DEEPGRAM_API_KEY`.

### OpenAI

Visit https://platform.openai.com to get your `OPENAI_API_KEY`.

### ElevenLabs

Visit https://elevenlabs.io to get your `ELEVEN_API_KEY`.

### LiveKit Cloud

Visit https://livekit.io to get your `LIVEKIT_API_KEY`, `LIVEKIT_API_SECRET`, and `LIVEKIT_URL`.

## Usage

In this project's directory, run the following command to start the dispatcher:
```console
python dispatcher.py --port 8089
```

In a new terminal, run the following command to start the agent:
```console
source venv/bin/activate
python agent_worker.py dev --avatar-url http://localhost:8089/launch
```

### LiveKit Agents Playground

Visit https://docs.livekit.io/home/cli/cli-setup to install the LiveKit CLI and authenticate with LiveKit Cloud.

In your browser, navigate to https://agents-playground.livekit.io, and connect to your LiveKit Cloud project.
Then, select the connect button on the top right.