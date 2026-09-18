# WeightWatch — Import Cost, Deduplicated (VS Code)

![WeightWatch CI catching a real budget breach](media/cli-demo.svg)
*Real CLI run against a real fixture: `src/dates/` in budget, `src/utils/` 95.8KB over a 20KB cap.*

Inline import sizes that don't lie about shared dependencies.

## The problem it fixes
Import Cost prices two imports of the same package as if you paid for it twice. WeightWatch prices every package **once** across your workspace, attributes it to the first file that imports it, and marks every other import `already paid (see thatFile)`. That statement is true no matter which bundler you use.

## Free
Inline min+gzip size per import line (JS/TS/JSX/TSX) — parity with what you use today, so switching costs nothing.

## Pro ($7 one-time)
The **workspace ledger** (each package priced once, `already paid` annotations, jump-to-first-payer), `.weightwatch.json` per-path budgets, and a self-contained **CI runner** (`node weightwatch-ci.mjs check`) that needs no editor, no npm install, no seat.

## Honest by design
We do **not** claim to match your exact bundle — tree-shaking and chunking are your bundler's job, and chasing parity is a forever-war. The ledger's dedup is bundler-independent and always correct; the byte number is a close approximation.

Made by The Hive.
