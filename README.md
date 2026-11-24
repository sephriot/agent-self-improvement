# agent-self-improvement

One agent skill that runs an improvement round over the instructions you give coding agents. It mines recent Claude Code transcripts and memories for user corrections, decides which rules to remove, refine, relocate, or add, and records a follow-up check for about two weeks later.

## Install

Link the skill directory into each host's skill directory, for example:

    ln -s "$PWD/skills/agent-self-improvement" ~/.claude/skills/agent-self-improvement
    ln -s "$PWD/skills/agent-self-improvement" ~/.agents/skills/agent-self-improvement

The skill sets `disable-model-invocation: true`, so it runs only when invoked, as `/agent-self-improvement` in Claude Code.

## Privacy

Transcripts contain work code, credentials, and customer data. The extractor reads local transcripts and writes no files; keep its output local.

## Test

The extractor needs Python 3 and its standard library only.

    bash tests/extract-user-turns.sh
