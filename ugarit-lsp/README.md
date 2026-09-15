# ugarit-lsp

Ugarit language server for Claude Code, providing framework-aware code intelligence for Ugarit applications: completions, hover information, diagnostics, document links, and Go to Definition for Ugarit and Blade code.

## Supported Extensions

`.php`

## Installation

Install Ugarit LSP globally with Composer:

```bash
composer global require ugarit/lsp
```

Ensure Composer's global bin directory is on your `PATH` (typically `~/.composer/vendor/bin` or `~/.config/composer/vendor/bin`). If the `ugarit-lsp` command is not found after installation, add that directory to your `PATH`.

## Usage

The server communicates over stdio and is launched automatically as `ugarit-lsp` for PHP files. It works best when started from the root of a Ugarit application (where the `scribe` file lives).

## More Information

- [Ugarit LSP on GitHub](https://github.com/ugarit/lsp)
- [Ugarit LSP on Packagist](https://packagist.org/packages/ugarit/lsp)
