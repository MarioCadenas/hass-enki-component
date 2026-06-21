# hass-enki-component

Enki custom component for Home Assistant

Tested devices:
- Eglo V-link tunable white
- Inspire Radix ceiling fan with light
- NEW! Solar Panels by Envertech-Lexman
- Inspire Cadix ceiling fan with light

### Dual-light ceiling fans (Cadix / Radix)

Inspire ceiling fans with two independent lights use Enki's per-channel power API
(`switch-channel1-electrical-power` / `switch-channel2-electrical-power`) for on/off.
Brightness and color temperature still use the global lighting API and may affect both lights.
See `doc/api_rest_reference.md` for API details.

Howto :

- install HACS
- add this repo
- add Enki integration

## Live API test

This repository includes a standalone live diagnostics script that can authenticate against Enki
and print available devices/actions from your account. This can help to develop and debug the
component against the real API.

Before running it locally, install runtime dependencies:

```bash
python -m pip install aiohttp
```

Run the script with credentials as parameters:

```bash
python tools/enki_api_live.py --user "your-email@example.com" --password "your-password"
```

You can also use environment variables:

```bash
export ENKI_USER="your-email@example.com"
export ENKI_PASSWORD="your-password"
python tools/enki_api_live.py
```
