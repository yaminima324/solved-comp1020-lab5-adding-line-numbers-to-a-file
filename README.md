Download Link: https://assignmentchef.com/product/solved-comp1020-lab5-adding-line-numbers-to-a-file
<br>
<ul>

 <li>Exceptions</li>

 <li>File reading and writing</li>

</ul>

Notes:

<ul>

 <li>The three exercises are independent – you can do them in any order.</li>

 <li>Only one of the three exercises is required.</li>

 <li>The Bronze and Silver exercises are similar – both will read in an entire text file and write it out again in modified form. About 75% of the code is the same in the two exercises. If you do both of them, use a copy of your Bronze program as a starting point for your Silver program.</li>

</ul>

Adding line numbers to a file

<ol>

 <li>Begin with the supplied file <strong>java</strong>.</li>

 <li>Complete the main method so that it will read in the supplied file <strong>txt</strong> and write out a modified version of this file as <strong>outputLab5Bronze.txt</strong>. (These two names are predefined for you as global constants.) The output file should be the same as the input file, except that every line should have a line number added to the front, in the format shown below.</li>

</ol>

The supplied file <strong>testLab5Bronze.txt</strong> contains:

<strong>This is the top line </strong>

<strong> </strong>

<strong>The previous one is blank. </strong>

<strong>Short one. </strong>

<strong>This is the last one. </strong>

Your program should create an output file <strong>outputLab5Bronze.txt</strong> which contains:

<strong>1: This is the top line 2:  </strong>

<strong>3: The previous one is blank. </strong>

<strong>4: Short one. </strong>

<strong>5: This is the last one. </strong>




Adding indentation to a Java file

<ol>

 <li>Begin with the supplied file <strong>java</strong>.</li>

 <li>Complete the main method so that it will read in the supplied file <strong>java</strong> which contains a Java program, but with randomized indentation. Your program should fix the indentation as described below, and write out a new version of this file named</li>

</ol>

<strong>Lab5SilverOutput.java</strong>. (These names are predefined for you as global constants.) To fix the indentation, do the following things:

<ol>

 <li>Remove any existing blanks from the front of each line. The built-in <strong>String</strong> method with the signature <strong>String trim()</strong> can be used to do this easily. It will remove all leading and trailing white space from any <strong>String</strong>. For example,</li>

</ol>

<strong>”   test one   “.trim()</strong>   will give the result   <strong><sub>“test one”</sub></strong>

<ol>

 <li>Add blanks to the front of each line to indent it properly. The amount of indentation should be 0 for the first line. Note the supplied <strong>String blanks(int n)</strong> method which will give you a <strong>String</strong> containing <strong>n</strong></li>

 <li>If any line contains a <strong><sub>“{“</sub></strong> character, then increase the indentation for all following lines (but not this one) by an extra <strong>INDENT_AMOUNT</strong> This is a predefined constant. Note that the <strong>String</strong> method <strong>boolean contains(String)</strong> will tell you whether or not one <strong>String</strong> is contained inside another. For example, <strong>“Test”.contains(“e”)</strong> will return <strong>true</strong>.</li>

 <li>If any line contains a <strong><sub>“}”</sub></strong> character, then decrease the indentation for this line, and all following lines, by <strong><sub>INDENT_AMOUNT</sub></strong>.</li>

 <li>This makes the assumptions that <strong><sub>{ }</sub></strong> braces are the only reason to ever indent a line in a Java program (which is not true), that no line will ever contain more than one brace character (also not necessarily true), and that the braces are properly matched up. But it will do a reasonable job of any file for which these assumptions are true.</li>

</ol>

For example, if the input file contained:

<strong>      while(x){  doThis();     if(y){ </strong>

<strong>              doThat(); </strong>

<strong> }//if </strong>

<strong>                      }//while </strong>Then the output file should contain:

<strong>while(x){      doThis();      if(y){           doThat(); </strong>

<strong>     }//if </strong>

<strong>}//while </strong>

<strong>        </strong>

<strong> </strong>




In this exercise, you will use Exceptions to complete a program, including throwing an Exception from the catch block that is handling a previous exception. Begin with the supplied file

<strong>TemplateLab5Gold.java</strong>. The static variables <strong>intArray</strong> and <strong>numElements</strong> form a standard partiallyfull array of integers. The <strong>insertIntoArray</strong> method adds a new integer to this list. It does no error checking and will throw an <strong>ArrayIndexOutOfBoundsException</strong> when the array is full. Do not modify this method in any way. The <strong>expandArray</strong> method will double the capacity of <strong>intArray</strong>. Add the following exceptions and exception handling to this program:

<ol>

 <li>Modify the <strong>addElement</strong> method (which, at the moment, simply calls the i<strong>nsertIntoArray</strong> method) so that it will catch the <strong>ArrayIndexOutOfBoundsException</strong> thrown by <strong>insertIntoArray</strong>. When it does, it should print <strong>“Expanding the array”</strong>, call <strong>expandArray</strong> and then call <strong>insertIntoArray</strong> again, now that there is more room. Now everything should work. The main program will add the numbers 1-20 with no problem.</li>

 <li>But it has been decided that the array should never be allowed to become any larger than <strong>MAX_SIZE</strong> (predefined for you as 16). Modify the <strong>expandArray</strong> method so that it will not expand the array any more after it reaches this size. Instead, it should throw a <strong>RuntimeException</strong> containing the message <strong>“Array at maximum capacity”</strong>.</li>

 <li>You will now have to catch the <strong>RuntimeException</strong> in the <strong>addElement</strong> Note that the place that the exception will occur is inside the catch block from part 1. The <strong>addElement</strong> method should respond by printing out <strong>“Error in addElement: “</strong> followed by the message contained in the Exception. It should then throw a <strong>RuntimeException</strong> itself, containing the message <strong>“Element xxx not added.”</strong>.</li>

 <li>Catch this <strong>RuntimeException</strong> in the main program, where it should print the message <strong>“Error in main: “</strong> followed by the message in the exception.</li>

 <li>When working correctly, the output produced by the program should be:</li>

</ol>

<strong>element 1 added element 2 added Expanding the array element 3 added element 4 added Expanding the array element 5 added element 6 added element 7 added element 8 added Expanding the array element 9 added element 10 added element 11 added element 12 added element 13 added element 14 added element 15 added element 16 added Expanding the array </strong>

<strong>Error in addElement: Array at maximum capacity Error in main: Element 17 not added. </strong>


