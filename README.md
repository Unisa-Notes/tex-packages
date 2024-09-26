# Kayzels Tex Packages

This repo contains LaTeX packages that define custom styles and commands that can be used
when writing notes in LaTeX, or an assignment.

## Usage
There are two ways to use these files:
1. Add them directly to the project directory that contains the `tex` files being worked on.
   This requires importing them in a slightly different way — the normal way works,
   but sometimes it will complain on compiling.
   ```tex
   \usepackage{./notestyles}
   ```
2. Add them to your `texmf` directory.
   On Windows, using MiKTex, you can add a custom directory to your `texmf` root directories,
   by opening `MiKTex Console > Settings > Directories`, and then adding a path there.
   I recommend making a directory at `~\texmf`, set with `Generic` purposes.
   Inside that directory, the path needs to be `tex\latex\custom`, but `custom` can be replaced
   with whatever name you want to give the folder.
   After that, they can be imported into a LaTeX file as
   ```tex
   \usepackage{notestyles}
   ```
   Adding the files to your `texmf` directory has the added benefit of allowing LSPs such as [texlab](https://github.com/latex-lsp/texlab),
   and tools such as [vimtex](https://github.com/lervag/vimtex) (if you use Vim or Neovim),
   to find the added commands and environments, which aids in autocomplete.

## Packages Used
TeX packages that have been used are:
- [amsmath, amssymb](https://www.ctan.org/pkg/amsmath): Used for mathematical symbols and environments
- [amsthm](https://ctan.org/pkg/amsthm): Used for the proof environment
- [babel](https://ctan.org/pkg/babel): Use description environment, and chapter renaming
- [caption](https://ctan.org/pkg/caption): Allow captions in non-floating environments
- [changepage](https://ctan.org/pkg/changepage): Allow paragraphs to be indented
- [enumitem](https://ctan.org/pkg/enumitem): Used to improve the way lists are displayed
- [etoolbox](https://ctan.org/pkg/etoolbox): Allow commands to be patched
- [fancyhdr](https://ctan.org/pkg/fancyhdr): Improve header and footer display
- [fontenc](https://ctan.org/pkg/fontenc), [charter](https://ctan.org/pkg/charter), [inconsolata](https://ctan.org/pkg/inconsolata), [cabin](https://ctan.org/pkg/cabin), [newtxmath](https://ctan.org/pkg/newtx), [bm](https://ctan.org/pkg/bm): Font display
- [geometry](https://ctan.org/pkg/geometry): Used for document margins
- [graphicx](https://www.ctan.org/pkg/graphicx): Import images into LaTeX
- [hyperref](https://ctan.org/pkg/hyperref): Add PDF bookmarks
- [parskip](https://ctan.org/pkg/parskip): Set proper default values for paragraph separation
- [subfiles](https://ctan.org/pkg/subfiles): Allow `tex` files to be written separately, but built together
- [tabularray](https://ctan.org/pkg/tabularray): Better table display and management.
  * Also uses libraries to simulate [booktabs](https://ctan.org/pkg/booktabs) and [varwidth](https://ctan.org/pkg/varwidth)
- [tcolorbox](https://ctan.org/pkg/tcolorbox), [adjustbox](https://ctan.org/pkg/adjustbox): Create colored boxes for different environments
- [tikz](https://ctan.org/pkg/tikz): Construct images using LaTeX
- [wrapfig](https://ctan.org/pkg/wrapfig): Used to allow text to wrap around figures
- [xparse](https://ctan.org/pkg/xparse): Better argument parsing for optional arguments
- [xcolor](https://ctan.org/pkg/xcolor): Used to get more colors
- [xstring](https://ctan.org/pkg/xstring): Analyze strings given as arguments to an environment

## Commands Added
### Commands
- `concept{text}`: Marks specific text as a concept to be learned.
  Puts the text in bold.
- `rulebookend`: Insert a decorative horizontal line at the end of the text.
- `rulechapterend`: Insert a decorative horizontal line at the end of each chapter.

### Environments
- `answer`: Indicates an answer to a question, normally in exercises.
  Unbolds the text that is made bold with the question environment.
- `definition[args]{title}`: Creates a definition tcolorbox, with the given title.
  Args are optional, and are extra parameters for the tcolorbox.
- `example[title][args]`: Creates an example tcolorbox.
  Both the title and args are optional, but if both are included, the title must appear
  before the additional arguments.
  ```tex
  % Right
  \begin{example}[Some Title][float]
  \end{example}

  % Wrong
  \begin{example}[float][Some Title]
  \end{example}
  ```
- `descriptenum`: Creates a mix of an enumerate list and a description list.
- `descriptimize`: Creates a mix of an itemize list and a description list.
- `exercise[args]{title}`: Creates an exercise tcolorbox, with the given title.
  Args are optional, and are extra parameters for the tcolorbox.
- `indentparagraph`: Creates an indented paragraph.
- `question`: Indicates a question to be answered, normally in exercises.
- `sidenote[args]{title}`: Creates a sidenote tcolorbox, with the given title.
  Args are optional, and are extra parameters for the tcolorbox.
- `theorem[args]{title}`: Creates a theorem tcolorbox, with the given title.
  Args are optional, and are extra parameters for the tcolorbox.

### Colors
- `example color`: Used for the background in examples
- `example title`: Used for the title background in examples
- `example border`: Used for the border around examples
- `definition color`: Used for the background in definitions
- `definition border`: Used for the border around definitions
- `exercise color`: Used for the background in exercises
- `exercise border`: Used for the border around exercises
- `note color`: Used for the background in sidenotes
- `note border`: Used for the border around sidenotes
- `theorem color`: Used for the background in theorems
- `theorem border`: Used for the border around theorems

---
