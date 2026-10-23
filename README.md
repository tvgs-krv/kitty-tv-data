# kitty-tv-data

Данные для приложения Kitty TV на одном телевизоре: список каналов, программа передач, файл версии и APK для самообновления. Ссылки на потоки собраны из открытых плейлистов ([smolnp/IPTVru](https://github.com/smolnp/IPTVru) и другие) и проверены вручную.

| Файл | Что это | Кто меняет |
|---|---|---|
| `config.json` | каналы, их источники, зеркала, тайм-ауты | человек, через `make publish-data` в kitty-tv |
| `epg.json` | программа на двое суток | задача `.github/workflows/epg.yml`, раз в сутки |
| `version.json`, `apk/` | последняя версия приложения | `make publish-apk` в kitty-tv |
| `tools/` | проверка и сборка данных, собрана из kitty-tv | `make publish-tools` в kitty-tv |

Править `config.json` руками можно, но перед пушем проверить: `tools/bin/tools validate .` — тем же кодом файл читает телевизор.
