# SVcall
lightweight, independent randomized structural variant generation

This is a lightweight alternative to the SVsim randomized variant generation tool (https://github.com/GregoryFaust/SVsim)

More specifically, unlike SVsim, SVcall:

1. Requires only a fasta index file as a reference
2. Generates independent SV's without outputting the whole genome
3. Nondeterministically generates SV start positions, given the same fasta index file

Unlike SVsim, however, SVcall does not emulate the creation of the SV's - it instead outputs coordinates for SV's of given 
lengths distributed across the genome; the point of this is to enable extraction of features of the genome at these coordinates
(rather than features of the SV itself)

# Queued Improvements
1. Blacklisting (not adding SV's in certain regions of the fasta, specified by an additional input file) 
2. SV simulation (creating the actual SV's in the genome based on the type, as SVsim does, and outputting a mutated fasta)
