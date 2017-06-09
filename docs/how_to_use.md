# How to use

1. Create a "lib" and a "locales" folder in you script resource folder

2. Copy the i18n.lua file to the "lib" folder

3. Create your locales files in the "locales" folder (for example : en.lua, fr.lua, ...) :
You have to use i18n.importData(CodeLang, TranslationTable) function
* CodeLang is a string parameter : for a english local file, this parameter should be "en" ; for a french local file, this parameter should be "fr"
* TranslationTable is a table parameter, the key is the identifier of your message, and the value is the message itself
Note that you can have more than just one pair key-value = identifier-message

You can have some locales files' examples in the **examples/lua** in order to know how to build your files

4. Don't forget to add the library and all locales files in your __resource.lua - client and/or server side. There's an example :

```LUA
client_scripts {
  'client.lua'
  'lib/i18n.lua',
  'locales/fr.lua',
  'locales/en.lua'
}
```

5. You have now to setup which language you want to use with Translator.setLang(CodeLang)
CodeLang is a string parameter : it corresponds to the language you want to use in the script (example : "en", "fr", ...)

6. In order to use imported locales in your scripts, you can use the i18n.translate(Key) function
Key is a string parameter : it corresponds at a key you have already defined in step 3 (example : "welcome_message")


There is a simple but working lua script example in **examples/lua** directory which is working with this library.
