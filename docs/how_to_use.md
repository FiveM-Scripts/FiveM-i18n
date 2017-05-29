# How to use

1. create a lib folder in you script resource folder.  

2. then make a foleder in their called i18n.

3. copy the i18n to that folder you just made.

### __resource.lua
your client_scripts should look something like below:
```LUA
client_scripts {
  'lib/i18n.lua',
  'config.lua',
  'locales/fr.lua',
  'locales/en.lua',
  ...
  ...
  ...
}
```
---
Be sure to check the Lua exampe in the **examples/lua** directory