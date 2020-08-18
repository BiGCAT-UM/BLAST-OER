# BLAST​ ​scoring example: proteins

Comparing proteins is different from comparing nucleotide sequences. Basically, nucleotides
are the same or they are not. However, for amino acids this is more different. First of all,
some amino acids are encoded by more than one codon. Second, not every amino acid change
changes the protein structure and biological function a lot.

For example, the following two protein sequences can be aligned like this without
introducing a gap:

```
MLGDSAVLGT
||||||.|||
MLGDSAILGT
```

## Substition matrices: PAM and BLOSUM


