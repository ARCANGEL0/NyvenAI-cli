<div align="center"> 

![Nyven](https://rest.ishanoshada.com/svg/banner/blackhole/Nyven.AI)
 
[![GitHub watchers](https://img.shields.io/github/watchers/ARCANGEL0/NyvenAI-cli.svg?style=flat-square&color=4c1)](https://github.com/ARCANGEL0/NyvenAI-cli/watchers)
[![GitHub stars](https://img.shields.io/github/stars/ARCANGEL0/NyvenAI-cli.svg?style=flat-square&color=4c1)](https://github.com/ARCANGEL0/NyvenAI-cli/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/ARCANGEL0/NyvenAI-cli.svg?style=flat-square&color=4c1)](https://github.com/ARCANGEL0/NyvenAI-cli/network/members)
![Python Version](https://img.shields.io/badge/python-3.10%2B-blue?style=flat-square)

![Stats](https://dynamic-badges.ishanoshada.com/svg/count/5/Repository%20Views/Nyven)





</div> 

-----------

## About 

Nyven.AI is a lightweight, fast, and extensible AI assistant for your terminal.  
It supports multiple modes, tidy formatted output in terminal window, persistent chat history, and an optional pentest agent (experimental).

## Features

- **Fast & Lightweight** – Minimal dependencies, instant startup with a single binary.
- **Multiple Modes** – Generic AI chat + Web search, shell commands and execution, code generation & save to file, pentest mode with interactive and autonomous execution.
- **Formatted output** – Easy visualization data on terminal, outputs saved in frames responsive to window size.
- **Persistent History** – Keeps context of chat if used with proper flags. Chat history is saved in ~/.config/Nyven.AI/chats.json
- **No OpenAI dependencies** – Since I'm motivated by opensource and I don't want to set any API key to use these corporate paid AI models, I'm using my personal local model, present in this code, totally modifiable to set your own endpoint or ollama model from *:11434.
 
---

## Installation

Clone the repository and make Nyx globally available:

```bash
git clone https://github.com/ARCANGEL0/NyvenAI-cli
cd Nyven.AI
chmod +x nyx.py
sudo mv nyx.py /usr/bin/nyx
```

## Optional Alias

Sometimes on prompt, a noglob wrapper is necessary and to make command easier for usage, you can append the startup in a simple alias at your .zshrc or .bashrc file.

```bash
alias x="noglob nyx $1"
```

or an automated command to set it to shell alias in a oneliner

```bash
f="$HOME/.${SHELL##*/}rc"; echo 'alias x="noglob nyx $1"' >> "$f" && . "$f"
```

## Usage 

You can call nyx anywhere in your terminal along with a prompt to make a question, you can also pass stdin arguments for Nyx to read.

```bash
cat serverLogs.txt | nyx Analyze these logs and return a solution for it
```

You can also use custom flags for different agent modes in Nyx.

> Usage: nyx [options] <question or prompt> <br<br>
> -w, --web         Activate real time web searching <br><br>
> -c, --code        Tells Nyx to handle code generation, returning a description of code and full code itself, being able to save on disk. <br><br>
> -s, --shell        Tells Nyx to generate shell commands for specific usage based on prompt, returns a short text and the command to be run at CLI <br><br>
> -i, --interactive Enters interactive mode and enables chat history, you ask a question and proceed to make a new question in context or quit. <br><br>
> -a, --auto        (EXPERIMENTAL) Autonomous multi-step cybersecurity mode, pass an initial prompts and let Nyx autorun commands and analyze outputs, and advance to next steps by itself. <br><br>
> -x, --agent       Manual cybersecurity assistant, analyzes given outputs, handles prompts and deal suggestions with chat history, but not autonomously. <br><br>
> -r, --reset       Erases the chat history saved in config folder <br><br>
> -h, --help        Displays the help menu <br>

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

Not much to say, I just needed an interactive AI to speed up my workflow in terminals, and assist at pentesting or coding and hitting Alt + Tab consistently to navigate through documentations, chatGPT for assistance, among other things can be quite annoying. <br><br>
And most repo's that offer similar solutions always require an OpenAI key, which I, as an Engineer Grad. student, cannot afford because by tides of destiny, I was born poor. <br><br>
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
