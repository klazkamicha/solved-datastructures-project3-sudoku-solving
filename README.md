Download Link: https://assignmentchef.com/product/solved-datastructures-project3-sudoku-solving
<br>
In this assignment, you will be implementing a <strong>backtracking</strong> algorithm to solve Sudoku puzzles. If you aren’t familiar (or even if you are and need a refresher), <a href="https://www.sudoku.name/rules/en"><strong>have a look at this site</strong></a>.

<h1>Starting point</h1>

<a href="https://jarrettbillingsley.github.io/teaching/classes/cs0445/projects/cs0445_proj3_materials.zip"><strong>Download and extract these materials.</strong></a> Contained are:

<strong>Sudoku.java </strong>, <strong>the file you will modify.</strong>

5 <strong><sub>.su</sub></strong> files, which are <strong>plain text files</strong> containing Sudoku puzzles to solve.

Since they’re plain text files (like java files), you can open them in your text/code editor.

<strong>Sudoku.java</strong> contains the following:

a <strong><sub>main</sub></strong> method which can accept some command-line arguments. the <strong>readBoard</strong> method, which reads a board from a file. <strong>main</strong> calls this.

“Unsolved” (empty) cells contain 0s.

the <strong>printBoard</strong> method, which prints the board to the console, which will be very helpful. the <strong>solve</strong> backtracking template method.

and finally, 8 “skeleton” methods for you to fill out.

you know, cause Halloween. <sub>&#x1f480;</sub>

<h1>Testing</h1>

<strong>We will be testing your code on the command line.</strong> You are welcome to use an IDE, but before submitting, please test that your Java files can be compiled and run on the command line without it.

We should be able to run your program like so:

to run all the test methods, or:

to load and solve a Sudoku board file.

The <strong><sub>main</sub></strong> we gave you handles this command-line interface. But right now, nothing happens &#x1f642;

<h1>Your task</h1>

This is a tough project. As such, <strong>60% of the grade is for correctness, and 40% is for the thoroughness of your testing methods.</strong>

You will implement four methods to solve the problem: <strong>isFullSolution </strong>, <strong>reject </strong>, <strong>extend </strong>, and <strong>next </strong>.

To     complement     those     four,     there     are     four     testing     methods:

<strong>testIsFullSolution </strong>, <strong>testReject </strong>, <strong>testExtend </strong>, and <strong>testNext </strong>. Each of these should make <strong>several tests</strong> of the corresponding solving methods.

<h2>The puzzle-solving algorithm</h2>

By implementing the four solving methods, you will be constructing a backtracking solver program. Important points:

You must not change any of the original numbers already on the board. You must implement all the Sudoku rules: each row, column, and 3×3 square may only contain each number once.

You only need to find <em>one</em> solution, not all solutions. Once you find a solution, you can stop.

If a board is not solvable, your program must say so.

<h2>The puzzle-solving methods</h2>

These methods make up the four parts of the backtracking template. These methods are <strong>not recursive!</strong> Only the <strong><sub>solve</sub></strong> method is, and we already wrote that for you &#x1f609;

<h3>boolean isFullSolution(int[][] board)</h3>

This takes a board as a 2D array, and returns <strong><sub>true</sub></strong> if it is complete (no empty cells) and satisfies all the rules.

If there are any empty cells, or if there are any rule violations, it returns false.

<h3>boolean reject(int[][] board)</h3>

This takes a <em>partial</em> solution, and returns <strong><sub>true</sub></strong> if it is <strong>impossible </strong>to continue with this board.

For example, if there are two 3’s on one row, there is no reason to keep solving this board. <strong>int[][] extend(int[][] board)</strong>

This takes a <em>partial</em> solution, and constructs a <strong>new</strong> partial solution. When I say “new” I mean use <strong><sub>new</sub></strong> to allocate a new 2D array!

What I mean by “constructs a new partial solution” is it <strong>places a number into a previously-empty cell.</strong>

If there are no more possible cells to place a number in, it should return <strong>null.</strong>

<h3>int[][] next(int[][] board)</h3>

The partner to <strong>extend </strong>. This takes a <em>partial</em> solution, and constructs another <strong>new</strong> partial solution.

It will <strong>change the most-recently-placed number</strong> to the next possible option.

So if the most-recently-placed number was a 1, this would change it to a 2…

…or a 2 to a 3, or a 3 to a 4, and so on.

If there are no options for the most-recently-placed number, it should return <strong>null.</strong>

<strong>Do not write all the methods at once.</strong> Start with <strong>isFullSolution </strong>and <strong>reject </strong>. Test them extensively with your testing methods (by running your program with <strong>java Sudoku -t </strong>).

<h2>The testing methods</h2>

Re-read starting at Chapter 2.16 to review the concepts behind writing test methods. Write your testing methods <em>at the same time you write the solving methods.</em> Have a look at <a href="https://jarrettbillingsley.github.io/teaching/classes/cs0445/examples/Ex18QueensBacktracking.java"><strong>this 8-Queens exam</strong></a><a href="https://jarrettbillingsley.github.io/teaching/classes/cs0445/examples/Ex18QueensBacktracking.java"><strong>p</strong></a><a href="https://jarrettbillingsley.github.io/teaching/classes/cs0445/examples/Ex18QueensBacktracking.java"><strong>le</strong></a> to see some example testing methods.

For each of the testing methods, try to follow these guidelines:

Come up with a variety of partial solutions that will test all possible paths through your solving method.

Call the method with those partial solutions.

Check that the method actually returns what you expect it to return. Print out the test cases and results, so that you can easily see if things are looking right.

Include enough test cases that you are convinced that your solving method is working properly.

You can make new board files following the guidelines below, and then use <strong>readBoard</strong> to load them for testing.

For example, if I were testing the <strong>reject</strong> method, I would give it…

a board with two of the same number in the same row. a board with two of the same number in the same column.

a board with two of the same number in a 3×3 square.

(probably a few versions of that, to be thorough.)  the boards we gave you ( <strong>1-trivial.su</strong> etc.) to make sure it <em>doesn’t </em>reject those. a solved board (look online for one) to make sure it <em>doesn’t</em> reject that.

<h1>Example boards</h1>

We’ve included 5 example boards (the <strong><sub>.su</sub></strong> files). If you open them in your text editor, you will see they look something like this:

There are 9 rows, and each has 9 columns. Any non-number character is treated as an empty (unsolved) cell.

You can open one of the existing files and “File &gt; Save As…” to make your own boards. Make a bunch! It’s fine!

<h2>Sudoku.java</h2>

Any <em>extra</em> boards besides the ones we gave you

And if anything is wrong/not working, a plain text (.txt) file with notes to the grader about what is not working.

<a href="https://pitt.box.com/s/uj6pq7yim8115vlk8px5tuk8vqd88n5l"><strong>Submit to the Box folder at this link.</strong></a> Drag your zip file into your browser to upload. <strong>If you can see your file, you uploaded it correctly!</strong>

You can also re-upload if you made a mistake and need to fix it.

<em>© 2016-2018 Jarrett Billingsley</em>