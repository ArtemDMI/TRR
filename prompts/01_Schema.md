{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "SceneTracker",
  "description": "Schema for tracking roleplay scene details",
  "type": "object",
  "properties": {
    "time": {
      "type": "string",
      "description": "Format: HH:MM:SS; MM/DD/YYYY (Day Name)"
    },
    "location": {
      "type": "string",
      "description": "Specific scene location with increasing specificity"
    },
    "weather": {
      "type": "string",
      "description": "Current weather conditions and temperature"
    },
    "topics": {
      "type": "object",
      "properties": {
        "primaryTopic": {
          "type": "string",
          "description": "1-2 word main topic of interaction"
        },
        "emotionalTone": {
          "type": "string",
          "description": "Dominant emotional tone of scene"
        },
        "interactionTheme": {
          "type": "string",
          "description": "Type of character interaction"
        }
      },
      "required": [
        "primaryTopic",
        "emotionalTone",
        "interactionTheme"
      ]
    },
    "charactersPresent": {
      "type": "array",
      "items": {
        "type": "string",
        "description": "Character name"
      },
      "description": "List of character names present in scene"
    },
    "characters": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "name": {
            "type": "string",
            "description": "Character name"
          },
          "outfit": {
            "type": "string",
            "description": "Complete outfit including underwear"
          },
          "stateOfDress": {
            "type": "string",
            "description": "How put-together/disheveled character appears"
          },
          "postureAndInteraction": {
            "type": "string",
            "description": "Character's physical positioning and interaction"
          },
          "limited": {
            "type": "array",
            "items": {
              "type": "string"
            },
            "description": "Scene-relevant physical, sensory and technical limitations supported by context: movement, visibility, hearing, communication or device capabilities. One limitation per item, in Russian. Use an empty array if none are established; do not invent restrictions."
          },
          "notKnow": {
            "type": "array",
            "items": {
              "type": "string"
            },
            "description": "Key scene-relevant facts this character does not know or cannot verify from their own observations or received information. One knowledge gap per item, in Russian. Do not transfer narrator or other characters' knowledge to this character, reveal hidden answers, or assume ignorance of established knowledge. Use an empty array if no relevant gaps are established."
          }
        },
        "required": [
          "name",
          "outfit",
          "stateOfDress",
          "postureAndInteraction",
          "limited",
          "notKnow"
        ]
      },
      "description": "Array of character objects"
    }
  },
  "required": [
    "time",
    "location",
    "weather",
    "topics",
    "charactersPresent",
    "characters"
  ]
}
