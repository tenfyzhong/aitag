# aitag

Automatically generate meaningful Git tag messages using LLM.

## Installation

1. Using homebrew
```bash
brew install tenfyzhong/tap/aitag
```

## Usage

```bash
aitag [OPTIONS] TAG_NAME [COMMIT]
```

### Options
- `-h, --help` - Show help message
- `-a, --annotate` - Create an annotated tag
- `-s, --sign` - Create a signed tag
- `-u, --local-user USER` - Create tag with specific user
- `--prompt FILE` - Use custom prompt file
- `--model MODEL` - Specify LLM model to use

### Environment Variables
- `LLM_TAG_PROMPT` - Default prompt file path
- `LLM_TAG_MODEL` - Default LLM model to use

### Examples
```bash
aitag v1.0.0                  # Tag HEAD commit as v1.0.0
aitag -a v1.0.0 abc1234       # Create annotated tag for specific commit
aitag --model gpt-4 v1.0.0    # Use gpt-4 model for message generation
LLM_TAG_MODEL=gpt-4 aitag v1.0.0  # Use gpt-4 via environment variable
```

## Shell Completion

Available for:
- [Bash](completions/aitag.bash)
- [Zsh](completions/_aitag)
- [Fish](completions/aitag.fish)

## Prompt Customization

Default prompt file location: `~/.config/prompts/tag-system-prompt.txt`

Example prompt format:
```
Write short commit messages:
- First line should be a short summary
- Blank line after summary
- Explain the 'why' behind changes
- Use bullet points for multiple changes
```

## License

MIT
