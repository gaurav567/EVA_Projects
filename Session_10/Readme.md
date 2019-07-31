<h3>Assignment 10_B</h3>
<h4>It is mentioned that all the convolutions are 3x3x3 filters.

The Conv/2 layer at the beginning of a contracting block has a stride of 2, thus reduces the size of each dimension by half.

Convolution (f,p,s) Input Output RF Jump

Conv1 3,1,0 128x128x96 128x128x96 3x3x3 1

Conv2 3,1,2 128x128x96 64x64x48 5x5x5 2

Conv3 3,1,0 64x64x48 64x64x48 9x9x9 4

Conv4 3,1,2 64x64x48 32x32x24 13x13x13 4

Conv5 3,1,0 32x32x24 32x32x24 21x21x21 8

Conv6 3,1,2 32x32x24 16x16x12 29x29x29 8

End of contracting path

Conv7 3,1,0 16x16x12 16x16x12 45x45x45 16

The jump of RF from 29 to 45 is because the jump value is 16 = 8 x (stride = 2), thus 29 + 16 = 45.</h4>
