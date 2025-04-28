

# CDD: Change Directory Destination
Guillaume Singer

## Motivation:

Anyone who works in a terminal all the time (Linux or even Windows) knows that one of the most frequently used commands is "cd" (change directory). Many people have come up with tools to change the current directory intuitively, the most successful of which is probably zoxide (https://github.com/ajeetdsouza/zoxide), but which doesn't suit my needs.

In my daily work, I've used the cd command a few dozen times (that's about the order of magnitude). I've always found it annoying to have to retype the same paths over and over again, or to search for them in the history. 
By analyzing my use of “cd” and my history, I realized that I was most often moving through fifty or so directories, and that they were almost always the same. 
You can try this out with the command below, which displays the number of times a specific directory is the target of a “cd” command:

```bash
history | grep -E '^[ ]*[0-9]+[ ]+cd ' | awk '{print $3}' | sort | uniq -c | sort -nr
```

From this observation, why not use a mnemonic shortcut to access the most used directories. 
So that's what I did, first for the Windows terminal, years ago, quickly followed by a port to Linux. 
Today cdd is the command I use the most in a console. 
Simple and very efficient.

## Installation:

The source is available here: https://github.com/gsinger/cdd

1. The `cdd_run` file  can be copied anywhere in your system. 
   Don't forget to make it executable (`chmod +x ./cdd_run`)
2. Because the script changes the current directory it cannot be launched in a different bach process from your current session. 
It must be launched by the `source` command. Just add the alias in your `~/.bashrc` file:

```bash
alias cdd='source ~/cdd_run'
```
3. Last step : restart your terminal (or run `source ~/.bashrc`) 

## Usage

Running `cdd` without argument displays the usage of the tool



Then run `source ~/.bashrc` for the alias to be taken into account.

## Why "cdd"

I wanted a short name that was not too far from "cd". My muscle memory is so used to "cd" that adding just a 'd' was the most efficient in terms of speed.