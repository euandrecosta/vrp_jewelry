<div align="center">

# vRP Jewelry

A legacy jewelry store robbery system developed for FiveM and vRP.

![Lua](https://img.shields.io/badge/Lua-2C2D72?style=flat-square\&logo=lua\&logoColor=white)
![FiveM](https://img.shields.io/badge/FiveM-Resource-F40552?style=flat-square)
![vRP](https://img.shields.io/badge/Framework-vRP-444444?style=flat-square)
![Status](https://img.shields.io/badge/Status-Legacy%20Project-6c757d?style=flat-square)

</div>

> [!NOTE]
> **Early project — originally developed around 2020.**
>
> This repository is part of my early programming journey.
>
> The repository is preserved to document my technical evolution and does not represent my current coding standards.

---

## About

**vRP Jewelry** is a jewelry store robbery resource developed for FiveM servers using the vRP framework.

The resource implements a complete robbery flow involving security system hacking, police requirements, synchronized showcases, animations, effects, randomized rewards and cooldown management.

It represents one of the more complex systems from my early FiveM development period.

---

## Features

* Jewelry store robbery flow
* Security system hacking sequence
* Minimum police requirement
* Required hacking item
* Weapon requirement to initiate the robbery
* Police alerts
* Temporary police map blip
* Jewelry showcase interactions
* Multiple showcase positions
* Character robbery animations
* Glass-breaking particle effects
* Sound effects
* Showcase model synchronization
* Randomized jewelry rewards
* Individual showcase cooldowns
* Global robbery cooldown
* Client/server state synchronization
* vRP inventory integration

---

## Robbery Flow

The original implementation follows approximately this flow:

```text
Player reaches the hacking point
        ↓
Server validates robbery requirements
        ↓
Security system hacking starts
        ↓
Robbery state is activated
        ↓
Police players are alerted
        ↓
Jewelry showcases become available
        ↓
Player breaks individual showcases
        ↓
Random jewelry items are rewarded
        ↓
Cooldowns prevent immediate repetition
```

---

## Original Requirements

### Police

The robbery requires more than two players with:

```text
policia.permissao
```

which means at least **3 police officers** must be available.

### Hacking item

The player must have:

```text
pendrive
```

in their inventory.

### Weapon

The original client implementation requires either an assault rifle or an SMG when starting the interaction.

---

## Rewards

The original implementation randomly selects jewelry from:

```text
relogioroubado
pulseiraroubada
anelroubado
colarroubado
brincoroubado
```

The amount rewarded is randomized by the server.

These items must exist in the server's vRP inventory configuration.

---

## Cooldowns

The original system includes two levels of cooldown.

### Robbery cooldown

After a robbery starts, the jewelry store uses a global recovery period of approximately:

```text
3600 seconds
```

or **1 hour**.

### Showcase cooldown

Individual showcases also maintain their own timers before they can be interacted with again.

---

## Police Alert

When the robbery starts, police players receive:

* an alert;
* an interface sound;
* a temporary map blip;
* the jewelry store location.

The original implementation uses:

```text
policia.permissao
```

to identify police players.

---

## Tech Stack

| Technology             | Usage                            |
| ---------------------- | -------------------------------- |
| Lua                    | Client and server logic          |
| FiveM                  | Runtime and GTA V natives        |
| vRP                    | Users, permissions and inventory |
| Tunnel / Proxy         | Client-server communication      |
| GTA V Scaleforms       | Hacking interface                |
| GTA V particle effects | Showcase effects                 |

---

## Integrations

The original resource also interacts with server-specific events/resources such as:

```text
Notify
progress
vrp_sound
```

Depending on the server base, these integrations may need to be replaced or adapted.

---

## Requirements

The resource was created for an older vRP-based FiveM server.

Required or expected integrations include:

```text
vRP
Notify
progress
vrp_sound
```

Additional adaptations may be necessary for other server bases.

---

## Installation

Place the resource inside the FiveM resources directory:

```text
resources/
└── vrp_jewelry/
```

Add:

```text
start vrp_jewelry
```

to the server configuration.

Ensure that the required inventory items, permissions and integrations exist in your server.
