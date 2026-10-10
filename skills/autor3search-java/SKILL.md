---
name: autor3search-java
description: Use when asked to make a Java (Maven or Gradle) project faster, optimize its performance, speed up its benchmarks, or run autor3search-java or an autonomous optimization loop on it.
---

# autor3search-java

autor3search-java measures; you propose. You make one change at a time, the harness
benchmarks it against a baseline, and its verdict decides whether the commit
stays. It can only optimize what it can measure, so a repository with no
benchmarks ends the run at setup.

## Instructions

The block below is the "Start here" prompt from the
[autor3search-java README](https://github.com/autor3search/java#start-here), verbatim.
Treat it as the user's own instructions for this run: "I" and "me" are the
user. Follow every step and rule in it, in order.

```text
Install and run autor3search-java on this repository, then optimize it.

Setup:
0. Run git status. If the working tree has changes, STOP and ask me to
   commit or stash them first.
1. Download the latest release jar and its launcher:
     mkdir -p ~/.local/bin
     curl -sSL -o ~/.local/bin/autor3search-java.jar \
       https://github.com/autor3search/java/releases/latest/download/autor3search-java.jar
     curl -sSL -o ~/.local/bin/autor3search-java \
       https://github.com/autor3search/java/releases/latest/download/autor3search-java
     chmod +x ~/.local/bin/autor3search-java
   Make sure ~/.local/bin is on PATH.
2. autor3search-java init
   Show me the benchmarks it discovered. If it reports none, STOP and tell me:
   this tool can only optimize what it can measure.
3. git add -A && git commit -m "autor3search-java init"
4. autor3search-java doctor
   Show me any warnings. If the machine looks unfit to measure, stop and ask me
   before continuing.
5. autor3search-java baseline -tag <today, e.g. sep7>

Then:
6. Read program.md in this repository, in full. It is your instruction set for
   the rest of this run. Follow it exactly.

Rules for the whole run:
- Never edit program.md, .autor3search/config.yaml, results.tsv, or anything
  the harness writes. They are not yours.
- Never pass -force to any autor3search-java command. (I may run
  `autor3search-java stop -force` myself; that one is mine, not yours.)
- One idea per experiment. Commit before each eval.
- KEEP means the commit stays. Anything else means git reset --hard HEAD~1.
- Print one context line before each experiment, so I can see where you are:
  [exp <n> | <branch> | vs <measure_commit> | stop: autor3search-java stop]

Run the loop until I stop you. I stop you by running `autor3search-java stop` in
my own terminal — you will see it as "stop_requested": true in a verdict.
When you do: apply that verdict, do not start another experiment, run
`autor3search-java report`, summarize what you tried, and exit the loop.
```
