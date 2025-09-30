# Simple OpenAI Plugin for Unreal Engine 5

**Simple OpenAI** is a lightweight Unreal Engine 5 plugin that makes it easy to integrate OpenAI’s GPT models into your projects.  
It provides Blueprint-accessible async actions, Actor components for dialogue, and a unified Project Settings panel for configuration.  

The goal: **drop-in access to OpenAI features with minimal setup, no extra boilerplate.**

---

## ✨ Features

- **Project Settings Integration**
  - Configure everything in one place (`Project Settings → Plugins → Simple OpenAI`).
  - Paste your API key.
  - Choose a default model (e.g. `gpt-3.5-turbo`, `gpt-4`).
  - Optionally override with custom model names.
  - Run inline API key validation with "Test API", it will log the response (pings OpenAI `/v1/models`).
  - Shortcut to send feedback/bug reports.

- **Async Blueprint Actions**
  - `Send Chat Message` → Send messages to OpenAI models and get a response.
  - Easy integration into any Blueprint graph.

- **UGPTChatComponent**
  - Attach to any Actor to enable persistent conversations.
  - Supports:
    - Dialogue history (`bSaveDialogueHistory`).
    - Custom **Behavior Prompts** (define how the AI should act).
    - Reset/clear history when needed.
    - Choosing unique OpenAI model other then default chosen in project settings.
  - Great for NPCs, companions, or AI-driven systems.

- **Logging & Debugging**
  - The plugin logs requests and responses at the **VeryVerbose** level.  

---

## 🚀 Setup

1. Clone or download the plugin.  
2. Place it inside your project’s `Plugins/` folder.  
3. Restart Unreal Engine and enable the plugin in **Edit → Plugins**.  
4. Open **Project Settings → Plugins → Simple OpenAI** and paste your API key.  
5. (Optional) Select your default model.
6. Test the API key to see that everything is ready to go.
7. Ready to use all functionalities. 

---

## 🔧 Troubleshooting

### No responses / empty string
- Make sure your **API key** is set in **Project Settings → Plugins → Simple OpenAI**.
- Verify your key is valid by pressing the **Test Key** button in settings.
- Check that you’re using a supported model (e.g. `gpt-3.5-turbo`, `gpt-4`).
- Check that you have balance added on your account hosting the API key. 

### Output Log shows nothing
- The plugin logs at **VeryVerbose** level.  
- To see the logs, enable them in the Output Log or run with: `-LogCmds="LogSimpleOpenAI VeryVerbose`

### Requests failing / network errors
- Ensure you have an active internet connection.
- Some corporate or school networks may block API traffic, test on a personal connection.

### Large responses are cut off
- OpenAI applies **token limits** per model.  
- Use a model with a higher context window.
