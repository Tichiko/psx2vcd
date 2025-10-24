# 🕹️ PSX2VCD

**PSX2VCD** is a Linux command-line tool that converts **PlayStation 1 BIN/CUE disc images** into **VCD (Virtual CD)** format — perfect for loading games with **PS2 tools** such as **PSBBN**, **HDDOSD**, and **Open PS2 Loader (OPL)**.

This project is a continuation and refinement of the original conversion script created by [gotbletu](https://github.com/gotbletu), with additional quality-of-life improvements, automatic game ID detection, flexible file naming, and batch processing.

---

## ✨ Features

* 🧠 **Automatic PS1 game ID detection**
  Reads from the disc header and appends the proper `SLUS_XXXX.YY` or `SCUS_XXXX.YY` ID automatically.

* 🗁️ **Flexible output naming**
  Files are now named as:

  ```
  Game Name.ID.VCD
  ```

  instead of `ID.Game Name.VCD`.
  Optional brackets around game names are supported.

* ⚙️ **Batch processing**
  Convert all `.cue` files in a directory at once:

  ```bash
  psx2vcd *.cue
  ```

* 💾 **Native Linux support**
  Runs natively on Linux and compatible with WSL for Windows users.

* 🧩 **Integration ready**
  Outputs VCDs compatible with PSBBN, OPL, and HDDOSD setups.

---

## 🧪 Dependencies

These are the tools required to run **PSX2VCD**:

| Type             | Package Name                                       | Source                                      |
| ---------------- | -------------------------------------------------- | ------------------------------------------- |
| System tools     | `coreutils`, `gawk`, `sed`, `psmisc`, `mame-tools` | Official Linux repositories                 |
| Conversion tools | `popstationr`, `cue2pops`                          | [AUR](https://aur.archlinux.org/) or GitHub |

> You can install them on Arch-based systems with:
>
> ```bash
> sudo pacman -S coreutils gawk sed psmisc mame-tools
> yay -S popstationr cue2pops
> ```

---

## 🚀 Installation

### Manual Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/Tichiko/psx2vcd.git
   cd psx2vcd
   ```

2. Make the script executable:

   ```bash
   chmod +x psx2vcd
   ```

3. (Optional) Link it system-wide:

   ```bash
   sudo ln -s "$(pwd)/psx2vcd" /usr/local/bin/psx2vcd
   ```

After that, you can run it from anywhere:

```bash
psx2vcd MyGame.cue
```

---

## 🥪 Usage Examples

Convert a single game:

```bash
psx2vcd "Crash Bandicoot (USA).cue"
```

Convert all `.cue` files in the current directory:

```bash
psx2vcd *.cue
```

Example output:

```
Converting: 'Crash Bandicoot (USA).cue' -> 'Crash Bandicoot (USA).SCUS_949.00.VCD'
Converting: 'CTR - Crash Team Racing (USA).cue' -> 'CTR - Crash Team Racing (USA).SCUS_944.26.VCD'
```

---

## ⚡ Future Plans

* 🎗️ Add Arch Linux AUR package
* 🗾 Add checksum verification for conversions
* 💡 Optional output directory and naming flags

---

## 🤝 Credits

* **Original concept and script:** [gotbletu](https://github.com/gotbletu)
* **Current maintenance and updates:** [Tichiko](https://github.com/Tichiko)

---

## 📜 License

This project is licensed under the **GNU General Public License v3.0 (GPLv3)**.
You are free to use, modify, and distribute this software under the same license.

See [LICENSE](LICENSE) for full details.

---

## 💬 Feedback & Contributions

Pull requests, bug reports, and suggestions are welcome!
If you find a bug or have a feature request, please open an [issue](https://github.com/Tichiko/psx2vcd/issues).

---

> 🤊 *For educational and preservation use only. Please ensure you own the original discs for any game you convert.*
