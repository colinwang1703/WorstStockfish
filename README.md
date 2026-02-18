<div align="center">

  <h3>WorstStockfish</h3>

  A modified UCI chess engine that plays the worst moves.
  <br>
  <strong>An inverted version of Stockfish for educational and entertainment purposes</strong>

</div>

## Overview

WorstStockfish is a **UCI chess engine** that has been modified to find and play the **worst possible moves** instead of the best ones. This is the opposite of a normal chess engine - it will actively try to lose the game by making the poorest decisions available.

This engine is derived from the Stockfish chess engine but with inverted move evaluation logic. It can be useful for:
- Educational purposes (understanding what NOT to do in chess)
- Entertainment and fun games
- Testing chess GUIs and analysis tools
- Understanding how chess engines work by seeing the inverse behavior

WorstStockfish **does not include a graphical user interface** (GUI) that is required to display a chessboard and to make it easy to input moves. These GUIs are developed independently and are available online. **Read the documentation for your GUI** of choice for information about how to use WorstStockfish with it.

## Files

This distribution of WorstStockfish consists of the following files:

  * [README.md][readme-link], the file you are currently reading.

  * [Copying.txt][license-link], a text file containing the GNU General Public
    License version 3.

  * [AUTHORS][authors-link], a text file with the list of authors for the original Stockfish project.

  * [src][src-link], a subdirectory containing the full source code, including a
    Makefile that can be used to compile WorstStockfish on Unix-like systems.

  * a file with the .nnue extension, storing the neural network for the NNUE
    evaluation. Binary distributions will have this file embedded.

## Compiling WorstStockfish

WorstStockfish has support for 32 or 64-bit CPUs, certain hardware instructions,
big-endian machines such as Power PC, and other platforms.

On Unix-like systems, it should be easy to compile WorstStockfish directly from the
source code with the included Makefile in the folder `src`. In general, it is
recommended to run `make help` to see a list of make targets with corresponding
descriptions. An example suitable for most Intel and AMD chips:

```
cd src
make -j profile-build
```

## How It Works

WorstStockfish uses the same sophisticated search algorithms and position evaluation as Stockfish, but with one critical difference: **the move sorting order is reversed**. Instead of selecting moves with the highest evaluation scores, it selects moves with the lowest scores.

This means WorstStockfish will:
- Prefer losing material over gaining it
- Avoid strong tactical shots
- Choose moves that weaken its position
- Actively seek checkmate against itself

## Terms of use

WorstStockfish is free and distributed under the
[**GNU General Public License version 3**][license-link] (GPL v3). Essentially,
this means you are free to do almost exactly what you want with the program,
including distributing it among your friends, making it available for download
from your website, selling it (either by itself or as part of some bigger
software package), or using it as the starting point for a software project of
your own.

The only real limitation is that whenever you distribute WorstStockfish in some way,
you MUST always include the license and the full source code (or a pointer to
where the source code can be found) to generate the exact binary you are
distributing. If you make any changes to the source code, these changes must
also be made available under GPL v3.

## Acknowledgements

WorstStockfish is based on [Stockfish](https://stockfishchess.org), a free and strong UCI chess engine.

Stockfish uses neural networks trained on [data provided by the Leela Chess Zero
project][lc0-data-link], which is made available under the [Open Database License][odbl-link] (ODbL).


[authors-link]:       https://github.com/official-stockfish/Stockfish/blob/master/AUTHORS
[license-link]:       https://github.com/official-stockfish/Stockfish/blob/master/Copying.txt
[readme-link]:        https://github.com/colinwang1703/WorstStockfish/blob/master/README.md
[src-link]:           https://github.com/colinwang1703/WorstStockfish/tree/master/src
[lc0-data-link]:      https://storage.lczero.org/files/training_data
[odbl-link]:          https://opendatacommons.org/licenses/odbl/odbl-10.txt
