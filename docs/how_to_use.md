# How to use

## 1. Create the required folders
We recommended to create 2 folders `lib` and `locales` in your script resource folder

#### Example

    resources/myscript/lib
    resources/myscript/locales

## 2. Copy i18n.lua
Then copy ***i18n.lua*** to the "lib" folder

## 3. Create your locales files
Go to the "locales" folder.    
Then create your lang file (for example : en.lua, fr.lua, nl.lua, ..)    

You have to use the `i18n.importData(CodeLang, TranslationTable)` function

| Parameter | Type | Description |
| --------- | ---- | ----------- |
| CodeLang  | string | This will set the locale for example ***"en"*** or ***"fr"***. |
| TranslationTable | array | The key is the identifier of your message, and the value is the message itself. |

## 4 Add the files to your `__resource.lua` file

This can either be client or server side, below is an example:

```LUA
client_scripts {
  'lib/i18n.lua',
  'locales/fr.lua',
  'locales/en.lua',
  'client.lua',
}

server_scripts {
  'lib/i18n.lua',
  'locales/fr.lua',
  'locales/en.lua',
  'server.lua',
}
```

## 5. Configure the default locale
You now have to configure the default language that you want to use.
```Lua
Translator.setLang(CodeLang)
```

CodeLang is a string parameter : it corresponds to the language you want to use in the script (example : "en", "fr", ...)

## 6. You can use the i18n.translate(Key) function in order to use imported locales in your scripts.

Key is a string parameter : it corresponds at a key you have already defined in step 3 (example : "welcome_message")
For your convienence there is a simple but working lua example in **examples/lua** directory which is working with this library.
