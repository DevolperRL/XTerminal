# xTerminal

**xTerminal** is a powerful in-sim terminal for X-Plane, designed to simulate a Linux-like command-line environment within the simulator. It uses its own custom scripting language, allowing users to create commands, automate simulator tasks, and interact with the sim environment in real time.

> ⚠️ xTerminal is free to use but not open source. Redistribution or modification is not allowed without explicit permission.

---

## ✨ Features

- 🖥️ In-sim terminal interface  
- 🧠 Custom lightweight command language (interpreted)  
- 🔧 Create your own commands and scripts  
- 🎮 Interact with X-Plane datarefs and commands  
- 🧩 Plugin-based architecture for extendability  
- 📝 Script execution and inline command input    
- 🚀 Fast, sandboxed execution for in-sim safety  

---

## 📦 Installation

1. Download the latest release from the Releases section.
2. Extract the `xTerminal` folder into your `X-Plane 12/Resources/plugins/` directory.
3. Start X-Plane and the terminal will appear as a new plugin menu item:  
   Plugins → xTerminal → Open Terminal

---

## 🛠️ Language Overview

xTerminal uses its own custom scripting language designed to be minimal, fast, and safe.

### Example Commands

CreateCommand({"ClimbTest"}, call = (
    set(alt, 0)
    while(alt < 3000)
        log("Climbing... alt is ${alt}")
        set(alt, alt + 1000)
    endwhile
    if(alt >= 3000)
        log("Reached altitude.")
    else
        log("Still climbing...")
    endif
))


### Built-in Commands

| Shortcut   | Description                              |
|-----------|------------------------------------------|
| `...`   | anything/something              |
| `s`     | string              |
| `n`     | name     |
| `dtf`     | dataref                      |
| `v`   | value         |
| `cmd`      | command                    |
| `i`      | int number                    |
| `f`      | float number                    |
| `db`      | double number                    |

| Command   | Description                              |
|-----------|------------------------------------------|
| `while(...)/endwhile`   | while is a loop like always              |
| `log(s)`     | logs to X-Plane's log.txt and terminal              |
| `set(n, v)`     | create a variable     |
| `get(n, dtf)`     | get a dataref value                      |
| `setf(dtf, v)/sets(dtf, v)/setsa(dtf, v)/setfa(dtf, v)`   | set a dataref value, each letter is the type, like f is float or s is string or a is array         |
| `if(...)/endif`      | conditional execution                    |
| `wait(n)`    | delays next command by milliseconds      |
| `to_float(v)`    | convert to float      |
| `to_int(v)`    | convert to int      |
| `to_string(v)`    | convert to string      |
| `command(cmd)`    | find and run once a command      |
| `reloadScenery()`    | reload scenery      |
| `reloadPlugins()`    | reload plugins      |
| `getMagneticVariation(db lat, db lon)`    | get the magnetic variantion      |
| `degTrueToDegMagnetic(f hdg)`    | deg to deg magnetic      |
| `degMagneticToDegTrue(f hdg)`    | deg magnetic to deg      |
| `setUsersAircraft(s path)`    | change the plane of the user      |
| `placeUserAtAirport(s icao)`    | change the airport of the user      |
| `placeUserAtLocation(db lat, db lon, f MSL, f hdg, f speed)`    | place the user at location      |
| `findFirstNavAid(n)`    | place the user at location      |

### Built-in Language Elements

| Elements   | Description                              |
|-----------|------------------------------------------|
| `+ / * - `   | basic math              |
| `== != <= >= < >`     | operators              |
| `[i]`     | arrays     |
| `${v}`     | this is used for log to get the variable value                      |
| `__tmp`   | this is used for to_string() after converted it, you will need to do a set and put __tmp for the converted string         |
| `args[i]`      | this is the argument someone pass on the terminal i shoud be a int number                   |


More language documentation coming soon in the Wiki.

---

## 🧪 Creating Custom Commands

You can define your own commands using `alias` or by placing scripts in the `Scripts/` folder inside the plugin directory.

Example:

alias climb "set VS 1000; set THRUST 90"


Then simply run:


---

## 📁 Folder Structure

xTerminal/

├── xTerminal/

├── scripts/ ← Your custom .or scripts

---

## 📋 License

This plugin is **free to use** for personal, non-commercial purposes.

- All rights reserved © Raoul Origa 2025  
- Redistribution, reverse-engineering, or modification is **not allowed**  
- Provided “as is” without warranty  

See LICENSE.txt for full terms.

---

## ❓ FAQ

**Q: Is xTerminal open source?**  
No. It is free to use, but the source code is proprietary and not available.

**Q: Can I extend xTerminal?**  
Yes! You can write custom `.or` scripts or use the scripting API if made available.

---

Enjoy hacking the skies with **xTerminal** ✈️🖥️
