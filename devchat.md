# devchat

- DevChat: Open-source AI tool for prompt-centric development
- Goes beyond code auto-completion, uses diverse context
- Highly customizable, utilizes maximum AI power
- Shift from traditional code-centric methods, offers user
  customization control

<!-- end list -->

    ~/.chat/mamba/envs/devchat/lib/python3.11/site-packages/devchat

    ./
    ├── ./assistant.py
    ├── ./chat.py
    ├── ./_cli/
    │   ├── ./_cli/__init__.py
    │   ├── ./_cli/log.py
    │   ├── ./_cli/main.py
    │   ├── ./_cli/prompt.py
    │   ├── ./_cli/run.py
    │   ├── ./_cli/topic.py
    │   └── ./_cli/utils.py
    ├── ./engine/
    │   ├── ./engine/command_parser.py
    │   ├── ./engine/__init__.py
    │   ├── ./engine/namespace.py
    │   └── ./engine/recursive_prompter.py
    ├── ./__init__.py
    ├── ./message.py
    ├── ./openai/
    │   ├── ./openai/__init__.py
    │   ├── ./openai/openai_chat.py
    │   ├── ./openai/openai_message.py
    │   └── ./openai/openai_prompt.py
    ├── ./prompt.py
    ├── ./store.py
    └── ./utils.py

    3 directories, 22 files
    (base)

## Workflows

    github.com/devchat-ai/workflows

    .
    ├── code
    │   ├── command.yml
    │   ├── prompt.txt
    │   └── py
    │       ├── command.yml
    │       └── prompt.txt
    ├── commit_message
    │   ├── command.yml
    │   └── prompt.txt
    ├── LICENSE
    ├── README.md
    └── release_note
        ├── command.yml
        └── prompt.txt

## components

- prompt (yaml)
- command (text)

## prompt

```yaml
description: Generate code with a Python-specific template embedded into the prompt.
```

## command

````text/plain
As a software developer assistant, your tasks are to:

- Provide a clear and concise response to address the user's requirements.
- Write code and give advice based on given code or information in the <context> if provided.
- Follow language-specific best practices and common coding standards.

When responding:

1. First summarize the requirements or provided information in your own words.
The summary should better be written in bullet points (excluding code).
1. When modifying the provided code, include the entire modified functions, but exclude any unmodified functions.
If any global statements are changed, include the full global statements; otherwise, do not include them.
1. Enclose code or changes within blocks using triple backticks (```), and include the programming language and the file path.

For example:
```python path=./path/to/file.py
print("Hello, World!")
````

Do your best to deduce the file path based on the given or previous
messages. If you are still uncertain about the file path of the code,
feel free to omit it.

1.  Use separate code blocks for different files.
2.  When providing a suggestion or instruction, begin by explaining the
    reason behind it.
3.  You may not receive all the direct information needed for your task.
    Analyze the given to understand how existing code was written, and
    use this knowledge for your task.
4.  Note that not all previous messages or contexts are necessarily
    relevant.
5.  Respond in the language of the request.

You may encounter duplicate or conflicting messages or contexts, and the
later ones should be considered as the most accurate. If you need more
information, ask for it. \`\`\`
(base)
