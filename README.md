# BoatRaci

**BoatRaci** — это плагин для Minecraft (Paper/Purpur), который позволяет устраивать гонки на лодках с чекпоинтами, наградами, эффектами финиша и полноценным игровым процессом для нескольких игроков.  

---

## 🎮 Введение

BoatRaci вдохновлён классическими гоночными мини-играми Minecraft, но с расширенными возможностями:

- Многопользовательские гонки от 2 до 16 игроков.
- Настраиваемые треки с чекпоинтами.
- Финишные эффекты: фейерверки и звуки.
- Различные игровые эффекты для игроков во время гонки.
- Награды: предметы, опыт, деньги, команды, сообщения.
- Возможность наблюдать за гонками других игроков.

---

## 📥 Загрузка

Скачайте `.jar` файл плагина и поместите его в папку `plugins` вашего сервера Paper или Purpur. После перезапуска сервера создадутся необходимые конфиги.

---

## ⚙ Конфигурация

### Основной конфиг (`config.yml`)

```yaml
language: ru_RU

queue:
  min-players: 2
  max-players: 16

race:
  start-time: 5
  time-to-race: 10
  checkpoint-cooldown: 3
  match-time: 600

start:
  world: BOATRACI
  x: 0.5
  y: 64.0
  z: 0.5
  yaw: 0.0
  pitch: 0.0

items:
  race-checkpoint:
    name: §aТелепорт к последней контрольной точке
    slot: 0
    item: STICK
    glow: true
  race-exit:
    name: §cПокинуть гонку
    slot: 8
    item: BARRIER
    glow: false
  race-effects:
    name: §bЭффекты
    slot: 4
    item: DIAMOND
    glow: true

effects:
  FIRE:
    particle: FLAME
    name: §6Огонь под лодкой
    material: BLAZE_POWDER
    slot: 1
  GLOW:
    particle: END_ROD
    name: §dСвечение
    material: AMETHYST_SHARD
    slot: 2
  ANGRY:
    particle: VILLAGER_ANGRY
    name: §cЯрость
    material: EMERALD
    slot: 3
  # ... остальные эффекты ...
```

| Команда                | Описание                                 |  Права  |
| ---------------------- | ---------------------------------------- | ------- |
| `/br start <track>`    | Начать гонку на выбранном треке          | default |
| `/br quickstart`       | Авто-выбор свободного трека              | default |
| `/br spectate <track>` | Наблюдать за гонкой                      | default |
| `/br leave`            | Покинуть гонку или прекратить наблюдение | default |
| `/br list`             | Список доступных треков                  | default |

---

| Команда                            | Описание                          | Права |
| ---------------------------------- | --------------------------------- | ----- |
| `/bra reload`                      | Перезагрузить плагин              |  op   |
| `/bra setfirework <трек> <цвет>`   | Установить фейерверк              |  op   |
| `/bra setfinishsound <трек> <звук>`| Установить звук победы            |  op   |
| `/bra createtrack <название трека>`| Создать новый трек                |  op   |
| `/bra createracer <трек>`          | Создать стартовую позицию гонщика |  op   |

For English, see [README_EN.md](README_EN.md)

