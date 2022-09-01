# CSE-306-Computer-Architecture-Sessional
This is a repository containing all the simulations and reports of CSE-306 Computer Architecture Sessional.

## 4 bit ALU
**This ALU contains:**
- Two 4 bit inputs A and B
- Three select bits S2, S1, S0 as ALU opcodes
- One 4 bit output
- Four flags: Zero, Carry, Overflow, Negative
### Implemented functions and opcodes
<table class="tg">
<thead>
  <tr>
    <th class="tg-c3ow" colspan="3">ALU opcodes</th>
    <th class="tg-c3ow" rowspan="2">Functions</th>
  </tr>
  <tr>
    <th class="tg-c3ow">S2</th>
    <th class="tg-c3ow">S1</th>
    <th class="tg-c3ow">S0 (Cin)</th>
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

### Truth table
<table class="tg">
<thead>
  <tr>
    <th class="tg-c3ow" colspan="3">ALU opcodes</th>
    <th class="tg-c3ow" rowspan="2">Required outputs</th>
    <th class="tg-c3ow" colspan="3">Adder inputs</th>
    <th class="tg-c3ow" rowspan="2">Functions</th>
  </tr>
  <tr>
    <th class="tg-c3ow">S2</th>
    <th class="tg-c3ow">S1</th>
    <th class="tg-c3ow">S0 (Cin)</th>
    <th class="tg-c3ow">Xi</th>
    <th class="tg-c3ow">Yi</th>
    <th class="tg-0pky">Zi</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">A</td>
    <td class="tg-c3ow" rowspan="2">Ai</td>
    <td class="tg-c3ow" rowspan="2">0</td>
    <td class="tg-0pky" rowspan="2">Ci</td>
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
    <td class="tg-c3ow" rowspan="2">AiBi</td>
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
    <td class="tg-c3ow" rowspan="2">Ai</td>
    <td class="tg-c3ow" rowspan="2">Bi</td>
    <td class="tg-0pky" rowspan="2">Ci</td>
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
    <td class="tg-c3ow" rowspan="2">AiBi'</td>
    <td class="tg-c3ow" rowspan="2">Bi</td>
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

### Simplified inputs to individual full adders
Xi = A(S1' + S2 XOR B)

Yi = S2B

Zi = S1'Ci

### Circuit diagram
![4 bit ALU circuit diagram](1%20-%204%20bit%20ALU/4%20bit%20ALU%20circuit%20diagram.png)