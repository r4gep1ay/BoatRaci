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
language: ru_RU

queue:
min-players: 1
max-players: 4

race:
start-time: 5
time-to-race: 10
checkpoint-cooldown: 3
match-time: 600

start:
world: BOATRACI
x: 400.5
y: -17.0
z: 1091.5
yaw: -130.0
pitch: 0.0

items:
race-checkpoint:
name: §aTeleport to the last checkpoint
slot: 0
item: STICK
glow: true
race-exit:
name: §cLeave the race
slot: 8
item: BARRIER
glow: false
race-effects:
name: §bEffects
slot: 4
item: DIAMOND
glow: true

effects:
FIRE:
particle: FLAME
name: §6Fire under the boat
material: BLAZE_POWDER
slot: 1
GLOW:
particle: END_ROD
name: §dGlow
material: AMETHYST_SHARD
slot: 2
ANGRY:
particle: VILLAGER_ANGRY
name: §cRage
material: EMERALD
slot: 3
# ... other effects ...
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

For Russian, see [README.md](README.md)
