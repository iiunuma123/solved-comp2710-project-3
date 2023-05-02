Download Link: https://assignmentchef.com/product/solved-comp2710-project-3
<br>
5/5 - (1 vote)

Goals:

<ul>

 <li>To learn streams and file I/O</li>

 <li>To learn how to use tools for stream I/O</li>

 <li>To use arrays to group data elements</li>

 <li>To design and implement functions (Note: this topic was covered in Project 2)</li>

 <li>To perform unit testing</li>

 <li>To design a simple algorithmWrite a program that merges the numbers in two files and writes all the numbers into a third file. Your program takes input from two different files and writes its output to a third file. Each input file contains a list of numbers of type int in sorted order from the smallest to the largest. After the program is run, the output file will contain all the numbers in the two input files in one longer list in sorted order from smallest to largest.You must provide the following user interface. The user input is depicted as Bold, but you do not need to display user input in bold. Please replace “Li” with your name. Your program loads two input files and merges the numbers in the two files.</li>

</ul>

*** Welcome to Li’s sorting program *** Enter the first input file name: input1.txt The list of 6 numbers in file input1.txt is: 4

13 14 17 23 89

Enter the second input file name: input2.txt The list of 5 numbers in file input2.txt is:37

9 14 15

1

The sorted list of 11 numbers is: 3 4 7 9 13 14 14 15 17 23 89 Enter the output file name: output.txt*** Please check the new file – output.txt ****** Goodbye. ***

Your program must follow the above user interface.

Design Issues:

Please do NOT intend to implement this project using a single main() function.You need at least three functions to implement this project. The suggested functions are:

1. array_size &lt;- readfile(inputArray[], instream)2. outputArray_size &lt;- sort(inputArray1[], inputArray1_size,

inputArray2[], inputArray2_size, outputArray[])3. void &lt;- writefile(outputArray[], outputArray_size)

Integration Testing:

Integration testing (a.k.a., Integration and Testing) is the phase in software testing in which individual software modules are combined and tested as a group. You may use the attached two input files to test the correctness of your program as an entire system.

Requirements:

<ol>

 <li>(5 points) Use comments to provide a heading at the top of your code containing your name, AUuserID, filename, and how to compile your code. Also describe any help or sources that you used (as per the syllabus).</li>

 <li>(5 points) Your source code file should be named as “project3_AUuserID.cpp”. You will not lose any point if Canvas automatically changes your file name due to resubmissions.</li>

 <li>(5 points) Your program must test if files have been correctly opened.</li>

 <li>(5 points) You must close files after using them.</li>

 <li>(10 points) Your program should read and display numbers stored in the twoinput files.</li>

 <li>(20 points) You program should sort and display the numbers.</li>

 <li>(15 points) You program should correctly write the sorted list to the third file.</li>

 <li>(10 points) You must define at least three functions.</li>

 <li>(5 points) You must reduce the number of global variables and data</li>

 <li>(10 points) Usability of your program (e.g., user interface)</li>

 <li>(10 points) Readability of your source code.</li>

</ol>

Note: You will lose at least 40 points if there are compilation errors or warning messages when the TA compiles your source code. You will lose points if you: do not use the specific program file name, or do not have a comment on each function in your program you hand in.

2

Programming Environment:

Write a program in C++. Compile and run it using AU server (no matter what kind of text editor you use, please make sure your code could run on AU server, the only test bed we accept is AU server).

Sample Code 1:

The following code shows you how to use arrays and their sizes as input parameters of functions.

//Input: (1) Array storing data retrieved from the file (i.e., instream)// (2) input file stream object//Output: Size of array. Note: you need to use this parameter to control the array size.

int readfile(int inputArray[], ifstream&amp; instream);

int main( ) {

ifstream inStream1;

int iArray1[MAX_SIZE]; int iArray1_size;int iArray2[MAX_SIZE]; int iArray2_size;

inStream1.open(“input1.txt”);

iArray1_size = readfile(inputAry, inStreamFirst);

inStreamFirst.close( );

return 0; }

int readfile(int inputArray[], ifstream&amp; inStream){ int index;

inStream &gt;&gt; inputArray[index]; while (! inStream.eof()) {

cout &lt;&lt; inputArray[index] &lt;&lt; endl; index++;inStream &gt;&gt; inputArray[index];

//Sample code for Project 3

#include &lt;fstream&gt; #include &lt;iostream&gt; using namespace std;

const int MAX_SIZE = 100;

}

Sample Code 2:

return index; }

3

Sample Code 2:

The following code shows you (1) how to retrieve a file name from your keyboard, (2) how to open a file, and (3) how to read data from the file.

#include &lt;fstream&gt;#include &lt;iostream&gt;#include &lt;cstdlib&gt; //for exit() using namespace std;

int main() {

ifstream inStream; int data;

cout &lt;&lt; “file name:”;cin &gt;&gt; filename;cout &lt;&lt; “entered filename is:” &lt;&lt; filename &lt;&lt; endl;

// Pass the file name as an array of chars to open() // inStream.open(filename); inStream.open((char*)filename.c_str());

if (inStream.fail()) {cout &lt;&lt; “Input file opening failed.” &lt;&lt; endl; exit(1);

}

inStream &gt;&gt; data;while (!inStream.eof()) {

cout &lt;&lt; data &lt;&lt; endl;

inStream &gt;&gt; data; }

inStream.close();