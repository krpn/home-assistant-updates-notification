# Home Assistant Updates Notification

## Briefly

This is example configuration to get updates notification in a Telegram chat.

Notifies about:

- Core updates
- Supervisor updates
- OS updates
- Supervisor Add-ons updates
- HACS Integrations/Frontend updates
- [Valetudo](https://valetudo.cloud/) Firmware updates

[Lovelace UI card example](#lovelace-ui-card-example) is also available.

## How it looks

![image](https://raw.githubusercontent.com/krpn/home-assistant-updates-notification/master/images/telegram.png)

The links in the message are clickable.

## How to use

1. Copy the contents of the [`secrets.yaml`](https://github.com/krpn/home-assistant-updates-notification/blob/master/secrets.yaml) to your `secrets.yaml` file and change it according to your home configuration
1. Copy the contents of the [`configuration.yaml`](https://github.com/krpn/home-assistant-updates-notification/blob/master/configuration.yaml) to your `configuration.yaml`
    - You can remove any sensors if you don't need some of them (for example, you can remove Valetudo entities if you don't use it)
    - You can change the alert text according to your needs
1. Restart Home Assistant

## Lovelace UI card example

![image](https://raw.githubusercontent.com/krpn/home-assistant-updates-notification/master/images/lovelace.png)

You need to install [Lovelace auto-entities card](https://github.com/thomasloven/lovelace-auto-entities) in order to use the below code.

```yaml
cards:
  - type: custom:auto-entities
    card:
      type: entities
      title: Updates
      state_color: true
    filter:
      include:
        - group: group.updaters
          options:
            secondary_info: last-changed
```
