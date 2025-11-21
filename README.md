# Gemini Album Art Generator

This project aims to generate album art for bootleg concert recordings based on metadata that is provided in JSON format.

## Input Format

```
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Concert/Setlist Data Schema",
  "type": "object",
  "properties": {
    "artist": {
      "type": "string",
      "description": "The name of the performing artist."
    },
    "location": {
      "type": "object",
      "description": "Details about the concert location.",
      "properties": {
        "city": {
          "type": "string",
          "description": "The city where the concert took place."
        },
        "venue": {
          "type": "string",
          "description": "The name of the venue."
        },
        "nation": {
          "type": "string",
          "description": "The name of the nation (e.g., 'Germany')."
        },
        "state": {
          "type": "string",
          "description": "The state or region. Can be an empty string."
        },
        "country_or_state": {
          "type": "string",
          "description": "A country or state code (e.g., 'DE')."
        }
      },
      "required": [
        "city",
        "venue",
        "nation",
        "state",
        "country_or_state"
      ]
    },
    "date": {
      "type": "object",
      "description": "The date of the concert.",
      "properties": {
        "year": {
          "type": "integer",
          "description": "The four-digit year."
        },
        "month": {
          "type": "integer",
          "description": "The month (1-12)."
        },
        "day": {
          "type": "integer",
          "description": "The day of the month (1-31)."
        }
      },
      "required": [
        "year",
        "month",
        "day"
      ]
    },
    "setlist": {
      "type": "array",
      "description": "A list of tracks performed in the setlist.",
      "items": {
        "type": "object",
        "properties": {
          "tracknum": {
            "type": "integer",
            "description": "The sequential number of the track in the setlist."
          },
          "title": {
            "type": "string",
            "description": "The title of the song/track."
          },
          "disc": {
            "type": "integer",
            "description": "The disc number (assuming 1 for this data)."
          },
          "unmatched": {
            "type": "boolean",
            "description": "An optional flag, present if the track wasn't fully matched/identified.",
            "default": false
          }
        },
        "required": [
          "tracknum",
          "title",
          "disc"
        ]
      }
    }
  },
  "required": [
    "artist",
    "location",
    "date",
    "setlist"
  ]
}
```
