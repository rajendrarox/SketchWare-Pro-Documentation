# 🧩 Custom Blocks in Sketchware Pro

> 📱 A complete guide to creating reusable and dynamic custom blocks in **Sketchware Pro**, with a working example for a `Toast` message block.

---

## 📘 Overview

Sketchware Pro supports **Custom Blocks** that allow you to define reusable Java code with visual blocks for use throughout your app. You can create your own blocks, define their inputs, colors, types, and associate them with Java logic—**all without writing repetitive code each time.**

---

## 🧱 Block Structure

Every custom block has two main sections:

### 🧩 Properties

| Field       | Description |
|-------------|-------------|
| `Name`      | Unique block identifier. Example: `Toast` |
| `Type`      | Defines block logic. Use `regular` for simple actions. |
| `Type Name` | Only required for component (`p`) blocks. Optional otherwise. |

### 🎨 Design

| Field         | Description |
|---------------|-------------|
| `Color`       | Set block background color (hex). Example: `#ffffff` |
| `Block Spec`  | Layout and parameters visible in the block (e.g., `Toast %s`) |

---

## 🧠 Supported Spec Codes

| Spec Code | Meaning            |
|-----------|--------------------|
| `%s`      | String input        |
| `%d`      | Number input        |
| `%b`      | Boolean input       |
| `%v`      | Variable            |
| `%m`      | Map or object       |
| `%l`      | List                |
| `%p`      | Component (e.g. Button) |
| `%c`      | Code block (for logic like `if`) |

> 📝 Use `%1$s`, `%2$s`, etc., in Java code to refer to these inputs in order.

---

## 🛠️ Step-by-Step: Creating a `Toast` Block

Follow these steps inside **Sketchware Pro**:

### 🔹 1. Open Block Manager

- Go to ☰ Navigation Bar → `Settings` → `Block Manager`

### 🔹 2. Create a New Pallet

- Tap ➕ button (bottom-right)
- Set:
  - **Pallet Name**: `Operator`
  - **Color**: Any you like (e.g., `#ff9800`)
- Tap ✅ Save

### 🔹 3. Create the Toast Block

- Open the `Operator` pallet
- Tap ➕ icon to add a new block

#### 🔧 Fill in the Block Configuration:

**Properties:**

```
Name      : Toast
Type      : regular
Type Name : toast
```

**Design:**

```
Color     : #ffffff
Block Spec: Toast %s
```

**Java Code:**

```java
Toast.makeText(getApplicationContext(), %1$s, Toast.LENGTH_SHORT).show();
```

> 🔁 `%1$s` refers to the first `%s` input in the Block Spec.

---

## ✅ Using the Toast Block

Once saved, the `Toast` block appears under your `Operator` pallet.

Example usage:

```
[Toast "Hello, Sketchware!"]
```

Internally compiles to:

```java
Toast.makeText(getApplicationContext(), "Hello, Sketchware!", Toast.LENGTH_SHORT).show();
```

---

## 🧪 Advanced Example: Log Block

### Block Spec:

```text
Log %s with tag %s
```

### Java Code:

```java
Log.d(%2$s, %1$s);
```

> ✅ `%1$s` = Message  
> ✅ `%2$s` = Tag

This allows user input like:

```
[Log "Started app" with tag "MainActivity"]
```

---

## 📌 Notes

- Use `%1$s`, `%2$d`, etc., to reference parameters in order.
- Create multiple blocks under a pallet for better organization.
- Avoid duplicate `Name` values across blocks.
- Blocks can be used in any logic area across your app.

---

## 🚀 Benefits

- 🔁 No need to repeat Java code
- ⚡ Faster development
- 📦 Modular & Reusable blocks
- 🎨 Fully visual and customizable

---

## 🙌 Final Thoughts

Using **Custom Blocks** in **Sketchware Pro** boosts your productivity and keeps your code clean. From `Toast` messages to complex operations, this feature brings real power to visual coding.

---

## 🔗 License

Feel free to fork, edit, or improve this guide for your own use or team documentation.

---

> Created with ❤️ by a Android Bulb
