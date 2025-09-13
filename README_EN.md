# BoatRaci

**BoatRaci** is a Minecraft (Paper/Purpur) plugin that allows you to organize boat races with checkpoints, rewards, finish effects and full multiplayer gameplay.

---

## 🎮 Introduction

BoatRaci is inspired by classic Minecraft racing minigames, but with expanded features:

- Multiplayer races from 2 to 16 players.
- Customizable tracks with checkpoints.
- Finish effects: fireworks and sounds.
- Various game effects for players during the race.
- Rewards: items, experience, money, commands, messages.
- Ability to spectate other players' races.

---

## 📥 Download

Download the `.jar` file of the plugin and place it in the `plugins` folder of your Paper or Purpur server. After restarting the server, the necessary configs will be created.

---

## ⚙ Configuration

### Main config (`config.yml`)

```yaml
language: ru_RU # Language

license:
  eula-agreed: false # Agreement with the rules
  license-key: "YOUR-LICENSE-KEY-HERE" # Your license key

queue:
  min-players: 2 # Minimum number of players to start
  max-players: 16 # Maximum number of players in the race

race:
  start-time: 5 # Time before the start
  time-to-race: 10 # Time before the start of the race
  checkpoint-cooldown: 3 # Checkpoint cooldown in seconds, from 0 to 60
  match-time: 600 # Match time (sec)
  traffic-light: 2 # After how many seconds do we turn on the traffic light? After start-time

# Starting point
start:
  world: "BOATRACI"
  x: 0.5
  y: 64.0
  z: 0.5
  yaw: 0.0
  pitch: 0.0

# Race items
items:
  race-checkpoint:
    name: "§aTeleport to last checkpoint"
    slot: 0
    item: "STICK"
    glow: true
  race-exit:
    name: "§cLeave race"
    slot: 8
    item: "BARRIER"
    glow: false
  race-effects:
    name: "§bEffects"
    slot: 4
    item: "DIAMOND"
    glow: true

# Any supported particles/effects can be enabled here
# Full list of particles: https://helpch.at/docs/1.21.1/org/bukkit/Particle.html
effects:
FIRE:
  particle: "FLAME" # Particle type
  name: "§6Fire trail" # Effect name in menu
  material: "BLAZE_POWDER" # Item to display in GUI
  slot: 1 # Menu slot
GLOW:
  particle: "END_ROD"
  name: "§fSky glow"
  material: "AMETHYST_SHARD"
  slot: 2
ANGRY:
  particle: "VILLAGER_ANGRY"
  name: "§cRoad storm"
  material: "EMERALD"
  slot: 3
WATER_WAKE:
  particle: "WATER_WAKE"
  name: "§bSea spray"
  material: "WATER_BUCKET"
  slot: 4
CAMPFIRE:
  particle: "CAMPFIRE_COSY_SMOKE"
  name: "§6Campfire smoke"
  material: "CAMPFIRE"
  slot: 5 
ENDERMAN: 
  particle: "SPELL_WITCH" 
  name: "§dPurple Glow" 
  material: "ENDER_PEARL" 
  slot: 6 
GLOW_INK: 
  particle: "GLOW_SQUID_INK" 
  name: "§aRadiance of the Deep" 
  material: "GLOW_INK_SAC" 
  slot: 7 
FIREWORK: 
  particle: "FIREWORK" 
  name: "§fSparks of the Night" 
  material: "FIREWORK_ROCKET" 
  slot: 8 
TRIAL_OMEN: 
  particle: "TRIAL_OMEN" 
  name: "§5Mark of Death" 
  material: "OMINOUS_BOTTLE" 
  slot: 9 
SQUID_INK: 
  particle: "SQUID_INK" 
  name: "§9Squid Ink" 
  material: "INK_SAC" 
  slot: 10 
DRAGON_BREATH: 
  particle: "dragon_breath" 
  name: "§dDragon's Breath" 
  material: "dragon_breath" 
  slot: 11 
SOUL: 
  particle: "SOUL" 
  name: "§5Dead Souls" 
  material: "SOUL_SAND" 
  slot: 12 
SOUL_FIRE_FLAME: 
  particle: "SOUL_FIRE_FLAME" 
  name: "§cFlame from Souls" 
  material: "SOUL_CAMPFIRE" 
  slot: 13 
PORTAL: 
  particle: "PORTAL" 
  name: "§cEcho End" 
  material: "end_portal_frame" 
  slot: 14 
SNEEZE: 
  particle: "SNEEZE" 
  name: "§fStink" 
  material: "WARD_ARMOR_TRIM_SMITHING_TEMPLATE" 
  slot: 15

database:
  type: sqlite # sqlite / mysql
  mysql:
    host: localhost
    port: 3306
    database: boatraci
    username: root
    password: password

# Here you can block interaction with blocks by setting true
# Also you can set up traffic lights for the race
advanced:
  world: "BOATRACI"
  block-use: false
  traffic_light:
    enabled: false
    red:
      x: 0
      y: 70
      z: 0
      block: red_wool
    yellow:
      x: 0
      y: 69
      z: 0
      block: yellow_stained_glass
    green:
      x: 0
      y: 68
      z: 0
      block: emerald_block
    return_block: tinted_glass
```

| Command | Description | Permissions |
| ---------------------- | ---------------------------------------- | ------- |
| `/br start <track>` | Start a race on the selected track | default |
| `/br quickstart` | Auto-select a free track | default |
| `/br spectate <track>` | Spectate a race | default |
| `/br leave` | Leave a race or stop spectating | default |
| `/br list` | List of available tracks | default |

---

| Command | Description | Permissions |
| ---------------------------------- | --------------------------------- | ----- |
| `/bra reload` | Reload plugin | op |
| `/bra setfirework <track> <color>` | Set fireworks | op |
| `/bra setfinishsound <track> <sound>`| Set victory sound | op |
| `/bra createtrack <track name>`| Create new track | op |
| `/bra createracer <track>` | Create racer starting position | op |
| `/bra leaderboard create/move/remove <track>`| Leaderboard management | op |

For Russian, see [README.md](README.md)
