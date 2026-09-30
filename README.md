# IMPORTANT NOTICE, READ THIS FIRST.

THIS TOOL IS FOR LEARNING, RESEARCH, DECODING PUBLICLY POSTED ALERTS, AND FICTION SUCH AS FILM AND AUDIO PROJECTS. **DO NOT** TRANSMIT EAS TONES OR GENERATED HEADERS OVER THE AIR, OVER A PHONE OR RADIO SYSTEM, OR INTO REAL EAS EQUIPMENT, AND DO NOT USE THEM TO MISLEAD ANYONE. IN THE UNITED STATES, MISUSING EAS TONES AND SENDING FALSE ALERTS IS ILLEGAL AND CAN CARRY SERIOUS PENALTIES. REAL ALERTS SHOULD ALWAYS COME FROM OFFICIAL SOURCES SUCH AS THE NATIONAL WEATHER SERVICE AND LOCAL EMERGENCY MANAGEMENT.




# SAME Code Decoder & Generator

A single-file, browser-based tool for decoding and generating **SAME (Specific Area Message Encoding)** headers, the data bursts used by the Emergency Alert System (EAS) and NOAA Weather Radio. Everything lives in one HTML file, so there is nothing to install and no server to run.

Made by **Expired**.

## Features

- Decode raw SAME headers (`ZCZC-...`) into plain English: originator, event, locations, duration, issue time, and sending station
- Location lookup using FIPS codes for US states and counties
- Reads VTEC strings (for example `/O.NEW.KGLD.SV.W.0334.260920T2111Z-260920T2200Z/`) alongside the header
- Generator buttons to build SAME headers, UGC strings, VTEC strings, and `ZCZC` headers
- EAS-style audio playback, including the attention tones and end-of-message tones
- Text-to-speech announcement with selectable voices
- Retro EAS-style interface with a pixel font, scanlines, and glowing borders
- Works offline once you have the file

## Download

### Option 1: Download just the file

1. Open the repository page: `https://github.com/pastexpirationdate/EAS-SAME-Code-Encoder-and-Decoder`
2. Click `SAME_Code_Decoder_and_Encoder__BY_EXPIRED.html`
3. Click the **Download raw file** button (the download icon in the top right of the file view)

### Option 2: Clone the repository

```bash
git clone https://github.com/pastexpirationdate/EAS-SAME-Code-Encoder-and-Decoder.git
cd EAS-SAME-Code-Encoder-and-Decoder
```

### Option 3: Download as ZIP

Click the green **Code** button on the repository page, choose **Download ZIP**, and extract it.

## How to run it

Double-click `SAME_Code_Decoder_and_Encoder__BY_EXPIRED.html`, or right-click it and choose **Open with** and pick your browser. That is all. No build step, no dependencies.

On Linux you can also run:

```bash
xdg-open SAME_Code_Decoder_and_Encoder__BY_EXPIRED.html
```

Browsers block audio until you interact with the page, so click somewhere on the page once before trying to play sound.

## How to use

### Decoding a message

1. Paste a SAME header into the input box. You can paste more than one line.
2. Press the decode button.
3. Read the breakdown: who sent it, what the event is, which areas it covers, when it was issued, and how long it lasts.
4. Press the play button to hear it with EAS-style tones and a spoken announcement.

Example header:

```
ZCZC-WXR-SVR-020173+0100-2711845-KICT/NWS-
```

| Part | Meaning |
| :-- | :-- |
| `ZCZC` | Start of message marker |
| `WXR` | Originator (National Weather Service) |
| `SVR` | Event code (Severe Thunderstorm Warning) |
| `020173` | Location: state 20 (Kansas), county 173 (Sedgwick) |
| `+0100` | Valid for 1 hour |
| `2711845` | Issued on Julian day 271 at 18:45 UTC |
| `KICT/NWS` | Sending station |

You can also paste VTEC strings, which NOAA includes in many alert texts, and the tool will decode them.

### Generating a header

1. Pick the generator you want (SAME header, UGC, VTEC, or `ZCZC`).
2. Fill in the fields such as originator, event, locations, duration, and station.
3. Press generate and copy the output.

### Changing the voice

Text-to-speech uses the voices installed on your device and browser, so the list looks different on every system. If the announcement is not in English, pick an English voice from the voice dropdown. If a language you want is missing, install its voice pack in your operating system settings and reload the page.

## Troubleshooting

**No sound plays.** Click on the page first, check your tab and system volume, and make sure the tab is not muted.

**The voice is in the wrong language.** Choose a different voice from the dropdown. Available voices depend on your OS and browser.

**A location shows only as a number.** Some codes, such as marine zones, are not counties and may not be in the FIPS list. Open an issue with the code and it can be added.

**The output does not match an official alert.** Make sure the whole header was pasted, including the trailing `-`.

## Data sources

SAME structure follows the public NOAA / NWS documentation. Example alerts come from publicly posted NOAA data.

## Contributing

Bug reports and suggestions are welcome. Open an issue and include the SAME string that caused the problem and what you expected to see.
