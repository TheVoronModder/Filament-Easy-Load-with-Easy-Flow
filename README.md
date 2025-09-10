# Filament-Easy-Load-with-Easy-Flow
Filament Loader and Easy Flow


This project is for the Inertia Cube, it can be used for other things too.

Things needed:

Nema 14 Round Pankake stepper
BMG gear set
BMG bearings
servo motor
endstop switch

Smart Extruder

misc. hardware

time



What is it?

An Auto Loader (easy load) and a filament helper through the bowden tube (easy flow), which mimics your extruder speeds.




First thing is first, you need to add this line to your printer.cfg under your "includes" section:

```[include config/elef/elef_master.cfg]```

then add the file above in your printer.cfg area in mainsail / fluidd


how to use?

```ELEF_AUTOLOAD SPEED=300 CHUNK=25 LIMIT=2000 FOLLOW=1```

>[!note]
>
>the ELEF feeder “listens” to the main extruder’s E moves (in mm of filament). As long as each device’s rotation_distance / gear_ratio is set correctly in its own config section, Klipper sends the same E-mm to both—so the ELEF feeder will match whatever toolhead you use (LGX, Orbiter2, etc.) without any hard-coded speeds. The only fixed speed is during the fast prefeed before the tip switch is hit; once arrival is detected and follow mode is on, it self-matches automatically.

>[!tip]
>In elef_master.cfg, make sure:
>
>[extruder] (your toolhead: LGX, Orbiter2, etc.) has its correct rotation_distance (and gear_ratio if you use it).
>
>[extruder_stepper elef_feeder] has BMG-accurate rotation_distance / gear_ratio (since ELEF is always BMG on your build).
>
>Tip: If you ever want the ELEF to “assist less” (e.g., avoid overstuffing during startup on a very grippy toolhead), you can slightly increase the ELEF feeder’s rotation_distance by a couple percent; that makes it push a hair less per E-mm while still staying synced. To revert, set it back to the calibrated value.


> [!note]
> Used for general information or reminders.

> [!tip]
> For hints, shortcuts, or useful suggestions.

> [!important]
> Highlights something critical the user must not miss.

> [!warning]
> Flags potential issues, pitfalls, or risks.

> [!caution]
> Emphasizes that extra care should be taken.

> [!info]
> Generic info block (similar to note).

> [!abstract]
> Summary or overview.

> [!summary]
> Alternative to abstract.

> [!tldr]
> Another alternative to summary.

> [!faq]
> For frequently asked questions.

> [!help]
> For assistance or guidance.

> [!check]
> For task completion, confirmations, or success states.

> [!success]
> Positive outcome messages.

> [!done]
> Another success/completion style.

> [!quote]
> For quotations or external references.

> [!example]
> For code examples, cases, or scenarios.

