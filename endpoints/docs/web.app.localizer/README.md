# WebAppLocalizer

## Overview
WebAppLocalizer is a JavaScript class that simplifies the process of localizing web applications. It manages translations, persists language preferences, and provides an optional UI for language selection.

## Installation
Include the WebAppLocalizer script in your HTML file:

```html
<script src="/lollms_assets/js/web.app.localizer"></script>
```

## Usage

### Initialization
Create a new instance of WebAppLocalizer:

```javascript
const localizer = new WebAppLocalizer(translations, localStoragePrefix, languageSelector);
```

Parameters:
- `translations` (required): An object containing translations for different languages.
- `localStoragePrefix` (optional): A string prefix for localStorage keys. Default: 'webAppLocalizer_'.
- `languageSelector` (optional): A DOM element or its ID for the language selector UI.

### Translations Object Structure
```javascript
const translations = {
    en: {
        name: "English",
        translations: {
            "key1": "Translation 1",
            "key2": "Translation 2"
        }
    },
    fr: {
        name: "Français",
        translations: {
            "key1": "Traduction 1",
            "key2": "Traduction 2"
        }
    }
};
```

### Methods

#### setLanguage(lang)
Set the current language.

#### getCurrentLanguage()
Get the current language code.

#### getAvailableLanguages()
Get an array of available languages with their codes and names.

#### translate(key)
Get the translation for a specific key.

#### apply()
Apply translations to all elements with the `data-translate` attribute.

### HTML Usage
Add the `data-translate` attribute to elements you want to localize:

```html
<h1 data-translate="welcome-message"></h1>
<p data-translate="about-us"></p>
```

## Example

```javascript
const translations = {
    en: {
        name: "English",
        translations: {
            "welcome-message": "Welcome to our website!",
            "about-us": "About Us"
        }
    },
    fr: {
        name: "Français",
        translations: {
            "welcome-message": "Bienvenue sur notre site web!",
            "about-us": "À propos de nous"
        }
    }
};

const localizer = new WebAppLocalizer(translations, 'myApp_', document.getElementById('language-selector'));
localizer.apply();
```

This will initialize the localizer, set up a language selector (if provided), and apply translations to your HTML elements.
