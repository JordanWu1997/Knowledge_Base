# VisiData

## Reference

- https://blog.jiayu.co/2021/12/analysing-hdb-resale-flat-transactions-with-visidata/
- https://jsvine.github.io/intro-to-visidata/basics/understanding-columns/
- https://jsvine.github.io/intro-to-visidata/basics/understanding-rows/
- https://jsvine.github.io/visidata-cheat-sheet/en/
- https://www.visidata.org/docs/columns/
- https://www.visidata.org/docs/customize/
- https://www.visidata.org/docs/graph/
- https://www.visidata.org/docs/split/

# Context

## Sheet

- `[Shift]`+`[w]`: Create pivot table sheet
- `[Shift]`+`[m]`: Create a melted sheet
- `[Shift]`+`[t]`: Create a transposed sheet
- `[Shift]`+`[f]`: Create a frequency table sheet of current column
- `[Shift]`+`[i]`: Open statistics sheet
- `[Shift]`+`[v]`: Open visidata menu sheet
- `[Shift]`+`[s]`: Open sheets sheet
  - `[g]`+`[Shift]`+`[s]`: Visit sheet graveyard
- `[Shift]`+`[c]`: Open columns sheet
- `[Shift]`+`[o]`: Open options sheet
- `[Shift]`+`[d]`: Show  VisiData command log
- `[v]`: Open visibility sheet

### Sheet Type

- Sheet types
  - Source Sheet
  - Derived Sheet
  - Meta-sheet

## Basics

- `[Ctrl]`+`[h]`: Open manual
- `[Ctrl]`+`[f]`: Page Down
- `[Ctrl]`+`[b]`: Page Up
- `[q]`: Quit
- `[Ctrl]`+`[q]`: Force-quit
- `[d]`: Delete row
- `[e]`: Edit current cell
- `[a]`: Append new row
- `[i]`: Append new column
- `[h/j/k/l]`: Move left/down/up/right
- `[g]`+`[h/j/k/l]`: Move to the most left/down/up/right
- `[Shift]`+`[u]`: Undo
- `[Shift]`+`[r]`: Redo

## Rows

- `[g]`+`[u]`: unselect all rows
- `[g]`+`[t]`: toggle all selected/unselected
- `[g]`+`[/]`: Search forward all columns
- `[Shift]`+`[']`: Create copy of current sheet but contains only selected rows
- `[Shift]`+`[-]`: Adjust the width of current column to fit text
- `[z]`+`[Shift]`+`[\]`: Select rows where _expr_ evaluates to True

## Columns

- `[g]`+`[v]`: unhide all columns
- `[g]`+`[Shift]`+`[-]`: Adjust the width of all columns to fit text
- `[Shift]`+`[1]`: Mark current column a "key" column
- `[Shift]`+`[6]`: Rename current column

## Sheet Usage

### Sheet Operation

- `[Shift]`+`[s]`: Open sheets sheet
  - `[d]`: Send sheet to sheet graveyard
- `[g]`+`[S]`: Go to sheet graveyard (trash can)
  - `[Enter]`: Revive sheet in graveyard
- `[Shift]`+`[c]`: Show column attributes
  - `[d]`: Delete column
  - `[a]`: Add column

## Table Usage

### Help/Menu

- `[Ctrl]`+`[h]`: Show help menu
- `[z]`+`[Ctrl]`+`[h]`: Show sheet commands
- `[g]`+`[z]`+`[Ctrl]`+`[h]`: Show all commands
- `[Alt]`+`[f]`: Menu - File
- `[Alt]`+`[e]`: Menu - Edit
- `[Alt]`+`[c]`: Menu - Column
- `[Alt]`+`[r]`: Menu - Row
- `[Alt]`+`[d]`: Menu - Data
- `[Alt]`+`[p]`: Menu - Plot
- `[Alt]`+`[s]`: Menu - System

### Navigation

- `[h/j/k/l]`: Go to left/down/up/right
- `[g]`+`[h/j/k/l]`: Go to leftmost/bottom/top/rightmost
- `[z]`+`[r/c]`+`[NUM]`: Jump to row/column number
- `[c]`: Move to column

### Search

- (`[Shift]`)+`[/]`: Regex search (backward)/forward in current column
- `[g]`+(`[Shift]`)+`[/]`: Regex search (backward)/forward in all columns
- (`[Shift]`)+`[n]`: Jump to (previous)/next matching result
- `[c]`: Search column name
- (`[Shift]`)+`[|]`: Unselect/Select row matches the current row

### Undo/Redo

- `[Shift]`+`[u]`: Undo
- `[Shift]`+`[r]`: Redo

### JOIN

- `[&]`: JOIN operation

## Row

### Operation

- `[Shift]`+`[j/k]`: Move current row down/up
- `[{/}]`: Previous/Next selected row

### Pattern Matching

- (`[Shift]`)+`[\]`: (Select)/Unselect rows that matches current column
- (`[g]`)+(`[Shift]`)`[\]`: (Select)/Unselect rows that matches current column

### Expression

## Column

### Column Type

- `[~]`: Set column type to string
- `[#]`: Set column type to integer
- `[%]`: Set column type to float
- `[$]`: Set column type to currency
- `[@]`: Set column type to date
- `[z]`+`[#]`: Set column type to vlen
- `[z]`+`[~]`: Set column type to anytype

### Operation

- `[Shift]`+`[h/l]`: Move current column left/right
- (`[g]`)+`[s]`: Select (all)/current row
- (`[g]`)+`[u]`: Unselect (all)/current row
- (`[g]`)+`[t]`: Toggle (all)/current row selected/unselected

## Miscellaneous

### Row/Column/Cell Operations

- `[i]`: Insert column
- `[s]`: Select
- `[g]`+`[s]`: Select all
- `[d]`: Delete
- `[e]`: Edit current cell
- `[^]`: Rename current column
- `[[]`: Sort ascending
- `[]]`: Sort descending
- `[=]`: Create new column according to expression
- `[z]`+`[i]`: Create new column with interval (e.g. 1,1,1 or 1,2,3)
- `[+]`: Aggregate function

### VisiData 3.0

- `[b]`: Toggle sidebar

### Save as markdown table (github-favored style)

- Change filename from `.csv` to `.github`

### Select column with datetime

- Reference
  - https://github.com/saulpw/visidata/issues/975
- Select column newer than 2024-11-22
  - `<COLUMN_NAME> > datetime.datetime(2024, 11, 22)`

## TODO

### Unorganized Commands

- `[z]`+`[+]`
- `[:]`: split column with delimiter
- `[;]`: capture
- `[(]`: expand
- `[z]`+`[Enter]`
- `[Ctrl]`+`[e]`
- `[</>]`
- `[g]`+`[z]`+`[=]`
