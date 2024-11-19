# 🤖 HA Text AI for Home Assistant

<div align="center">  

![GitHub release](https://img.shields.io/github/release/smkrv/ha-text-ai.svg?style=flat-square)  
![GitHub downloads](https://img.shields.io/github/downloads/smkrv/ha-text-ai/total.svg?style=flat-square)  
![GitHub stars](https://img.shields.io/github/stars/smkrv/ha-text-ai.svg?style=social)  
![GitHub last commit](https://img.shields.io/github/last-commit/smkrv/ha-text-ai.svg?style=flat-square)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)  
[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg?style=flat-square)](https://github.com/hacs/integration)  
[![Community Forum](https://img.shields.io/badge/Community-Forum-blue.svg?style=flat-square)](https://community.home-assistant.io/t/ha-text-ai-integration)  

</div>

<p align="center">
Transform your smart home experience with powerful AI assistance powered by multiple AI providers including OpenAI GPT and Anthropic Claude models. Get intelligent responses, automate complex scenarios, and enhance your home automation with advanced natural language processing.
</p>

---

## 🌟 Features

- 🧠 **Multi-Provider AI Integration**:
  - Support for OpenAI GPT models
  - Anthropic Claude integration
  - Custom API endpoints
  - Flexible model selection
- 💬 **Advanced Language Processing**:
  - Context-aware responses
  - Multi-turn conversations
  - Custom system instructions
  - Natural conversation flow
- 📝 **Enhanced Memory Management**:
  - Persistent conversation history
  - Context-aware responses
  - Customizable history limits
  - Model-specific filtering
- ⚡ **Performance Optimization**:
  - Efficient token usage
  - Smart rate limiting
  - Response caching
  - Request interval control
- 🎯 **Advanced Customization**:
  - Per-request model selection
  - Adjustable parameters
  - Custom system prompts
  - Temperature control
- 🔒 **Enhanced Security**:
  - Secure API key storage
  - Rate limiting protection
  - Error handling
  - Usage monitoring
- 🎨 **Improved User Experience**:
  - Intuitive configuration UI
  - Detailed sensor attributes
  - Rich service interface
  - Model selection UI
- 🔄 **Automation Integration**:
  - Event-driven responses
  - Conditional logic support
  - Template compatibility
  - Model-specific automation

## 📋 Prerequisites

- Home Assistant 2023.8.0 or newer
- API key from supported providers:
  - OpenAI ([Get key](https://platform.openai.com/account/api-keys))
  - Anthropic ([Get key](https://console.anthropic.com/))
- Python 3.9 or newer
- Stable internet connection

## ⚡ Installation

### HACS Installation (Recommended)  
1. Open HACS in Home Assistant  
2. Click on the three dots in the top right corner  
3. Select "Custom repositories"  
4. Add `https://github.com/smkrv/ha-text-ai` as Integration  
5. Click "Add"  
6. Click on "Integrations" in HACS  
7. Search for "HA Text AI"  
8. Click "Download"  
9. Restart Home Assistant  

### Manual Installation
1. Download the latest release
2. Extract and copy `custom_components/ha_text_ai` to your `custom_components` directory
3. Restart Home Assistant
4. Add configuration via UI or YAML

## ⚙️ Configuration

### Via UI (Recommended)
1. Go to Settings → Devices & Services
2. Click "Add Integration"
3. Search for "HA Text AI"
4. Follow the configuration steps

### Via YAML
```yaml
ha_text_ai:
  api_key: !secret ai_api_key
  model: gpt-3.5-turbo  # or claude-3-sonnet
  temperature: 0.7
  max_tokens: 1000
  request_interval: 1.0
  api_endpoint: https://api.openai.com/v1  # optional, for custom endpoints
  system_prompt: |
    You are a home automation expert assistant.
    Focus on practical and efficient solutions.
```

## 🛠️ Available Services

### ask_question
```yaml
service: ha_text_ai.ask_question
data:
  question: "What's the optimal temperature for sleeping?"
  model: "claude-3-sonnet"  # optional
  temperature: 0.5  # optional
  max_tokens: 500  # optional
  system_prompt: "You are a sleep optimization expert"  # optional
```

### set_system_prompt
```yaml
service: ha_text_ai.set_system_prompt
data:
  prompt: |
    You are a home automation expert focused on:
    1. Energy efficiency
    2. Comfort optimization
    3. Security considerations
    Provide practical, actionable advice.
```

### clear_history
```yaml
service: ha_text_ai.clear_history
```

### get_history
```yaml
service: ha_text_ai.get_history
data:
  limit: 5  # optional
  filter_model: "gpt-4"  # optional
```

[... rest of the README remains the same with updated FAQ section ...]

## 📘 FAQ

**Q: Which AI providers are supported?**
A: Currently OpenAI (GPT models) and Anthropic (Claude models) are supported, with more providers planned.

**Q: How can I reduce API costs?**
A: Use GPT-3.5-Turbo or Claude-3-Sonnet for most queries, implement caching, and optimize token usage.

**Q: Can I use custom models?**
A: Yes, you can configure custom endpoints and use any compatible model by specifying it in the configuration.

**Q: How do I switch between different AI providers?**
A: Simply change the model parameter in your configuration or service calls to use the desired provider's model.

**Q: How can I reduce API costs?**
A: Use GPT-3.5-Turbo for most queries, implement caching, and optimize token usage.

**Q: Is my data secure?**
A: Yes, API keys are stored securely and data is transmitted via encrypted connections.

**Q: Can I use custom models?**
A: Yes, configure custom endpoints and models via configuration options.

## 🤝 Contributing

Contributions welcome! Please read our [Contributing Guide](CONTRIBUTING.md).

1. Fork the repository
2. Create feature branch (`git checkout -b feature/Enhancement`)
3. Commit changes (`git commit -m 'Add Enhancement'`)
4. Push branch (`git push origin feature/Enhancement`)
5. Open Pull Request

## 📝 License

MIT License - see [LICENSE](LICENSE) for details.

---

<div align="center">

Made with ❤️ for the Home Assistant Community

[Report Bug](https://github.com/smkrv/ha-text-ai/issues) · [Request Feature](https://github.com/smkrv/ha-text-ai/issues)

</div>
