# Language Support & Localization

---
- **Language Doc [English](Language.md) | [中文](Language_zh.md)**

MI2U provides a powerful and dynamic language selection system, making it easier for players to experience the game in their native tongue without restarting.

---

# Features

## Auto-Detection
- **Timezone-based Default**: Automatically detects your system's timezone on the first launch and sets the most appropriate language (e.g., `Asia/Shanghai` sets to `zh_CN`).
- **Fallback Support**: Safely defaults to English (`en`) if the system timezone cannot be resolved to a specific language.

## Real-time Switching
- **No Restart Required**: Instantly reloads the language bundle using `I18NBundle`. Most UI text and game elements will update immediately upon selection.
- **Vanilla Integration**: Works seamlessly with Mindustry's native language system and settings architecture.

## Comprehensive Support
- **Multi-Language Ready**: Fully supports all official Mindustry language codes, including Simplified Chinese, Japanese, Korean, Russian, German, French, Brazilian Portuguese, and Vietnamese.

---

# How to Use

1. Open the **Settings** menu in-game.
2. Locate the new section titled **"Language"**.
3. Click the dropdown menu and select your preferred language from the list.
4. The changes will apply instantly.

---

# Technical Details

- **Storage**: The selected language is saved directly in the vanilla settings file under the key `"locale"`.
- **Dynamic Reloading**: When a new language is selected, MI2U dynamically reconstructs `Core.bundle` using `arc.util.serialization.I18NBundle.createBundle()`. It also updates the default Java `Locale` via `Locale.setDefault()` to ensure all subsequent UI generation uses the correct language context.

---

# Contribution Guidelines (Localization)

We highly appreciate community translations! If you want to add or improve a translation, please follow these rules:
- **Base Template**: Always use the latest `ZH_CN` or `EN_US` properties file as your base template.
- **Consistent Fields**: Maintain the exact casing, placeholders (e.g., `{0}`), and order of the keys. 
- **Line Structure**: Preserve the original file line structure where possible to prevent merge conflicts.
- **Testing**: Test your translation in-game to ensure no UI text overflows or breaks.
