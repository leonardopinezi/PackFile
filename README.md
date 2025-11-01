# ⚙️ PackFile
**PackFile** is a minimalist automation language focused on **builds, code execution, and system tasks**.
It combines a simple syntax—inspired by Assembly and Batch—with the power of Node.js, allowing you to create **automated, repeatable, and clear scripts**.

---

## 🧠 Concept
With **PackFile**, you can create scripts that:
- Automate **compilations**, **executions**, and **packaging**;
- Control **simple logic flows** (comparisons, jumps, loops);
- Integrate **operating system commands** directly.

---

## 📘 Syntax and Commands

| Command | Syntax | Description |
|----------|----------|-----------|
| `SET` | `SET <VARIABLE> <VALUE>` | Creates or modifies a variable |
| `ECHO` | `ECHO <TEXT>` | Displays a message in the terminal |
| `END` | `END` | Ends the script execution |
| `CLEAN` | `CLEAN` | Clears the console |
| `SUM` | `SUM <NUM1> <NUM2> <VAR>` | Adds two values ​​and stores the result |
| `SUB` | `SUB <NUM1> <NUM2> <VAR>` | Subtracts two values ​​and stores the result |
| `#` | `# <COMMENT>` | Comment — ignored during execution |
| `SPAWN` | `SPAWN <COMMAND>` | Executes an operating system command |
| `IF=` | `IF= <VALUE1> : <VALUE2>` | Executes the next line **only if** the values ​​are equal |
| `IF!=` | `IF!= <VALUE1> : <VALUE2>` | Executes the next line **only if** the values ​​are **different** |

---
## 🧩 Example 1 — “Hello, World!”

```bash
# Defines a variable called MSG with the value "Hello,"
SET MSG Hello,
# Displays the variable (*MSG) and the word "World"
ECHO *MSG World

# Ends the program
END
```

**Exit:**
```
Hello, World
```

---

## 🛠️ Example 2 — Automatic Compilation

```bash
CLEAN
SET SRC main.c
SET OUT app

ECHO Compiling *SRC...
SPAWN gcc *SRC -o *OUT

IF= 0 : 0
    ECHO Compilation completed!

END
```

**Explanation:**
- Defines input and output files
- Compiles C code
- Displays a success message

---

## 💡 Tip

You can **use variables with the `*` prefix** to expand stored values.
### Example:

```bash
SET NAME Leonardo
ECHO Hello *NAME
```
🡒 prints → `Hello Leonardo`

---

## 🧱 Internal Structure
- Developed in **Node.js**
- Script files are named **`PackFile`**
- **Line-based** syntax, easy to interpret and expand
- Support for **labels and jumps** (`:` and `>`)

---

## 🚀 Usage Ideas
- Automate project builds
- Generate reports and logs
- Compile multiple projects sequentially
- Create minimalist DevOps tools
