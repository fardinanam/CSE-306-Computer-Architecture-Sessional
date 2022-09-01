# CSE-306-Computer-Architecture-Sessional
This is a repository containing all the simulations and reports of CSE-306 Computer Architecture Sessional.

## 4 bit ALU
**This ALU contains:**
- Two 4 bit inputs A and B
- Three select bits S<sub>2</sub>, S<sub>1</sub>, S<sub>0</sub> as ALU opcodes
- One 4 bit output
- Four flags: Z (Zero), C (Carry), O (Overflow), N (Negative)
### Implemented functions and opcodes:
<table class="tg">
<thead>
  <tr>
    <th class="tg-c3ow" colspan="3">ALU opcodes</th>
    <th class="tg-c3ow" rowspan="2">Functions</th>
  </tr>
  <tr>
    <th class="tg-c3ow">S<sub>2</sub></th>
    <th class="tg-c3ow">S<sub>1</sub></th>
    <th class="tg-c3ow">S<sub>0</sub> (C<sub>in</sub>)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">Transfer A</td>
  </tr>
  <tr>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">Increment A</td>
  </tr>
  <tr>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">X</td>
    <td class="tg-c3ow">AND</td>
  </tr>
  <tr>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">Add</td>
  </tr>
  <tr>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">Add with carry</td>
  </tr>
  <tr>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">X</td>
    <td class="tg-c3ow">OR</td>
  </tr>
</tbody>
</table>

### Truth table:
<table class="tg">
<thead>
  <tr>
    <th class="tg-c3ow" colspan="3">ALU opcodes</th>
    <th class="tg-c3ow" rowspan="2">Required outputs</th>
    <th class="tg-c3ow" colspan="3">Adder inputs</th>
    <th class="tg-c3ow" rowspan="2">Functions</th>
  </tr>
  <tr>
    <th class="tg-c3ow">S<sub>2</sub></th>
    <th class="tg-c3ow">S<sub>1</sub></th>
    <th class="tg-c3ow">S<sub>0</sub> (C<sub>in</sub>)</th>
    <th class="tg-c3ow">X<sub>i</sub></th>
    <th class="tg-c3ow">Y<sub>i</sub></th>
    <th class="tg-0pky">Z<sub>i</sub></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">A</td>
    <td class="tg-c3ow" rowspan="2">A<sub>i</sub></td>
    <td class="tg-c3ow" rowspan="2">0</td>
    <td class="tg-0pky" rowspan="2">C<sub>i</sub></td>
    <td class="tg-c3ow">Transfer A</td>
  </tr>
  <tr>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">A + 1</td>
    <td class="tg-c3ow">Increment A</td>
  </tr>
  <tr>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow" rowspan="2">A ^ B</td>
    <td class="tg-c3ow" rowspan="2">A<sub>i</sub>B<sub>i</sub></td>
    <td class="tg-c3ow" rowspan="2">0</td>
    <td class="tg-0pky" rowspan="2">0</td>
    <td class="tg-c3ow" rowspan="2">AND</td>
  </tr>
  <tr>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">1</td>
  </tr>
  <tr>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">A + B</td>
    <td class="tg-c3ow" rowspan="2">A<sub>i</sub></td>
    <td class="tg-c3ow" rowspan="2">B<sub>i</sub></td>
    <td class="tg-0pky" rowspan="2">C<sub>i</sub></td>
    <td class="tg-c3ow">Add</td>
  </tr>
  <tr>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">A + B + 1</td>
    <td class="tg-c3ow">Add with carry</td>
  </tr>
  <tr>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow" rowspan="2">A OR B</td>
    <td class="tg-c3ow" rowspan="2">A<sub>i</sub>B<sub>i</sub>'</td>
    <td class="tg-c3ow" rowspan="2">B<sub>i</sub></td>
    <td class="tg-0pky" rowspan="2">0</td>
    <td class="tg-c3ow" rowspan="2">OR</td>
  </tr>
  <tr>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">1</td>
  </tr>
</tbody>
</table>

### Simplified inputs to individual full adders:
X<sub>i</sub> = A(S<sub>1</sub>' + S<sub>2</sub> XOR B)

Y<sub>i</sub> = S<sub>2</sub>B

Z<sub>i</sub> = S<sub>1</sub>'C<sub>i</sub>

### Circuit diagram:
![4 bit ALU circuit diagram](1%20-%204%20bit%20ALU/4%20bit%20ALU%20circuit%20diagram.png)

## Floating Point Adder
The adder takes two 32 bit floating point numbers and adds them together. The numbers are represented in the following format:

|  Sign | Exponent |        Fraction        |
|:-----:|:--------:|:---------------------:|
| 1 bit |  10 bits | 21 bits (Lowest bits) |

The numbers are in normalized form. There are two flags U (underflow) and O (overflow) which are set if the result is too small or too large to be represented in the format.

### Flow chart:
![Floating point adder flow chart](2%20-%20Floating%20Point%20Adder/floating_point_adder_flowchart.svg)

### Circuit diagram:
![Floating point adder circuit diagram](2%20-%20Floating%20Point%20Adder/floating_point_adder_circuit_diagram.png)

### What individual components do:
- **Sign check**: Checks if a 32 floating point number is positive, negative or the exponent is zero. If the number is positive then the output is the same as input. If the number is negative then it outputs the two's complement of the input. And if the exponent is zero then the output is zero.
- **Normalizer**: Normalizes a floating point number. But if the number is overflowed or underflowed while trying to normalize then the appropriate flags are set.
- **Rounder**: Rounds the 32 bit significand to 21 bits.

## 4 bit MIPS processor

## Group members:
- [Showvik Biswas](https://github.com/showvikbiswas)
- [Fardin Anam Aungon](https://github.com/fardinanam)
- [Kazi Ababil Azam](https://github.com/ababiltalha)
- [Muhammad Ehsanul Kader](https://github.com/ehsankader16)
- [Anup Bhowmik](https://github.com/Anupznk)