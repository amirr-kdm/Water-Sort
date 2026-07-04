# Water Sort

A console-based Java implementation of the **Water Sort** puzzle game, built from scratch on custom data structures instead of Java's built-in collections.

## How it works

- Each bottle is a **stack** (`Stack`/`Node`, a singly linked list of colors) — the top of the stack is the top of the bottle.
- All bottles are chained together in a **circular linked list** (`ClinkedList`), which the game logic (`WaterSortGame`) walks to find, select, and manipulate bottles.
- The board starts from a random color distribution and one empty bottle; the goal is to sort every bottle into a single color.

## Running it

```bash
cd src
javac *.java
java Main
```

On start, enter the space-separated color names followed by the bottle capacity, e.g.:

```
red green blue
3
```

## Commands

| Command | Effect |
|---|---|
| `select <n>` | Select bottle `n` |
| `next` / `previous` | Move the selection to the next/previous bottle |
| `deSelect` | Clear the current selection |
| `pour <n>` | Pour the selected bottle into bottle `n` |
| `swap <n>` | Swap the position of the selected bottle with bottle `n` |
| `replace <c1> <c2>` | Replace every occurrence of color `c1` with `c2` |

The game ends once every non-empty bottle holds a single color.

## Project structure

```
src/
  Main.java           entry point / game loop
  WaterSortGame.java   game rules: selection, pouring, swapping, win check
  ClinkedList.java     circular linked list of bottles
  Stack.java           bottle contents as a stack
  Node.java            linked-list node holding one color
```
