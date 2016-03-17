# MyLZW

Builds on standard LZW compression algorithm by varying the size of the output/input codewords from 9 to 16 bits and can be run in three modes do nothing, reset, and monitor. In do nothing mode when the codebook is full (all 16 bit codewords have been used) the program continues to use the full codebook. In reset mode when the codebook is full, it is reset to empty so new codewords can be added. In minitor mode initially nothing is done (keep using the full codebook) but begin monitoring the compression ratio after no more 16 bit codewords remain. Define the compression ratio to be the size of the original data that has been consumed so far divided by the size of the (compressed) output data produced so far. If the compression ratio degrades by more than a set threshold from the point when the last codeword was added then reset the dictionary to empty. To run the compression from the command line enter for example "java MyLZW - r < foo.txt > foo.lzw" where r is reset mode, n is do nothing mode, and m is monitor mode. To expand the same example file "java MyLZW + < foo.lzw > foo2.txt"
