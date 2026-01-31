2026-01-31 16:22

Tags: [[mathematics]] [[computation]] [[boolean algebra]] 

------------------------------------------------

### General:
Two statements are logically equivalent if they possess the same boolean values in every single case.
For example, 

The last column in this table possesses the same boolean values as $P \lor Q$, making them logically equivalent.

| *$P$* | *$Q$* | *$\neg P$* | *$\neg Q$* | *$\neg P \land \neg Q$* | *$\neg ( \neg P \land \neg Q )$* |
| ----- | ----- | ---------- | ---------- | ----------------------- | -------------------------------- |
| T     | T     | F          | F          | F                       | T                                |
| T     | F     | F          | T          | F                       | T                                |
| F     | T     | T          | F          | F                       | T                                |
| F     | F     | T          | T          | T                       | F                                |






------------------------------------------------------
### References
Quantum Computing for Everyone - Chris Bernhardt, MIT Press