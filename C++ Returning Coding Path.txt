Awesome — welcome back to C++ and coding! Since you're rebuilding your skills and looking to **safely build a real-world C++ project (like Prism Launcher)**, I’ll guide you through a solid learning path. Here's a curated list of tutorials and resources — focusing on:

* Modern C++ (C++17/20)
* Real-world projects (like Prism Launcher)
* Safe practices (manual builds, no hidden telemetry)

---

## 🧱 1. **Modern C++ Refresher (Fundamentals)**

### 📘 Online Courses (Free)

* [**LearnCpp.com**](https://learncpp.com/) – 🔥 Best C++ reference from scratch (updated for C++20)
* [**The Cherno - C++ Series on YouTube**](https://youtube.com/playlist?list=PLlrATfBNZ98fqE45g3jZA_hLGUrD4bo6_) – Hands-on + explained clearly
* [**Cpp Reference (quick lookup)**](https://en.cppreference.com/w/) – A bit dense but gold-standard once you're comfy

---

## 🛠️ 2. **CMake & Building Projects (like Prism)**

Since Prism Launcher uses **CMake** + **Ninja**, you’ll need basic fluency here.

### 📘 Tutorials:

* [**CMake Beginner Tutorial** (cmake.org)](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)
* [**Modern CMake Best Practices (YouTube)**](https://www.youtube.com/watch?v=bsXLMQ6WgIk)
* [**Ninja Build System Overview**](https://ninja-build.org/manual.html)

> 💡 *Tip*: If you're used to Makefiles, Ninja is just a faster backend CMake uses.

---

## 🔍 3. **Understand Prism Launcher's Codebase**

Start here:

* [PrismLauncher GitHub](https://github.com/PrismLauncher/PrismLauncher)
* Read `CMakeLists.txt`, `src/launcher`, and `src/instance`
* Most GUI logic is Qt6-based

### 📘 Qt Learning Resources:

* [**Qt 6 Getting Started Guide**](https://doc.qt.io/qt-6/gettingstarted.html)
* [**Qt Widgets Tutorial (C++ GUI)**](https://zetcode.com/gui/qt6/)
* [**Official Qt Docs**](https://doc.qt.io/qt-6/index.html)

---

## 🧪 4. **Safe Sandbox C++ Practice Projects**

Try rebuilding these from scratch to practice:

* **Console Minecraft launcher** (offline mode, launches Minecraft via CLI)
* **Qt GUI: Simple App Launcher**
* **JSON parser tool** using [nlohmann/json](https://github.com/nlohmann/json) (used in Prism)

---

## 🛡️ 5. **Secure Your Build Environment**

* Use **Firejail** or **toolbox** to sandbox
* Consider compiling in a **VM** (e.g. Arch/Endeavour in a VirtualBox)
* Check binaries with `ldd`, `strace`, or `nm` if extra paranoid

---

## 📁 Bonus: Git & Source Navigation

* [Pro Git Book](https://git-scm.com/book/en/v2)
* Learn to use `git grep`, `git blame`, `git log -p` to trace C++ logic changes

---

## Want a Hands-on Path?

I can create:

* A small custom C++ project just for you (e.g. minimal Minecraft-like launcher)
* An annotated walkthrough of Prism's structure
* Practice tasks + review if you want feedback

Would you like a "learning plan" style roadmap for C++ + CMake + Qt based on how many hours per week you're spending?
