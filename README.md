# Antex-XM100-Control
Proof of concept HTML/JS page to control the Antex Electronics XM-100 XM Satellite Radio Tuner via serial RS-232 commands.  *Completely vibe coded; works, but please check for accuracy.*

I had an old XM-100 device I wanted to control by RS-232.  I couldn't find any command references online, but I had some souce code of an older program used to control the device.  I used CoPilot to determine the command structure from the source code, and ChatGPT to make the webpage.  Working currently (September 2025) in MS Edge, with a Trendnet TU-S9 v1 USB to Serial Converter with older drivers installed (see https://github.com/theAmberLion/Prolific).

General command structure for the XM-100:

Channel and Preset

    *CH1,###\r — Change channel (### = zero-padded 3-digit channel)
    *PS1,#\r — Recall preset #
    *PS1,#,###\r — Store channel as preset #

Channel/Category Navigation

    *CU1\r — Channel Up
    *CD1\r — Channel Down
    *CGU1\r — Category Up
    *CGD1\r — Category Down

Mute

    *MU1\r — Mute On
    *MU0\r — Mute Off

Power

    *PR1\r — Power On
    *PR0\r — Power Off
    *PR\r — Power status poll

Unsolicited Updates

    *UN1\r — Enable unsolicited updates (can also be used to poll channel, category, artist, song)
    *UN0\r — Disable unsolicited updates




