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

| Command   | Description                              |
|-----------|------------------------------------------|
| `while/endwhile`   | while is a loop like always              |
| `while`   | while is a loop like always              |
| `log`     | Logs to X-Plane's log.txt                |
| `set`     | Sets a dataref (e.g., `set ALT 8000`)    |
| `run`     | Runs another script                      |
| `alias`   | Creates a shortcut for a command         |
| `if`      | Conditional execution                    |
| `wait`    | Delays next command by milliseconds      |

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
├── plugins/
├── Scripts/ ← Your custom .xt scripts
├── Resources/
├── LICENSE.txt
└── README.md


---

## 📋 License

This plugin is **free to use** for personal, non-commercial purposes.

- All rights reserved © [Your Name / Brand] 2025  
- Redistribution, reverse-engineering, or modification is **not allowed**  
- Provided “as is” without warranty  

See LICENSE.txt for full terms.

---

## ❓ FAQ

**Q: Is xTerminal open source?**  
No. It is free to use, but the source code is proprietary and not available.

**Q: Can I extend xTerminal?**  
Yes! You can write custom `.xt` scripts or use the scripting API if made available.

**Q: Does it support VR?**  
Not yet, but VR compatibility is on the roadmap.

---

## 🤝 Support & Contact

For feedback, bug reports, or suggestions, please open an Issue or contact:  
📧 your-email@example.com  
🌐 your-website.com

---

## 🚧 Roadmap

- [ ] Script debugger / syntax highlighter  
- [ ] VR support  
- [ ] Remote command execution via TCP  
- [ ] Dataref browser  
- [ ] Full scripting language documentation  

---

Enjoy hacking the skies with **xTerminal** ✈️🖥️
