# NyxAI
-----------

[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https://github.com/ARCANGEL0/NyxAI&count_bg=%234c1&title_bg=%23555555&icon=github.svg&icon_color=%23ffffff&title=Views&edge_flat=false)](https://hits.seeyoufarm.com)
[![GitHub watchers](https://img.shields.io/github/watchers/ARCANGEL0/NyxAI.svg?style=flat-square&color=4c1)](https://github.com/ARCANGEL0/NyxAI/watchers)
[![GitHub stars](https://img.shields.io/github/stars/ARCANGEL0/NyxAI.svg?style=flat-square&color=4c1)](https://github.com/ARCANGEL0/NyxAI/stargazers)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/ARCANGEL0/NyxAI.svg?style=flat-square&color=4c1)](https://github.com/ARCANGEL0/NyxAI/pulls)
[![GitHub issues](https://img.shields.io/github/issues/ARCANGEL0/NyxAI.svg?style=flat-square&color=4c1)](https://github.com/ARCANGEL0/NyxAI/issues)
[![GitHub forks](https://img.shields.io/github/forks/ARCANGEL0/NyxAI.svg?style=flat-square&color=4c1)](https://github.com/ARCANGEL0/NyxAI/network/members)
![Python Version](https://img.shields.io/badge/python-3.10%2B-blue?style=flat-square)

-----------

## About 

NyxAI is a lightweight, fast, and extensible AI assistant for your terminal.  
It supports multiple modes, tidy formatted output in terminal window, persistent chat history, and an optional pentest agent (experimental).

## Features

- **Fast & Lightweight** – Minimal dependencies, instant startup with a single binary.
- **Multiple Modes** – Generic AI chat + Web search, shell commands and execution, code generation & save to file, pentest mode with interactive and autonomous execution.
- **Formatted output** – Easy visualization data on terminal, outputs saved in frames responsive to window size.
- **Persistent History** – Keeps context of chat if used with proper flags. Chat history is saved in ~/.config/NyxAI/chats.json
- **No OpenAI dependencies** – Since I'm motivated by opensource and I don't want to set any API key to use megacorporates AI models, I'm using my personal local model, present in this code, totally modifiable to set your own endpoint or ollama model from *:11434.
 
---

## Installation

Clone the repository and make Nyx globally available:

```bash
git clone https://github.com/arcangel0/NyxAI
cd NyxAI
chmod +x nyx.py
sudo mv nyx.py /usr/bin/nyx
```

## Optional Alias

Sometimes on prompt, a sglob wrapper is necessary and to make command easier for usage, you can append the startup in a simple alias at your .zshrc or .bashrc file.

```bash
alias x="sglob nyx $1"
```

or an automated command to set it to shell alias in a oneliner

```bash
f="$HOME/.${SHELL##*/}rc"; echo 'alias x="sglob nyx $1"' >> "$f" && . "$f"
```

## Usage 

You can call nyx anywhere in your terminal along with a prompt to make a question, you can also pass stdin arguments for Nyx to read.

```bash
cat serverLogs.txt | nyx Analyze these logs and return a solution for it
```

You can also use custom flags for different agent modes in Nyx.

> Usage: v [options] <question or prompt>
> -w, --web         Activate real time web searching
> -c, --code        Tells Nyx to handle code generation, returning a description of code and full code itself, being able to save on disk.
> -s, --shel        Tells Nyx to generate shell commands for specific usage based on prompt, returns a short text and the command to be run at CLI
> -i, --interactive Enters interactive mode and enables chat history, you ask a question and proceed to make a new question in context or quit.
> -a, --auto        (EXPERIMENTAL) Autonomous multi-step cybersecurity mode, pass an initial prompts and let Nyx autorun commands and analyze outputs, and advance to next steps by itself.
> -x, --agent       Manual cybersecurity assistant, analyzes given outputs, handles prompts and deal suggestions with chat history, but not autonomously.
> -r, --reset       Erases the chat history saved in config folder
> -h, --help        Displays the help menu

### Examples
```bash 
$ nyx -s list all files sorted by size # generates a command and asks user if he wants to Run it. 
$ nyx -c Python script to merge two CSV files # generates a short text and full python code, and asks user to copy code or save as a file in local dir.
$ nyx -w Latest CVE for OpenSSL # searches web for all possible index and findings on user prompt (CVE searches)
$ nyx -a Help me in a pentest process, to enumerate this IP 10.10.x.x and get a webshell # Nyx will provide suggestions and commands to be run and ask authorization to run them, after running he will self collect the logs, analyze and suggest next steps and repeat the cycle.
$ nyx -i Tell me about Rutherford atom model # after output, you will have option to ask a new question i.e: ''What about Schrodinger model?'' and continue conversation in context.
$ nyx -x i need help to enumerate 192.168.0.10 for open ports # Nyx will return a small and a list of commands to be run by user, and ask them to retrieve the logs by calling command again, as in example below
$ cat nmapOutput.txt | nyx -x i have run nmap and found these info, what do you suggest now? # Continues conversation saved on chat.json, analyzes nmap output and proceeds to suggest next steps
$ nyx -r # resets all chat history.
```



## Project Note

Not much to say, I just needed an interactive AI to speed up my workflow in terminals, and assist at pentesting or coding and hitting Alt + Tab consistently to navigate through documentations, chatGPT for assistance, among other things can be quite annoying.
And most repo's that offer similar solutions always require an OpenAI key, which I, as a Engineer Grad. student, cannot afford because by tides of destiny, I was born poor.
So I decided to make the same thing released out there but in my own way and code, and using my personal AI from an endpoint at my server. 🐈

---

## ❤️ Support


<div align="center">
  <center> 
    If you enjoy the project and want to support future development:
<br><br>
<a href='https://ko-fi.com/J3J7WTYV7' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://storage.ko-fi.com/cdn/kofi3.png?v=6' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>
<br>
<strong>Hack the world. Byte by Byte.</strong> ⛛
</center>
</div>
