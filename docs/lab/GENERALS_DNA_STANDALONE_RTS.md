# Standalone RTS на базе Generals / Zero Hour GPL engine + WorldBuilder

**Status:** PARKED / LONG-TERM OPTION  
**Captured:** 2026-09-24  
**Domain:** GameDev / RTS / engine & tools  
**Working label:** Generals-DNA Standalone RTS

## Коротко

Идея: использовать официально опубликованный Electronic Arts исходный код **Command & Conquer: Generals + Zero Hour** не как основу обычного мода, а как технический фундамент для **самостоятельной RTS с полностью собственным IP, ассетами, фракциями, UI, звуком, картами и кампанией**.

Главная ценность — не копирование C&C, а повторное использование зрелого RTS-ядра: строительство базы, выделение и управление армиями, экономика, weapons/armor/projectiles, fog of war, pathfinding, AI, skirmish, mission scripting, replay, deterministic multiplayer, INI-driven gameplay и WorldBuilder.

## Ключевая развилка

### Track A — For-fun Zero Hour mod

Самый дешёвый и безопасный путь для эксперимента:

- свои карты;
- новые INI;
- свои units/buildings/factions;
- свои W3D models/textures/sounds;
- свои missions;
- запуск поверх Zero Hour.

Этот трек рассматривается как **бесплатный C&C mod / prototype**.

### Track B — Independent standalone

Отдельная долгосрочная возможность:

```text
Generals source
      ↓
modernized GPL fork
      ↓
remove EA trademarks / assets / proprietary middleware
      ↓
new game data
      ↓
new art + audio + UI + maps
      ↓
standalone executable
```

Критическая техническая цель для такого пути: **EMPTY-ASSET BOOT** — запуск fork без оригинальной C&C install/data, только на собственных runtime assets.

## Почему сейчас это вообще возможно

EA официально выпустила исходный код Generals / Zero Hour под GPLv3 с дополнительными условиями. Репозиторий содержит исходники движка и WorldBuilder.

Полезные upstream:

- EA canonical source: https://github.com/electronicarts/CnC_Generals_Zero_Hour
- EA modding support: https://github.com/electronicarts/CnC_Modding_Support
- EA Modding Guidelines: https://www.ea.com/games/command-and-conquer/news/modding-faq
- active modernization: https://github.com/TheSuperHackers/GeneralsGameCode
- alternative implementation: https://github.com/OpenSAGE/OpenSAGE

## WorldBuilder

WorldBuilder даёт:

- terrain sculpting;
- terrain painting;
- roads;
- water;
- objects;
- waypoints;
- trigger areas;
- build lists;
- mission scripting;
- cameras/cinematics;
- multiplayer map authoring.

На первом этапе его не нужно переписывать.

## Дальняя архитектура

Если эксперимент когда-нибудь вырастет:

- WorldBuilder 2.0;
- JSON/heightmap/road-graph import;
- CLI validation;
- headless AI-vs-AI simulation;
- replay-based regression tests;
- automatic balance metrics;
- natural-language mission DSL;
- procedural campaign layer;
- modernized multiplayer transport;
- Blender → glTF asset pipeline;
- first-class mod packaging.

## Legacy dependencies

Официальный EA source всё ещё несёт старые зависимости:

- DirectX-era SDK;
- STLport;
- 3DS Max SDK;
- NVASM;
- Miles;
- Bink;
- SafeDisc;
- GameSpy;
- legacy compression libraries.

Для for-fun mod это не нужно решать сразу. Для standalone — постепенно заменять.

## Юридическая рамка

- Не удалять `LICENSE.md` и EA notices.
- Не выдавать modified build за официальный EA/C&C release.
- Не использовать EA trademarks для собственного independent product branding.
- C&C mod с использованием C&C assets держать бесплатным.
- Отдельный independent standalone с собственными assets/IP — другой юридический режим; до коммерческого релиза нужен отдельный GPL/IP review.

## Текущий приоритет

Сейчас **не строить standalone engine**.

Текущий практический маршрут:

1. собрать/запустить исходный Zero Hour;
2. поднять WorldBuilder;
3. сделать одну test map;
4. добавить один свой unit;
5. затем один маленький набор собственных gameplay changes;
6. получить первый playable for-fun prototype.

После этого уже решать, есть ли смысл развивать идею дальше.
