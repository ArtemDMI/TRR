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
    "envaroment": {
      "type": "string",
      "description": "One shared description in Russian of the visible surroundings of the current scene, at most 150 words, in a concise, factual dungeon-master style. Describe established nearby objects, their condition, spatial relationships, visible paths and obstacles at the end of the latest message. Use only details supported by context; do not invent scenery, reveal hidden areas, narrate actions, or list topics and emotions. This scene overview does not imply that every character has noticed everything described."
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
    "envaroment",
    "charactersPresent",
    "characters"
  ]
}
