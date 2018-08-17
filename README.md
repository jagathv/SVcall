# SVcall
lightweight, independent randomized structural variant generation

This is a lightweight alternative to the SVsim randomized variant generation tool (https://github.com/GregoryFaust/SVsim)

More specifically, unlike SVsim, SVcall:

1. Requires only a fasta index file as a reference
2. Generates independent SV's without outputting the whole genome
3. Nondeterministically generates SV start positions, given the same fasta index file

Unlike SVsim, however, SVcall does not emulate the creation of the SV's - it instead outputs non-overlapping coordinates for SV's of given 
lengths distributed across the genome; the point of this is to enable extraction of features of the genome at these coordinates
(rather than features of the SV itself)

# Usage

SVcall requires a list of lengths for created SV's (one length per line) and a fasta index file (can be created from a fasta with samtools faidx).
The line:
```
python SVcall.py [length file] [fasta index file] [output file]
```
will output SV's, sorted within each chromosome by starting index, in tab-separated-value (BED) format to [output_file]
# Queued Improvements
1. Blacklisting (not adding SV's in certain regions of the fasta, specified by an additional input file) 
2. SV simulation (creating the actual SV's in the genome based on the type, as SVsim does, and outputting a mutated fasta)
3. Parallelizing (Currently somewhat slow, especially when creating SV's in larger chromosomes)
