---
tags:
  - "original"
context:
  - "[[Daggerheart]]"
  - "[[Warrior Philosopher]]"
---

# A Daggerheart Story

Story about a learner in a mysterious land.

---

```json
{
  "name": "Doni",

  "ancestry": {
    "type": "Human",
    "features": ["High Stamina", "Adaptability"]
  },

  "community": {
    "type": "Wildborne",
    "features": ["Lightfoot"]
  },

  "class": {
    "type": "Warrior",
    "domains": ["Blade", "Bone"],
    "features": {
      "hope": "No Mercy",
      "class": ["Attack of Opportunity", "Combat Training"]
    },

    "subclass": {
      "type": "Call Of The Slayer",
      "features": {
        "foundation": "Slayer"
      }
    }
  },

  "skills": ["Strategic Approach", "Untouchable", "I See It Coming"],

  "level": 2,
  "proficiency": 2,

  "health": 7,
  "stress": 7,

  "stats": {
    "agility": 3,
    "strength": -1,
    "finesse": 0,
    "instinct": 1,
    "presence": 0,
    "knowledge": 2
  },

  "experience": {
    "scholar": 2,
    "tactician": 2,
    "truthseeker": 2
  },

  "defense": {
    "evasion": 13,
    "armor": {
      "score": 3,
      "thresholds": [8, 15]
    }
  },

  "offense": {
    "primary": {
      "trait": "Agility",
      "range": "Melee",
      "damage": "d8 d8 +6 +2 +2 physical or magical"
    }
  },

  "equipment": {
    "armor": {
      "name": "Leather Armor",
      "thresholds": [6, 13],
      "score": 3,
      "feature": null
    },

    "weapons": {
      "primary": {
        "name": "Ghostblade Longsword",
        "trait": "Agility",
        "range": "Melee",
        "damage": "d8 +6 physical or magical",
        "burden": "Two-Handed",
        "feature": "Levels tier with holder tier"
      },

      "secondary": {
        "name": "Shortsword",
        "trait": "Agility",
        "range": "Melee",
        "damage": "d8 physical",
        "burden": "One-Handed",
        "feature": "Paired: +2 to primary weapon damage to targets within Melee range"
      }
    }
  },

  "backpack": [
    {
      "name": "Shortbow",
      "trait": "Agility",
      "range": "Far",
      "damage": "d6 +3 physical",
      "burden": "Two-Handed",
      "feature": null
    },
    {
      "name": "Tower Shield",
      "trait": "Strength",
      "range": "Melee",
      "damage": "d6 physical",
      "burden": "One-Handed",
      "feature": "Barrier: +2 to Armor Score; -1 to Evasion"
    }
  ],

  "gold": {
    "handfulls": 1,
    "bags": 0,
    "chests": 0
  },

  "inventory": [
    {
      "name": "Faerie Talisman",
      "info": "Gift from the faeries as a token of friendship."
    },
    {
      "name": "Skeleton Key",
      "description": "When you use this key to open a locked door, you gain advantage on the Finesse Roll.",
      "info": "Found near the ancient skeleton throne."
    },

    {
      "name": "Broken Crown",
      "info": "Looted from the remains of one reckless and yet heroic dwarf."
    },
    {
      "name": "Sharpening Stone"
    },

    {
      "name": "Longsword",
      "trait": "Agility",
      "range": "Melee",
      "damage": "d8 +3 physical",
      "burden": "Two-Handed",
      "feature": null
    },
    {
      "quantity": 2,
      "name": "Broadsword",
      "trait": "Agility",
      "range": "Melee",
      "damage": "d8 physical",
      "burden": "One-Handed",
      "feature": "Reliable: +1 to attack rolls"
    },

    {
      "quantity": 2,
      "name": "Basic Supplies"
    },
    {
      "name": "Torch"
    },
    {
      "name": "Rope"
    },
    {
      "quantity": 2,
      "name": "Skull"
    },

    {
      "name": "Minor Stamina Potion",
      "description": "Clear 1d4 Stress."
    },
    {
      "name": "Varik Leaves",
      "description": "You can eat these paired leaves to immediately gain 2 Hope."
    },
    {
      "quantity": 2,
      "name": "Snap Powder",
      "description": "Mark a Stress and clear a HP."
    },

    {
      "name": "Minor Stamina Potion Recipe",
      "description": "As a downtime move, you can use the bone of a creature to craft a Minor Stamina Potion."
    },
    {
      "name": "Vial of Darksmoke Recipe",
      "description": "As a downtime move, you can mark a Stress to craft a Vial of Darksmoke."
    }
  ]
}
```
