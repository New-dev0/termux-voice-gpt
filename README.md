# ai-control v1
Using GPT-4 to remotely execute code on my smartphone is a smart idea, surely. 

## [Video Demo (*YouTube*)](https://youtu.be/0evGdb2RLDY)

# features
Can do anything exposed in the Termux API. Also includes a few utility tools in `UtilTools.py` (so far just a `sleep` tool). **Not all of these have been tested, so please open an issue if you find something not working.**

* BatteryStatusTool
* BrightnessTool
* PhotoTool
* ClipboardGetTool
* ClipboardSetTool
* FingerprintTool
* LocationTool
* MediaPauseTool
* RecordMicTool
* NotificationTool
* ListNotificationsTool
* URLOpenerTool
* TorchTool
* SpeakTool
* GetVolumeTool
* SetVolumeTool
* WiFiInfoTool
* WiFiScanTool
* VibratorTool
* MediaPlayTool

# Limitations

* not good at performing multiple actions in sequence, that will be fixed in v2

# Future ideas

Ngl I'm writing this for myself. Sorry if I get too verbose with it.

* executing shell commands
* scheduling events for the future
* change `main.py` to `chatbot.py`, expose an interface. then make a new `main.py` with a CLI to run either the agent, chat, or both.
* add an option, for when running chat from a Termux environment (or when running both - as it must be a Termux environment), to **use Termux speech to text and vice versa** instead of typing to the bot

# setup/installation
Make a copy of `.env.example` named `.env` and set the following keys:

* `OPENAI_API_KEY` - from [OpenAI](https://platform.openai.com)
* `TERMUX_AGENT_URL` - the URL of where the termux agent is running
    * If you're running the termux agent and the controller on the same device, you can skip this step as it defaults to `http://localhost:8080`
    * Otherwise, it's just `http://` + your phone's IP address + `:8080` for the port

For the agent device, make sure you have the Termux-API app installed along with the interface. To install the interface, run `pkg install termux-*` from within a termux session.

# usage
1. Run `termux-agent.py` on your android device
2. Run `main.py` on the device you want to control it from
3. You will enter a chat session (when you see the prompt: `> `), type and send messages with enter. By default, the chatbot shows verbose output so that you can view the commands it is running.