---
title: Kangaroo
---

# Kangaroo

```{figure} ../../_static/videos/atari/kangaroo.gif
:width: 120px
:name: Kangaroo
```

This environment is part of the <a href='..'>Atari environments</a>. Please read that page first for general information.

|   |   |
|---|---|
| Action Space | Discrete(18) |
| Observation Shape | (210, 160, 3) |
| Observation High | 255 |
| Observation Low | 0  |
| Import | `gymnasium.make("ALE/Kangaroo-v5")` |

For more Kangaroo variants with different observation and action spaces, see the variants section.

## Description

The object of the game is to score as many points as you can while controlling Mother Kangaroo to rescue her precious baby. You start the game with three lives.During this rescue mission, Mother Kangaroo encounters many obstacles. You need to help her climb ladders, pick bonus fruit, and throw punches at monkeys.

    For a more detailed documentation, see [the AtariAge page](https://atariage.com/manual_html_page.php?SoftwareLabelID=923)

## Actions

Kangaroo has the action space `Discrete(18)` with the table below lists the meaning of each action's meanings.
As Kangaroo uses the full set of actions then specifying `full_action_space=True` will not modify the action space of the environment if passed to `gymnasium.make`.

| Value   | Meaning         |
|---------|-----------------|
| `0`     | `NOOP`          |
| `1`     | `FIRE`          |
| `2`     | `UP`            |
| `3`     | `RIGHT`         |
| `4`     | `LEFT`          |
| `5`     | `DOWN`          |
| `6`     | `UPRIGHT`       |
| `7`     | `UPLEFT`        |
| `8`     | `DOWNRIGHT`     |
| `9`     | `DOWNLEFT`      |
| `10`    | `UPFIRE`        |
| `11`    | `RIGHTFIRE`     |
| `12`    | `LEFTFIRE`      |
| `13`    | `DOWNFIRE`      |
| `14`    | `UPRIGHTFIRE`   |
| `15`    | `UPLEFTFIRE`    |
| `16`    | `DOWNRIGHTFIRE` |
| `17`    | `DOWNLEFTFIRE`  |

## Observations

Atari environment have two possible observation types, the observation space is listed below.
See variants section for the type of observation used by each environment id.

- `obs_type="rgb" -> observation_space=Box(0, 255, (210, 160, 3), np.uint8)`
- `obs_type="ram" -> observation_space=Box(0, 255, (128,), np.uint8)`

Additionally, `obs_type="grayscale"` cause the environment return a grayscale version of the rgb array for observations with the observation space being `Box(0, 255, (210, 160), np.uint8)`
### Rewards

Your score will be shown at the top right corner of the game.
Your end game score with be dependent on how much time you have remaining and who you encounter along the way.
For a more detailed documentation, consult [the AtariAge page](https://atariage.com/manual_html_page.php?SoftwareLabelID=923).

## Variants

Kangaroo has the following variants of the environment id which have the following differences in observation,
the number of frame-skips and the repeat action probability.

| Env-id                       | obs_type=   | frameskip=   | repeat_action_probability=   |
|------------------------------|-------------|--------------|------------------------------|
| Kangaroo-v0                  | `"rgb"`     | `(2, 5)`     | `0.25`                       |
| Kangaroo-ram-v0              | `"ram"`     | `(2, 5)`     | `0.25`                       |
| Kangaroo-ramDeterministic-v0 | `"ram"`     | `4`          | `0.25`                       |
| Kangaroo-ramNoFrameskip-v0   | `"ram"`     | `1`          | `0.25`                       |
| KangarooDeterministic-v0     | `"rgb"`     | `4`          | `0.25`                       |
| KangarooNoFrameskip-v0       | `"rgb"`     | `1`          | `0.25`                       |
| Kangaroo-v4                  | `"rgb"`     | `(2, 5)`     | `0.0`                        |
| Kangaroo-ram-v4              | `"ram"`     | `(2, 5)`     | `0.0`                        |
| Kangaroo-ramDeterministic-v4 | `"ram"`     | `4`          | `0.0`                        |
| Kangaroo-ramNoFrameskip-v4   | `"ram"`     | `1`          | `0.0`                        |
| KangarooDeterministic-v4     | `"rgb"`     | `4`          | `0.0`                        |
| KangarooNoFrameskip-v4       | `"rgb"`     | `1`          | `0.0`                        |
| ALE/Kangaroo-v5              | `"rgb"`     | `4`          | `0.25`                       |
| ALE/Kangaroo-ram-v5          | `"ram"`     | `4`          | `0.25`                       |

## Difficulty and modes

It is possible to specify various flavors of the environment via the keyword arguments `difficulty` and `mode`.
A flavor is a combination of a game mode and a difficulty setting. The table below lists the possible difficulty and mode values
along with the default values.

| Available Modes   | Default Mode   | Available Difficulties   | Default Difficulty   |
|-------------------|----------------|--------------------------|----------------------|
| `[0, 1]`          | `0`            | `[0]`                    | `0`                  |

## Version History

A thorough discussion of the intricate differences between the versions and configurations can be found in the general article on Atari environments.

* v5: Stickiness was added back and stochastic frameskipping was removed. The environments are now in the "ALE" namespace.
* v4: Stickiness of actions was removed
* v0: Initial versions release
