# Collapsable card

Hide a list of cards behind a dropdown.

## Options

| Name       | Type    | Default      | Description                               |
| ---------- | ------- | ------------ | ----------------------------------------- |
| type       | string  |  | `custom:collapsable-card`           |
| cards      | list    |  | List of cards                         |
| head       | card    |  | Card that will be displayed instead of toggle text |
| defaultOpen | string | false | Whether the cards should be visible by default. Can also be set to `desktop-only` to be open by default on desktop and collapsed by default on mobile. Or `contain-toggled` to open only if there are active entities |
| expand_upward | bool | false | Expands the list of cards above the toggle button |
| show_icon | bool | true | Whether the chevron icon should be visible or not |
| content_alignment | string | "justify" | Determines how the content of the toggle button should be aligned.  Options are `left`, `center`, `right`, `justify` and `even`
| title      | string  | "Toggle" | Button title                       |
| buttonStyle| string  | "" | CSS overrides for the dropdown toggle button |

## Installation

# HACS

Add this repository via HACS Custom repositories

https://github.com/HeedfulCrayon/collapsable-card

([How to add Custom Repositories](https://hacs.xyz/docs/faq/custom_repositories/))

# Manually
[In-depth tutorial here](https://github.com/thomasloven/hass-config/wiki/Lovelace-Plugins), otherwise follow these steps:

1. Install the `collapsable-card` card by copying `collapsable-card.js` to `<config directory>/www/collapsable-card.js`

2. On your lovelace dashboard
    1. Click options
    2. Edit dashboard
    3. Click Options
    4. Manage resources
    5. Add resource
        - URL: /local/collapsable-cards.js
        - Resource type: JavaScript module

3. Add a custom card to your dashboard


```yaml
type: 'custom:collapsable-card'
title: Office
cards:
  - type: entities
    entities:
      - entity: light.office_desk_led
      - entity: light.office_led_strips
      - entity: sensor.ross_work_laptop_is_on
    show_header_toggle: false
```

## Development
You can develop this using github codespaces or vscode devcontainers

After starting the container you can run `npm install` to install necessary packages.  Once that completes you can run `npm start` to serve up your custom card.

To start the home assistant container, open a new shell in your devcontainer and run `container start`.

NOTE: if you are using github codespaces, you need to set the WORKSPACE_DIRECTORY variable by running this command first`export WORKSPACE_DIRECTORY=/workspaces/collapsable-card`