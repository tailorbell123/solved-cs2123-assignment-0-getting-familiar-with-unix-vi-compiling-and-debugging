Download Link: https://assignmentchef.com/product/solved-cs2123-assignment-0-getting-familiar-with-unix-vi-compiling-and-debugging
<br>
In this assignment, you will make certain that you can (details are provided below):

<ul>

 <li>find the main CS lab at <strong>NPB 2.118</strong>.</li>

 <li>login to your user id.</li>

 <li>learn some essential <strong>Unix</strong> commands (pwd, mkdir, ls -al, cd, man, rm, gcc, cat, vi) and get familiar with the Unix cheat sheet.</li>

 <li>learn to use <strong>vi</strong> and get familiar with the vi cheat sheet</li>

 <li>modify the provided C source file to complete documentation and coding (see 3.4)</li>

 <li>learn to use <strong>gcc</strong> to compile your code</li>

 <li>learn to use <strong>ddd</strong> to debug your code</li>

 <li>optionally, learn to use Microsoft Visual Studio</li>

</ul>

Some useful stuff:

viCheatSheet                               This word document provides a brief list of the most important commands for using <strong>vi</strong>.  It is available on my webpage under “setup”.

unixCheatSheet                          This word document provides a brief list of the most important <strong>Unix</strong> commands.   It is available on my webpage under “setup”.

dddTips                                          This word document gives some tips on using the <strong>ddd</strong> debugger.  It also has a reference to a detailed tutorial.  It is available on my webpage under “setup”.

vimtutor                                        This provides a tutorial that allows you to practice using the Unix vi editor.  Change to the ~/tmp directory (<strong>cd ~/tmp) </strong>and execute vimtutor.  Follow the directions provided in the file.

usingMicrosoftVisualStudio (optional) This word document describes how to use Microsoft Visual Studio.  It is available on my webpage under “setup”.

ssh download (optional) This will download a copy of ssh suitable for windows.  It is available on my webpage under “setup”.

Steps:

<ol>

 <li>Login

  <ul>

   <li>Go to the CS lab NPB 2.118 (assuming it is available). If working remotely, see how to login remotely on my <u>setUp</u> and skip to step 1.5.</li>

   <li>There should be two types of workstation configurations in the CS lab:</li>

  </ul></li>

</ol>

Dell Thin Client – (left side of lab) which access VDI.  See how to login to VDI on my <u>setUp</u>. Linux Workstations – (right side of lab) these run Linux 14.04 and have a good desktop.

<ul>

 <li>Use a Linux workstation. Login locally using your id (3 letters and 3 numbers). Your password will be defaulted to your UTSA banner ID without the @.</li>

 <li>Open a terminal window. If your Linux login has a menu, use Applications&gt;Accessories &gt; Terminal.</li>

</ul>

If not, use

<ul>

 <li>Click on the bottom left icon which will show an applications menu.</li>

 <li>Click on Accessories</li>

 <li>Click on LXTerminal</li>

 <li>Most of the discussion below uses the Terminal window.</li>

</ul>

<ul>

 <li>Since your password was defaulted, change your password using the <strong>passwd</strong> (Note that the “$” is being used to indicate that the Linux shell is prompting you for input.  The actual prompt may include your user id.)In the terminal window type:</li>

</ul>

<h1>$ passwd</h1>

<strong>Notes:  </strong>If you are logging in remotely (from home):

If using linux:

<ul>

 <li>Start a terminal window:</li>

</ul>

$ ssh -X <em>userName</em>@fox<em>ii</em>.cs.utsa.edu   (where <em>ii</em> is one of 01 through 06) If using windows from home:

<ul>

 <li>You should install <strong>ssh </strong>(see the setup web page).</li>

 <li>You can transfer files, use <strong>vi,</strong> and the <strong>gcc </strong>compiler, but you can’t use <strong>ddd</strong> without an xwindow.</li>

 <li>When you use ssh specify <em><u><a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="f386809681bd929e96b3">[email protected]</a></u></em><u>fox<em>ii</em>.cs.utsa.edu</u> (where <em>ii </em>is one of 01 through 06)</li>

 <li>(In the future, consider using ubuntu as a dual boot or use Cygwin.)</li>

</ul>

<ol start="2">

 <li>Check out some Unix directory-related commands. (You may want to look at the unixCheatSheet.)

  <ul>

   <li>After logging in, check your current directory using <strong>p</strong>rint<strong> w</strong>orking<strong> d</strong>irectory:</li>

  </ul></li>

</ol>

$ <strong>pwd </strong>

<ul>

 <li>See what files are in your directory:</li>

</ul>

<h1>$ ls -al</h1>

This will list all files with long details).  You should notice some dot files (begin with “.”) such as .vimrc

2.3 Create a directory for cs2123:

$ <strong>mkdir cs2123</strong>

2.4 Change to your cs1713 directory:

<h1>$ cd cs2123</h1>

Verify that you are in that directory by using the <strong>pwd</strong> command.

2.5 Change back to your home directory:

<h1>$ cd ~</h1>

Verify your current directory using <strong>pwd</strong>.

2.6 The following are done to practice creating directories and subdirectories:

2.6.1     Create a subdirectory called <strong>Fruit</strong> and another called <strong>Veggie </strong>under your home directory.

$ <strong>mkdir Fruit </strong>$ <strong>mkdir Veggie </strong>

2.6.2     Create two subdirectories under <strong>Fruit </strong>called <strong>Apple </strong>and <strong>pineApple.  </strong>

$ <strong>cd Fruit </strong>$ <strong>mkdir Apple </strong>$ <strong>mkdir pineApple </strong>

2.6.3     Change directory to the <strong>Apple </strong>directory and then use <strong>pwd </strong>to check where you are:

$ <strong>cd Apple </strong>$ <strong>pwd </strong>

2.6.4     Create a subdirectory under <strong>Apple </strong>called <strong>Green  </strong>

<h1>$ mkdir  Green</h1>

2.6.5     Go up to the <strong>Fruit</strong> directory by using

$ <strong>cd ..          </strong>

$ <strong>pwd               </strong>

Note that <strong>cd ..</strong> took you up one directory.

2.6.5     You can specify multiple directories in a path when using cd

$ <strong>cd  Apple/Green  </strong>

$ <strong>pwd              </strong>

You should be in Fruit/Apple/Green

2.6.6     Go to the <strong>Veggie </strong>directory using ~ for the home directory.

<h1>$ cd  ~/Veggie $ pwd</h1>

2.6.7      See what files exist now in your account.

$ <strong>cd  ~ </strong>

$ <strong>ls  -alR          </strong>

This lists files recursively following subdirectories.

If you have more than a page worth of files, use <strong>ls -alR | more</strong>.   To exit out of <strong>more</strong>, type <strong>q</strong>.

2.7 Use the <strong>man </strong>command to see how it gives you manual pages for most Unix commands by typing <strong>man <em>command</em></strong>.  You can scroll through the manual pages by pressing the space bar to scroll a page or <strong>enter </strong>key to scroll fewer lines.  To quit out of man, type <strong>q. </strong>

<h1>$ man  ls</h1>

2.8 Practice using the <strong>find </strong>and <strong>rm </strong>commands.

2.8.1     Use the <strong>find </strong>command to find all files containing the word “Apple”.

<h1>                          $ find  .  -name  “*Apple*”</h1>

2.8.2     Use the <strong>rm </strong>command to remove the Fruit folder and all its contents.

$ <strong>rm  -r  Fruit </strong>

2.8.3      Use the up arrow several times to get Linux to show the find command you did.  If you go up too far, use the down arrow.  Execute that find again and notice that it doesn’t find the Apple and pineApple directories.

2.8.4     Remove the Veggie directory.




<ol start="3">

 <li>Use the <strong>vi</strong>

  <ul>

   <li>Look at the viCheatSheet.</li>

   <li>Try the vi tutorial:</li>

  </ul></li>

</ol>

<h1>3.2.1 $ cd  ~/tmp</h1>

3.2.2 $ <strong>vimtutor</strong><strong>                   </strong>(follow the instructions in that file)

3.3 Create a <strong>.vimrc</strong> file to help you with indentation and showing line numbers.

3.3.1 $ <strong>cd ~ </strong>

3.3.2      Use the Unix <strong>cat </strong>command to create that file (input is terminated by pressing the <strong>CTRL-D key</strong>).  Note that this only has to be done once.

<h1>$ cat  &gt;.vimrc</h1>

:set ai sw=4

:set number

:set expandtab

:set softtabstop=4

:set smartindent

<strong>CTRL-D </strong>

<strong> </strong>

3.4 Create your first program for this class.  (Create the cs2123 folder if you haven’t already.)

<h1>3.4.1 $ cd  ~/cs2123</h1>

3.4.2      Copy the code (details of how to do this are shown in 3.4.2.1), include file and data  from my web page<strong>:        p0abc123.c – </strong>contains most of the code for program #0.  You will have to make several changes:

getCourseData – replace the function documentation header with a good one based on my programming standards

printCourseData – change the code to print the course data as shown in the existing function documentation header.

In the program documentation header, specify your name.

<strong>cs2123p0.h – </strong>include file for this assignment         <strong>p0Input.txt </strong>– data file to be used with this assignment 3.4.2.1 Invoke the firefox browser:

$ firefox

3.4.2.2 The firefox internet browser will open.  Within firefox, go to Blackboard and login with your abc123 and pass phrase:

<a href="http://utsa.blackboard.com/">http://utsa.blackboard.com</a>

3.4.2.3 Go to our class <strong>CS2123 </strong> (not the recitation).  Then go to Content -&gt; Programming Projects and download p0abc123.c, cs2123p0.h, and p0Input.txt.  Save them to your cs2123 directory<strong>.</strong>

3.4.3      You may want to check to see if the files contain a combination of carriage returns (r) and line feeds (
) which happens when some file are copied from Microsoft Windows.  See the setUp page.

3.4.4      Use <strong>vi</strong> to make your changes (as described in 3.4.2)

$ <strong>vi  cs2123p0.c</strong>




<ol start="4">

 <li>Compile your program, naming the executable p0:</li>

</ol>

<h1>$ gcc  -g  -o p0  cs2123p0.c</h1>

where   -g  tells the compiler to generate information suitable for the debugger,

-o  specifies the name of the result (in this case an executable)

This compiles cs2123p0.c, creating an intermediate compiled object file, and generates an executable named p0.  Until we have more complex assignments, we will use that form of the gcc.

If you have any compilation errors, the compiler will tell you the line number.  Correct your mistakes using<strong> vi</strong> and repeat step 4.

<ol start="5">

 <li>Execute your program using the provided input file.</li>

</ol>

<h1>$ ./p0 &lt; p0Input.txt</h1>

You can look at the output by piping the result to <strong>more </strong>(use <strong>q </strong>to quit, <strong>Enter </strong>to advance 1 line, <strong>SpaceBar </strong>to advance many lines)<strong>: </strong>

$<strong> ./p0 &lt; p0Input.txt | more </strong>

You can save the output in a file by redirecting stdout to a file using “&gt;”:

<h1>$ ./p0 &lt; p0Input.txt &gt; p0Out.txt</h1>

<strong> </strong>

<ol start="6">

 <li>Use the debugger.

  <ul>

   <li>Look at <strong>docx</strong> under my setup web page. You will find it important to refer to that information while using <strong>ddd</strong>.</li>

   <li>Invoke the <strong>ddd</strong> (Note that if you didn’t use the -g compiler switch, the debugger will not work.  Also, if you are not executing from a Unix terminal window, ddd will probably not work.)</li>

  </ul></li>

</ol>

<h1>$ ddd  ./p0</h1>

You may want to show the line numbers for each statement.  See dddTips.

6.3 You will see the ddd screen which has the following areas:

Menu Bar                                                              This is at the menu at the top of the window and includes

File, Edit, View, etc.

Tool Bar                                                                    This is immediately below the menu bar and contains some

important tools like Find and Break.

Data Area                                                              At the beginning, this shows an empty grid area.  It is used to

show values of variables which you wish to closely examine.

Source File Area                                                 This displays your source code.

Command Tool Area                                         This appears on the right side of the Source File Area and includes buttons:

Run                                  run the program.

Step                                 execute the current step.  It will step

into a called function.

Next                                execute the current step, but do not

step into a called function.

Cont                                Continue execution until the next

break or stdin.

Finish                              continue execution until the finish of the current function.

Kill                                    Kill the execution of your program.

Console Area                                                        This is at the bottom of the screen:

<ul>

 <li>debugger commands are shown/entered</li>

 <li>standard input is entered (depending on preferences) standard output is shown (depending on preferences)

  <ul>

   <li>Tell <strong>ddd </strong>to show line numbers. This is done via the <strong>Source </strong>menu item.</li>

  </ul></li>

</ul>

Source &gt; Display Line Numbers

<ul>

 <li>Run your code using the <strong>Program</strong> menu item.</li>

</ul>

<ul>

 <li>Click on <strong>Run in Execution Window</strong> to give you an execution window when you run. You only have to do this once.</li>

 <li>Run your code using Program &gt; Run.  Tell the Run dialogue window to use the input file.</li>

</ul>

For arguments, specify:

&lt; p0Input.txt

<ul>

 <li>Click the <strong>Run</strong> button in that Run Program dialogue window.</li>

 <li>Your program should run to completion unless there is a bug. If it didn’t work and you wish to terminate the program press the <strong>Kill</strong> button in the  Command Tool Area.

  <ul>

   <li>Set a Breakpoint on the first <strong>printf </strong>statement in getCustomerData(). Click on its  line number, right click to get a submenu, and then select <strong>Set Breakpoint</strong>.  A stop sign will appear on that line.  This will cause the code to break execution so that you can examine what is happening at a point in the code.  You can set many breakpoints.</li>

   <li>Run your code using Program &gt; Run.  Again tell the Run dialogue window to use the input file.</li>

  </ul></li>

</ul>

For arguments, specify:

&lt; p0Input.txt

<ul>

 <li>Execution should have stopped at the first break point. Notice that an arrow will appear in the  Source File Area indicating the current statement to execute.  In this section, you will step through your code using the <strong>Next </strong>button and examine variable values. You can hover the cursor over a variable to see its value.</li>

</ul>

Try the <strong>Cont </strong>(continue) button.  It will continue executing until it hits a breakpoint.

Eventually hit the <strong>Finish </strong>button.  It will ignore breakpoints in getCustomerData() until it returns from getCustomerData().

Continue executing until the program completes.




<ul>

 <li>Execute your program again. It is often necessary to see what is happening with your variables.  You can <strong>display </strong>variables in the Data Area.  Examining arrays is a little more difficult.  Arrays and complex structures are usually shown in the Display Area.  Right click on the customer array and select <strong>  </strong></li>

</ul>

If your variable is a pointer, you might prefer to display what it references by selecting <strong>Display*</strong>.

Sometimes, it it easier to display a slice of the array.  Please see the <strong>dddTips</strong> for more information.

Step through your code using <strong>Next </strong>and see how the values in the Display Area change.

When you get to the statement which invokes the getToken function:

<ul>

 <li>If you use <strong>Next</strong>, <strong>ddd</strong> will execute that function and then return.</li>

 <li>If you use <strong>Step</strong> (which means step into), <strong>ddd </strong>will <strong>step</strong> into that function, allowing you to use Next to within that function.</li>

</ul>

If you want to stop debugging, use the <strong>Kill </strong>button in the Command Tool Area.

<strong> </strong>

6.10 Another useful feature is to tell <strong>ddd </strong>to interrupt execution when a particular variable’s value changes.

Clear all your breakpoints by clicking on each breakpoint and then pressing <strong>Delete Breakpoint</strong>.

Insert a new breakpoint at the call to getCustomerData().

Run your program using the input file.  It will stop at getCustomerData().

Insert a <strong>Watch point </strong>to watch for when the <strong>iNumberOfCustomers</strong> in main()  changes.  (This is done by clicking on that variable and then selecting the watchpoint button, which looks like two eyeballs,  on the main tool bar.)  Press <strong>Cont</strong> to continue execution.  Notice that execution stops when that variable changes even though it is the corresponding parameter.

When you are finished using ddd, type <strong>quit </strong>in the Debugger Console.

<ol start="7">

 <li>We want to save the output of your program by redirecting the output to <strong>p0Out.txt </strong></li>

</ol>

<h1>$ ./p0  &lt; p0Input.txt &gt;p0Out.txt</h1>

That redirected the stdin (standard input) to come from <strong>p0Input.txt </strong>and stdout (standard output) to <strong>p0Out.txt</strong>.

To save the output when using Microsoft VS, see the instructions in setup.




<ol start="8">

 <li>Upload your results to blackboard.</li>

</ol>

In the Programming Projects folder on Blackboard, there will be a dropbox for Programming Project

<ol>

 <li>Follow the directions on the screen to upload mutiple files<strong>. Upload p0abc123.c </strong>and<strong> p0Out.txt </strong></li>

</ol>