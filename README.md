<!---
{
  "depends_on": ["https://raw.githubusercontent.com/MaxClerkwell/1b2fb326-d1d7-4c0c-8193-c563871e3707/refs/heads/main/worksheet.tex"],
  "author": "Stephan Bökelmann",
  "first_used": "2025-04-01",
  "keywords": ["ed", "unix", "editor", "cli", "text"]
}
--->

# ed: Editing in a Line-Based World

## 1) Introduction

> Once you've experienced the massive power and time saving advantages of working with the one single editor (no matter what your editing or programming task) you'll wonder how you ever got by without ED! Every programmer, system administrator and PC User could do with some help from ED!
> Imagine the benefits of using the one editor for all your programming languages. From Assembler to VHDL, ED is the one-stop productivity tool that slashes coding time. [...] ED powers up YOUR development environment, without tying you to a particular language or platform.
>
> -- [Gareth Mc Caughan](https://wiki.c2.com/?GarethMcCaughan) on wiki.c2.com 

Long before full-screen editors like `vim`, there was `ed`. It's a line-based text editor that operates without any visual interface — perfect for minimal environments or scripting. While `ed` may seem archaic, learning it will give you a deeper appreciation for Unix philosophy and teach you the fundamentals of how text editors function internally.

In this challenge, you'll:

- Create and modify text files with `ed`
- Understand command structure (addressing, inserting, deleting, replacing)
- Save and quit without seeing the whole file

## 2) Tasks

1. **Start `ed`**

    - Open a terminal and type:

      ```bash
      ed test.txt
      ```

    - `ed` starts silently. To confirm it’s open, type `h` and press Enter. You should see an error message (e.g., `?`) — that’s your prompt.

2. **Insert Text**

    - Enter insert mode by typing:

      ```ed
      i
      Hello world
      This is my first time with ed.
      .
      ```

    - The period `.` ends insert mode.

3. **View Content**

    - To print the buffer:

      ```ed
      1,$p
      ```

    - `1,$` means from line 1 to the last line.

4. **Modify Text**

    - Replace "Hello" with "Greetings":

      ```ed
      1s/Hello/Greetings/
      ```

    - Delete the second line:

      ```ed
      2d
      ```

5. **Append a Line**

    - Append after line 1:

      ```ed
      1a
      This is a new second line.
      .
      ```

6. **Write and Quit**

    - Save and quit:

      ```ed
      w
      q
      ```

## 3) Questions

- Why does `ed` work the way it works, getting one line command and printing only dedicated lines?
- What does the `.` mean in `ed`?
- What happens if you forget the period after insert or append mode?
- How do you delete a specific line?
- What’s the difference between `i` and `a`?
- How can you search for text within the file?
- Why might `ed` be useful in scripts or recovery scenarios?

## 4) Advice

The editor `ed` is unforgiving, but powerful in constrained environments. If you make a mistake, you can always reopen the file and start again. Use line addresses and substitution carefully. Remember: every interaction counts when you don’t have a GUI!

