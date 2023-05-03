Download Link: https://assignmentchef.com/product/solved-cs314-lab-1
<br>
<ol>

 <li> Consider the following C code:</li>

</ol>

#include &lt;stdio.h&gt;




void printBytes(unsigned char *start, int len) {     for (int i = 0; i &lt; len; ++i) {         printf(” %.2x”, start[i]);

}

printf(“
”);

}

void printInt(int x) {

printBytes((unsigned char *) &amp;x, sizeof(int));

}

void printFloat(float x) {

printBytes((unsigned char *) &amp;x, sizeof(float));

}




Copy and paste the above code into a file named 1-1.  Add the following functions to the file, taking the indicated data type as a parameter and calling <em>printBytes</em> as appropriate: <em>printShort</em>, <em>printLong</em>, <em>printDouble</em>.

Also write a <em>main()</em> function to test each of the above functions (with the exception of <em>printBytes</em>, which you do not need to test directly) with reasonable inputs.  Do you notice anything unexpected regarding the output of your test functions?  List any observations as comments inline in your main function and explain these observations based on your readings from the textbook.

2.  Suppose we number the bytes in a 32-bit word from 0 (least significant) to 3 (most significant). Write code for the following C function that will return an unsigned int consisting of bytes 3 and 2 from <em>x</em> and bytes 1 and 0 from <em>y</em>:

unsigned int combine (unsigned int x, unsigned int y);

Here are some test runs:

combine(0x12345678, 0xABCDEF00): 0x1234EF00 combine(0xABCDEF00, 0x12345678): 0xABCD5678

Use only bitwise operators; no if statements, loops, or arithmetic operators (+, -, *, /, %).  Also write a main() function to test your function.

Hint: use a bit mask to isolate bytes 3 and 2 from <em>x</em>, and another bit mask to isolate bytes 1 and 0 from <em>y</em>, then combine the results.

Name your source file 1-2.c

<ol start="3">

 <li>Suppose we again number the bytes in a 32-bit word from 0 (least significant) to 3 (most significant). Write code for the following C function that will return an unsigned int such that byte <em>i</em> of <em>x</em> is replaced by byte <em>b</em>:</li>

</ol>

unsigned int replace (unsigned int x, int i, unsigned char b);

Here are some test runs:

replace(0x12345678, 2, 0xAB): 0x12AB5678 replace(0x12345678, 0, 0xAB): 0x123456AB




Use only bitwise operators; no if statements, loops, or arithmetic operators (+, -, *, /, %).  Also write a main() function to test your function.

Hint: use shifts to align the input byte and a mask to isolate the bytes that should remain.

Name your source file 1-3.c

<ol start="4">

 <li> Suppose we number the bits in a 32-bit word from 0 (least significant) to 31 (most significant). Write code for the following C function that will return 1 if <em>x</em> has at least one bit with a value of 1 at an odd index, 0 otherwise:</li>

</ol>

int oddBit(unsigned int x);

Here are some test runs:

oddBit(0x1): 0

oddBit(0x2): 1 oddBit(0x3): 1 oddBit(0x4): 0 oddBit(0xFFFFFFFF): 1 oddBit(0xAAAAAAAA): 1 oddBit(0x55555555): 0




Use only bitwise and logical operators (&amp;&amp;, ||, !); no if statements, loops, arithmetic operators (+, -, *, /, %), or conditional operators (==, !=, etc).  Also write a main() function to test your function.

Hint: use a bit mask to isolate the odd bits, and think about the effect of a logical <em>not</em> (or two) on an int in C.

Name your source file 1-4.c