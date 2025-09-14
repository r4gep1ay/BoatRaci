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

Купить - https://boosty.to/boatraci/posts/8d80e6e7-9a5c-4ec7-968f-a441e023d8a3

---

## ⚙ Конфигурация

### Основной конфиг (`config.yml`)

```yaml
language: ru_RU # Язык

license:
  eula-agreed: false # Соглашение с правилами
  license-key: "YOUR-LICENSE-KEY-HERE" # Ваш лицензионный ключ

queue:
  min-players: 2   # Минимальное количество игроков для старта
  max-players: 16   # Максимальное количество игроков в гонке

race:
  start-time: 5        # Время до начала старта
  time-to-race: 10      # Время до начала гонки
  checkpoint-cooldown: 3  # Перезарядка контрольной точки в секундах, от 0 до 60
  match-time: 600          # Время матча (сек)
  traffic-light: 2 # Через сколько секунд запускаем светофор? После start-time

# Начальная точка
start:
  world: "BOATRACI"
  x: 0.5
  y: 64.0
  z: 0.5
  yaw: 0.0
  pitch: 0.0

# Предметы гонки
items:
  race-checkpoint:
    name: "§aТелепорт к последней контрольной точке"
    slot: 0
    item: "STICK"
    glow: true
  race-exit:
    name: "§cПокинуть гонку"
    slot: 8
    item: "BARRIER"
    glow: false
  race-effects:
    name: "§bЭффекты"
    slot: 4
    item: "DIAMOND"
    glow: true

# Здесь можно включать любые поддерживаемые частицы/эффекты
# Полный список частиц: https://helpch.at/docs/1.21.1/org/bukkit/Particle.html
effects: 
  FIRE:
    particle: "FLAME"             # Тип частицы
    name: "§6Огненный след"    # Название эффекта в меню
    material: "BLAZE_POWDER"      # Предмет для отображения в GUI
    slot: 1                       # Слот в меню
  GLOW:
    particle: "END_ROD"
    name: "§fНебесное свечение"
    material: "AMETHYST_SHARD"
    slot: 2
  ANGRY:
    particle: "VILLAGER_ANGRY"
    name: "§cГроза дорог"
    material: "EMERALD"
    slot: 3
  WATER_WAKE:
    particle: "WATER_WAKE"
    name: "§bБрызги моря"
    material: "WATER_BUCKET"
    slot: 4
  CAMPFIRE:
    particle: "CAMPFIRE_COSY_SMOKE"
    name: "§6Дым костра"
    material: "CAMPFIRE"
    slot: 5
  ENDERMAN:
    particle: "SPELL_WITCH"
    name: "§dФиолетовое сияние"
    material: "ENDER_PEARL"
    slot: 6
  GLOW_INK:
    particle: "GLOW_SQUID_INK"
    name: "§aСияние глубин"
    material: "GLOW_INK_SAC"
    slot: 7
  FIREWORK:
    particle: "FIREWORK"
    name: "§fИскры ночи"
    material: "FIREWORK_ROCKET"
    slot: 8
  TRIAL_OMEN:
    particle: "TRIAL_OMEN"
    name: "§5Знак Смерти"
    material: "OMINOUS_BOTTLE"
    slot: 9
  SQUID_INK:
    particle: "SQUID_INK"
    name: "§9Чернила кальмара"
    material: "INK_SAC"
    slot: 10
  DRAGON_BREATH:
    particle: "dragon_breath"
    name: "§dДыхание дракона"
    material: "dragon_breath"
    slot: 11
  SOUL:
    particle: "SOUL"
    name: "§5Мёртвые души"
    material: "SOUL_SAND"
    slot: 12
  SOUL_FIRE_FLAME:
    particle: "SOUL_FIRE_FLAME"
    name: "§cПламя из душ"
    material: "SOUL_CAMPFIRE"
    slot: 13
  PORTAL:
    particle: "PORTAL"
    name: "§cЭхо энда"
    material: "end_portal_frame"
    slot: 14
  SNEEZE:
    particle: "SNEEZE"
    name: "§fСмрад"
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

# Здесь вы можете заблокировать взаимодействие с блоками, установив true
# Также вы можете настроить светофор для гонки
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
| `/bra leaderboard create/move/remove <трек>`| Управление таблицей лидеров       |  op   |

For English, see [README_EN.md](README_EN.md)

