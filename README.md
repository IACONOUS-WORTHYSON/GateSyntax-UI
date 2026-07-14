# GateSyntax

**Right now—users are treated as very rich overgrown toddlers. UI design is broken.**

Even premium apps have UIs that are glitchy and unreliable. Developers waste years fighting boilerplate. There's no reason for this.

**GateSyntax is a gateway between the user and the programmer.**

---

## What It Is

Write a single `.ui` file. It runs natively on **seven platforms** without changing a single character.

```
/SPEED :: 50\

WINDOW Root :: TITLE "My App"
COL    Col  :: IN [Root]

LABEL  SpeedLbl    :: IN [Col] :: TEXT "Speed: " + [SPEED]
SLIDER SpeedSlider :: IN [Col] :: MIN 0 :: MAX 200 :: VALUE [SPEED]
                                :: ON CHANGE /SPEED :: [SpeedSlider]\
BUTTON Reset       :: IN [Col] :: LABEL "Reset" :: ON CLICK /SPEED :: 0\
```

Same file. WPF. PyQt. JavaFX. React. Vanilla DOM. Works everywhere.

The syntax reads like you're talking:
> *"I want a slider from 0 to 200"*  
> `SLIDER Speed :: MIN 0 :: MAX 200`

---

## The Core Idea

- **Simple but effective syntax** — no XML, no JSX, no templates. Just clear, readable declarations.
- **Live bindings** — change a variable, the UI updates instantly. No boilerplate event handlers.
- **True portability** — write once, deploy to desktop, web, mobile, terminal. Same `.ui` file.
- **State-first design** — UI follows data, not the other way around.

---

## Run It Now

| Platform | Language | Run |
|---|---|---|
| WPF (Windows) | C# | `dotnet run` |
| PyQt (Desktop) | Python | `python main.py` |
| JavaFX (Desktop) | Java | `mvn javafx:run` |
| React (Web) | TypeScript | `npm run dev` |
| Vanilla DOM (Web) | TypeScript | `npm run dev` |
| Textual (Terminal) | Python | `python main.py` |

---

## The Integrador

Drop GateSyntax into any running program. Automatically get a live control panel with **zero UI code**.

```python
ig = GateSyntaxIntegrador()

@ig.expose(min=0, max=200)
def speed() -> float: 
    return _speed

@ig.action(label="Reset")
def reset(): 
    _speed = 0

ig.run()
```

Works the same way in C#, Java, TypeScript, and React.

---

## Build Your Own Runtime

This repo includes a **complete build guide**. Paste the prompt at the end of the full README into Claude Code, specify your language and UI toolkit, and get a working GateSyntax runtime.

One `.ui` format. Any language. Any toolkit. Same semantics everywhere.

---

**Designed by Iaconous Worthyson**  
Licensed under `LICENSE.md` as-is. See license for terms.
