# CharacterAI-TTS
**CharacterAI-TTS is an AI-based text-to-speech (TTS). It leverages character.ai advanced technology to synthesize natural-sounding speech from text.**

## 🚀 What's New

### v0.1.3
- ✅ **Increased character limit from 2048 to 4096 characters per request!**
- ⚠️ Long texts may take more time depending on CharacterAI server load.

### v0.1.2
- ℹ️ Maximum character limit was **2048 characters**.

## Installation

```bash
# Via pip (in the future)
pip install characterai-tts
# For audio playback (optional):
pip install -e .[audio]
```

## Getting Started

1.  **Obtain your token:**
    *   ⚠️ **DO NOT SHARE YOUR TOKEN!** It is required to send requests from your account.
    *   Open link https://character.ai/chat/2WPyJRflV_4nTx6_-tuNrhkiiqhDyOsn9O25BR1sDO8
    *   Open **Developer Tools** in your browser (usually F12).
    *   Go to the **Network** tab.
    *   Refresh the page or send a message to any character.
    *   In the list of network requests, click on any request (for example, to `/settings`).
    <img src="https://github.com/dauitsuragan002/tulgatts/raw/main/img/asset.jpg" alt="How to find the Authorization Token" width="500"/>

    *   Go to the **Headers** section.
    *   Find the **Authorization** header. It will look like:
        ```
        Authorization: Token <your_token_here>
        ```
    *   Copy only the token part (after `Token `).
    *   Set the `CHARACTER_AI_TOKEN` environment variable or create a `.env` file in the project root and add `CHARACTER_AI_TOKEN=your_copied_token`.
    **Authorization easy (use for mobile) script**  
    If you want to easily obtain your CharacterAI token using your email, you can use the provided `auth.py` script:

    ```sh
    pip install characterai
    python auth.py
    ```
    - Enter your email address.
    - Open the sign-in link sent to your email (you can do this on your mobile).
    - Paste the link back into the script prompt.
    - The script will save your token to `.env` in the format required for the library.

    This makes it easy to get your token without using browser developer tools.

   2. **How to get a voice ID:** * Go to the character page on Character AI (for example, [this link](https://character.ai/chat)). * Choose a voice and click the **Share** button. * In the opened window, copy the link. The link will look like: `https://character.ai/?voiceId=2372d060-8401-11ee-b277-020017084944` * Copy the value after `voiceId=` (for example, `2372d060-8401-11ee-b277-020017084944`). * Use this value as the `voice` parameter in the library. 

## Usage Examples
You can use the library in several ways. For simple scripts, use the synchronous method; for async applications, use the `async`/`await` method.

```python
from characterai_tts import TTS

# Create a client (default voice – your_voice_id)
client = TTS(api_token="CHARACTER_AI_TOKEN", voice="your_voice_id")

# 1. Speak with the default voice and save to file
client.say("This is an example created with this class")
```

Note: Sometimes CharacterAI-TTS may not synthesize your expected text. This issue is being worked on.
Special thanks to [PyCharacterAI](https://github.com/Xtr4F/PyCharacterAI) for enabling TTS with Character AI voices. And special thanks to [CharacterAI](https://github.com/kramcat/CharacterAI) for the authentication script.

## Authors
- David Suragan (CharacterAI-TTS)
- Gemini AI

## License
MIT
