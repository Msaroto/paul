# What's it like to code with GPT-4 and aider?

Below are some chat transcripts showing what it's like to code with the help of GPT-4 using the `aider` command-line chat tool.
In the chats, you'll see a varity of coding tasks like generating new code, editing existing code, debugging, exploring unfamiliar code, etc.

* [**Hello World Flask App**](https://aider.chat/examples/hello-world-flask.html): Start from scratch and have GPT create a simple Flask app with various endpoints, such as adding two numbers and calculating the Fibonacci sequence.

* [**Javascript Game Modification**](https://aider.chat/examples/2048-game.html): Dive into an existing open-source repo, and get GPT's help to understand it and make modifications.

* [**Complex Multi-file Change with Debugging**](https://aider.chat/examples/complex-change.html): GPT makes a complex code change that is coordinated across multiple source files, and resolves bugs by reviewing error output and doc snippets.

* [**Create a Black Box Test Case**](https://aider.chat/examples/add-test.html): GPT creates a "black box" test case without access to the source of the method being tested, using only a [high level map of the repository based on ctags](https://aider.chat/docs/ctags.html).

* [**Honor the NO_COLOR env var**](https://aider.chat/examples/no-color.html): The user pastes the NO_COLOR spec from no-color.org into the chat, and GPT-4 modifies the application to conform.

* [**Download, analyze and plot US Census data**](https://aider.chat/examples/census.html): GPT-4 downloads census data, suggests some hypotheses to test, tests one and then summarizes and plots a graph of the results.

* [**Semantic Search & Replace**](semantic-search-replace.md): Updating a collection of function calls, which requires dealing with various formatting and semantic differences in the various function call sites.

* [**Pong Game with Pygame**](pong.md): Creating a simple Pong game using the Pygame library, with customizations for paddle size and color, and ball speed adjustments.

* [**CSS Exercise: Animation Dropdown Menu**](css-exercises.md): A small CSS exercise involving adding animation to a dropdown menu.

* [**Automatically Update Docs**](update-docs.md): Automatically updating documentation based on the latest version of the main() function.

* [**Editing an Asciinema Cast File**](asciinema.md): Editing escape sequences in an `asciinema` screencast file.

## What's happening in these chats?

To better understand the chat transcripts, it's worth knowing that:

  - Each time GPT-4 suggests a code change, `aider` automatically applies it to the source files.
  - After applying the edits, `aider` commits them to git with a descriptive commit message.
  - GPT-4 can only see and edit files which have been "added to the chat session". The user adds files either via the command line or the in-chat `/add` command. If GPT-4 asks to see specific files, `aider` asks the user for permission to add them to the chat. The transcripts contain notifications from `aider` whenever a file is added or dropped from the session.

## Transcript formatting

> This is output from the aider tool.

#### These are chat messages written by the user.

Chat responses from GPT-4 are in a plain font like this, and often include colorized "edit blocks" that specify edits to the code.
Here's a sample edit block that switches from printing "hello" to "goodbye":

```python
hello.py
<<<<<<< ORIGINAL
print("hello")
=======
print("goodbye")
>>>>>>> UPDATED
```
