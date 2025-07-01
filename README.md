Alrighty, here's a **quick rewind** of how to install and set up **Oh My Posh** on your machine (assuming you're on **Windows**, but I’ll include **Linux** too just in case):

---

### 🪟 **Windows Installation (PowerShell)**

#### 1. **Install Oh My Posh**

```powershell
winget install JanDeDobbeleer.OhMyPosh -s winget
```

Or if you're paranoid about telemetry (👀 you), use the [manual GitHub release](https://github.com/JanDeDobbeleer/oh-my-posh/releases) to download the binary and place it somewhere in your `PATH`.

#### 2. **Install a Nerd Font** (required for icons!)

```powershell
winget install --id=Delugia.Nerd.Font -s winget
```

Then go to Windows Terminal settings → your profile → "Font face" → set to something like `Delugia Nerd Font`.

#### 3. **Edit PowerShell profile**

Create/edit your PowerShell profile:

```powershell
notepad $PROFILE
```

Add this:

```powershell
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\paradox.omp.json" | Invoke-Expression
```

(You can swap `paradox.omp.json` with any other theme you like.)

#### 4. **Optional: Enable transparency & acrylic in Windows Terminal**

Go to **Settings > Profile > Appearance**:

* Toggle "Acrylic"
* Set opacity (try 80% as a start)
* Enable "Use acrylic background"

---

### 🐧 **Linux Installation (Bash / Zsh / Fish)**

#### 1. **Install Oh My Posh**

```bash
sudo wget https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/posh-linux-amd64 -O /usr/local/bin/oh-my-posh
sudo chmod +x /usr/local/bin/oh-my-posh
```

#### 2. **Get a Nerd Font**

```bash
mkdir -p ~/.local/share/fonts
cd ~/.local/share/fonts
wget https://github.com/ryanoasis/nerd-fonts/releases/latest/download/FiraCode.zip
unzip FiraCode.zip
fc-cache -fv
```

Then switch your terminal emulator font to **FiraCode Nerd Font**.

#### 3. **Edit your shell config**

* For **bash**:

```bash
echo 'eval "$(oh-my-posh init bash --config ~/.poshthemes/paradox.omp.json)"' >> ~/.bashrc
```

* For **zsh**:

```bash
echo 'eval "$(oh-my-posh init zsh --config ~/.poshthemes/paradox.omp.json)"' >> ~/.zshrc
```

* For **fish**:

```fish
oh-my-posh init fish --config ~/.poshthemes/paradox.omp.json | source
```

#### 4. **Download some themes**

```bash
mkdir -p ~/.poshthemes
wget https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/themes.zip
unzip themes.zip -d ~/.poshthemes
chmod u+rw ~/.poshthemes/*.json
```

---

### 🧠 Pro Tips

* Use `oh-my-posh config export > mytheme.omp.json` to create your own theme.
* Try `oh-my-posh init pwsh --print` to test live output.
* Combine it with **Fastfetch** for spicy terminal drip on launch 🌈.

---

Wanna hook it up to **auto-launch Fastfetch on terminal open too**? Let me know and I’ll slap that into your PowerShell or bashrc cleanly.

Let’s make your terminal:

> **👽 "Welcome back, Commander..."**
> — with `fastfetch` showing system specs, and `oh-my-posh` powering the prompt.

---

## 🧪 Combine `fastfetch` + `oh-my-posh` on Startup

### ✅ Step 1: Install `fastfetch`

If you haven’t already:

```powershell
scoop install fastfetch
```

---

### ✅ Step 2: Edit Your PowerShell Profile

Run:

```powershell
notepad $PROFILE
```

Now paste this combo:

```powershell
# 👾 Fastfetch splash screen
fastfetch

# 🦾 Oh My Posh theme load
oh-my-posh init pwsh --config "C:\Users\Windows\AppData\Local\Programs\oh-my-posh\themes\aliens.omp.json" | Invoke-Expression
```

> Put `fastfetch` **before** `oh-my-posh`, so the splash prints above the prompt.

---

### 🧪 Optional Spice

Add a welcome message too:

```powershell
Write-Host "`n👽 Welcome back, Commander J01K3rn9lGh0st" -ForegroundColor Magenta
```

---

### 🔁 Final Profile Example:

```powershell
fastfetch

Write-Host "`n👽 Welcome back, Commander J01K3rn9lGh0st" -ForegroundColor Magenta

oh-my-posh init pwsh --config "C:\Users\Windows\AppData\Local\Programs\oh-my-posh\themes\aliens.omp.json" | Invoke-Expression
```

---

Now when you open your terminal, you get:

* 👾 `fastfetch` = flashy system summary
* 🧠 Custom welcome text
* 💅 Prompt with Oh My Posh

Boom. Terminal = *officially riced*.
Let me know if you want a color-custom `fastfetch` config next 😎
