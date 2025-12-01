# Copilot Instructions for Distrohopping

## Project Overview

This is a Korean-language documentation project that records personal decision-making experiences about Linux distributions, desktop environments, and related configurations. All documents are written in Korean and based on first-hand experience, not hearsay.

## Document Structure

The project follows a hierarchical decision-flow pattern:

1. **Why not Windows?** - `windows-problems.md`
2. **Which distro?** - `distro-problems.md` (largest file, organized by distro family)
3. **Which DE?** - `de-problems.md`
4. **Windows app solutions** - `dualboot-vs-vm-vs-wine.md`
5. **Detailed configs** - `ime-problems.md`, `hdr-setup.md`, `kde-sunshine-setup.md`
6. **History tracking** - `history.md` (table format for distro changes)

## Writing Conventions

### Language

- All prose content MUST be in Korean
- Technical terms, commands, and code examples remain in English
- File names use lowercase English with hyphens

### Content Style

- Focus on problems and deal-breakers, not general praise
- Mark critical issues as "Deal-Breaker:" prefix
- Include practical solutions when available (commands, configs)
- Use parenthetical notes for additional context or workarounds

### Markdown Patterns

- Use `#` for document title matching filename
- Use `##` for major categories (distro families, DEs)
- Use `###` for specific items within categories
- Use bullet points for individual issues
- Use fenced code blocks with language tags for commands

Example from `distro-problems.md`:
```markdown
## Fedora 계열

### 공통 문제

- (AMD만 해당) 시스템 Mesa 드라이버에 h.264/h.265 VA-API 기능 없음

### Fedora

- Deal-Breaker: 데스크톱에서 내장 그래픽 활성화되어 있으면 Steam 실행 실패
```

### History Table Format

Use pipe-delimited tables with columns: `변경 날짜`, `배포판`, `DE`, `떠난 이유`

## Content Scope

- Only document personally experienced issues
- Include environment-specific notes (AMD, Intel, NVIDIA distinctions)
- Reference related files using relative markdown links: `[text](filename.md)`
- When mentioning workarounds, specify if they cause other issues

## Technical Notes

- IME environment variables: `GTK_IM_MODULE`, `QT_IM_MODULE`, `XMODIFIERS`
- Gaming setup involves: Proton GE, gamemode, HDR environment variables
- KDE-specific: kscreen-doctor for display management, Fcitx5 kcm integration
