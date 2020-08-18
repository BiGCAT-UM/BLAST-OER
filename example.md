# BLAST​ ​scoring example: nucleotides

In Case 10, the various sequences were nicely aligned: the first nucleotides of both
sequences were at the same alignment position. However, one aspect of making a new
alignment and searching for a match in a database, is that one does not know at the start
which​ ​two​ ​nucleotides​ ​form​ ​that​ ​first​ ​match.

For​ ​example,​ ​given​ ​the​ ​next​ ​two​ ​DNA​ ​sequences:

```
GCATT
​ ​ ​ ​|
CAGTG
```

At first sight, does it not a good overlap. However, if we shift the alignment by one
nucleotide,​ ​it​ ​matches​ ​better:

```
GCATT
​ ​||​ ​|
​ ​CAGTG
```

​​Creating phylogenetic trees, or comparing two alignments (not sequences) in an automatic
manner, one needs a mathematical (numerical) distance. A simple approach would be as
follows: one point for each identical nucleotides, and zero points otherwise. Then, the above
two​ ​alignments​ ​have​ ​1​ ​(T​ ​matching​ ​T)​ ​and​ ​3​ ​points​ ​(CC,​ ​AA,​ ​and​ ​TT​ ​matches),​ ​respectively.

Now,​ ​say​ ​we​ ​have​ ​another​, third ​sequence,​ `​GCTT`.​ ​We​ ​could​ ​then​ ​make​ ​the​ ​following​ ​alignment:

```
GCATT
||​ ​|
GCTT
```

Again, a score of three points.

## Gaps

However, we could also introduce a gap. That is, at some
point an addition or deletion happened, and evolutionary these sequences could be related
via​ ​this​ ​alignment:

```
GCATT
||​ ​||
GC-TT
```

But artibrarily including gaps makes it match nicely, but it should affect the total score. After
all, we can match any sequence if we can introduce gaps without penalties. This is the
background of the gap penalty. Elongation of a gap (making it longer) typically has a lower
penalty than starting a new gap. If the penalty is -1 point, then the last alignment has three
points.​ ​However,​ ​if​ ​the​ ​penalty​ ​is​ ​-2​ ​points,​ ​then​ ​the​ ​alignment​ ​has​ ​4-2=2​ ​points.

