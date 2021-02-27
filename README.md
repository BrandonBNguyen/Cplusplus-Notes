---


---

<h1 id="c-notes">C++ Notes</h1>
<p>Notes and programs created while learning C++. These were notes were created following the content and examples from <a href="https://www.learncpp.com/">learncpp.com</a> and C++ Crash Course: A Fast-Paced Introductino by Josh Lospinoso.</p>
<h2 id="table-of-contents">Table of Contents</h2>
<ol>
<li><a href="#c-basics">C++ Basics</a>
<ol>
<li><a href="#compiling-and-running-code">Compiling and Running Code</a></li>
<li><a href="#instantiating-and-assigning-variables">Instantiating and Assigning Variables</a></li>
<li><a href="#output-and-input-with-the-console">Output and Input with the Console</a></li>
<li><a href="#literals-operators-and-expressions">Literals, Operators, and Expressions</a></li>
</ol>
</li>
<li><a href="#functions">Functions</a>
<ol>
<li><a href="#defining-functions">Defining Functions</a></li>
<li><a href="#return-values">Return Values</a></li>
<li><a href="#parameters-and-arguments">Parameters and Arguments</a></li>
<li><a href="#local-scope">Local Scope</a></li>
<li><a href="#using-functions-effectively">Using Functions Effectively</a></li>
</ol>
</li>
<li><a href="#formatting">Formatting</a>
<ol>
<li><a href="#whitespace-and-basic-formatting">Whitespace and Basic Formatting</a></li>
<li><a href="#forward-declarations-and-definitions">Forward Declarations and Definitions</a></li>
<li><a href="#separating-a-program-across-multiple-files">Separating a Program Across Multiple Files</a></li>
<li><a href="#naming-collisions-and-namespaces">Naming Collisions and Namespaces</a></li>
<li><a href="#preprocessor-and-directives">Preprocessor and Directives</a></li>
<li><a href="#header-files">Header Files</a></li>
</ol>
</li>
<li><a href="#data-types">Data Types</a>
<ol>
<li><a href="#integer-types">Integer Types</a></li>
<li><a href="#floating-point-types">Floating-Point Types</a></li>
<li><a href="#character-types">Character Types</a></li>
<li><a href="#boolean-types">Boolean Types</a></li>
<li><a href="#the-size_t-type">The <code>size_t</code> type</a></li>
<li><a href="#arrays">Arrays</a></li>
<li><a href="#strings">Strings</a></li>
<li><a href="#enumerations">Enumerations</a></li>
<li><a href="#classes">Classes</a>
<ol>
<li><a href="#plain-old-data-pod-classes">Plain-Old-Data (POD) Classes</a></li>
<li><a href="#unions">Unions</a></li>
<li><a href="#fully-featured-classes">Fully-Featured Classes</a>
<ol>
<li><a href="#access-control">Access Control</a></li>
<li><a href="#constructors">Constructors</a></li>
<li><a href="#destructors">Destructors</a></li>
<li><a href="#copy-constructors">Copy Constructors</a></li>
<li><a href="#copy-assignment-operators">Copy Assignment Operators</a></li>
<li><a href="#default-copy">Default Copy</a></li>
<li><a href="#delete-copy">Delete Copy</a></li>
<li><a href="#move-constructors-and-move-assignment-operators">Move Constructors and Move Assignment Operators</a></li>
</ol>
</li>
</ol>
</li>
</ol>
</li>
<li><a href="#control-flow">Control Flow</a>
<ol>
<li><a href="#if-statements">If Statements</a></li>
<li><a href="#switch-statements">Switch Statements</a></li>
<li><a href="#for-loops">For Loops</a></li>
<li><a href="#try-catch-blocks">Try-Catch Blocks</a>
<ol>
<li><a href="#exceptions">Exceptions</a></li>
<li><a href="#noexcept"><code>noexcept</code></a></li>
</ol>
</li>
</ol>
</li>
<li><a href="#reference-types">Reference Types</a>
<ol>
<li><a href="#pointers">Pointers</a></li>
<li><a href="#references">References</a></li>
<li><a href="#this-pointers"><code>this</code> Pointers</a></li>
<li><a href="#const"><code>const</code></a></li>
<li><a href="#auto-type-deduction"><code>auto</code> Type Deduction</a></li>
</ol>
</li>
<li><a href="#object-life-cycle">Object Life Cycle</a>
<ol>
<li><a href="#automatic-storage">Automatic Storage</a></li>
<li><a href="#static-storage">Static Storage</a></li>
<li><a href="#dynamic-storage">Dynamic Storage</a></li>
</ol>
</li>
<li><a href="#runtime-polymorphism">Runtime Polymorphism</a>
<ol>
<li><a href="#virtual-methods">Virtual Methods</a></li>
<li><a href="#pure-virtual-classes">Pure-Virtual Classes</a>
<ol>
<li><a href="#virtual-destructors">Virtual Destructors</a></li>
</ol>
</li>
<li><a href="#implementing-interfaces">Implementing Interfaces</a></li>
</ol>
</li>
</ol>
<h2 id="c-basics">C++ Basics</h2>
<h3 id="compiling-and-running-code">Compiling and Running Code</h3>
<p>After installing Microsoft Visual Studio, I started by compiling and running <em>HelloWorld.cpp</em>, which simply outputs “Hello World” to the console.</p>
<p><em>HelloWorld.cpp</em></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token comment">// HelloWorld.cpp : This file contains the 'main' function. Program execution begins and ends there.</span>
<span class="token comment">//</span>

<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">"pch.h"</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Hello World!\n"</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token comment">// Run program: Ctrl + F5 or Debug &gt; Start Without Debugging menu</span>
<span class="token comment">// Debug program: F5 or Debug &gt; Start Debugging menu</span>

<span class="token comment">// Tips for Getting Started: </span>
<span class="token comment">//   1. Use the Solution Explorer window to add/manage files</span>
<span class="token comment">//   2. Use the Team Explorer window to connect to source control</span>
<span class="token comment">//   3. Use the Output window to see build output and other messages</span>
<span class="token comment">//   4. Use the Error List window to view errors</span>
<span class="token comment">//   5. Go to Project &gt; Add New Item to create new code files, or Project &gt; Add Existing Item to add existing code files </span>
<span class="token comment">//      to the project</span>
<span class="token comment">//   6. In the future, to open this project again, go to File &gt; Open &gt; Project and select the .sln file</span>
</code></pre>
<p>To compile code, use the hotkey <code>Ctrl + B</code>.</p>
<p>To run code (using debugger), use the hotkey <code>Ctrl + F5</code>.</p>
<h3 id="instantiating-and-assigning-variables">Instantiating and Assigning Variables</h3>
<p>To create a variable, we need to define it starting by defining its type followed by the identifier for that variable, such as in the example below.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> x<span class="token punctuation">;</span> <span class="token comment">// Defines a variable named 'x' which we expect to hold an integer value.</span>
</code></pre>
<p>To assign a variable a value, use the assignment operator (<code>=</code>) in a statement known as a <strong>copy assignment</strong>. To do this, after a variable has already been initialized, start with the variable identifier, followed by the assignment operator, followed by the value you wish to assign to the variable.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> x<span class="token punctuation">;</span> <span class="token comment">// Defines a variable named 'x' which we expect to hold an integer value.</span>
x <span class="token operator">=</span> <span class="token number">5</span><span class="token punctuation">;</span> <span class="token comment">// Assign the value of 5 to the variable, x.</span>
</code></pre>
<p>Initializing a variable and assigning it a value can be done in a single statement by using <strong>copy initialization</strong>. To do this, start with the variable type, followed by the variable’s identifier, followed by the assignment operator, and lastly, followed by the value you wish to assign to that variable.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> x <span class="token operator">=</span> <span class="token number">5</span><span class="token punctuation">;</span> <span class="token comment">// Defines a variable named 'x' which holds an integer value of 5.</span>
</code></pre>
<p>Another common way of initializing and assigning a value to a variable is known as <strong>direct initialization</strong>. This is done by specifying the variable type, followed by the variable identifier, followed by parentheses containing the value you wish to assign to the variable.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">x</span><span class="token punctuation">(</span> <span class="token number">5</span> <span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// Defines a variable named 'x' which holds an integer value of 5.</span>
</code></pre>
<p>Since parenthesis-based direct initialization can’t be used for all types of initialization, another common method for initialization and assignment is <strong>list initialization</strong>. This is very similar to to direct initialization only it uses curly braces instead of parentheses. Some additional features of list initialization to mention are that if no value is specified, <strong>value initialization</strong> will initialize the variable to some default value (usually 0 or empty). Additionally, if a value is used to initialize that would require conversion, before being valid, the statement will result in an error (which can be useful if you are expecting a value of the type specified for that variable).</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> width<span class="token punctuation">{</span> <span class="token number">5</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>    <span class="token comment">// Direct list initialization, creating a variable named 'width' and setting its value to 5.</span>
<span class="token keyword">int</span> width <span class="token operator">=</span> <span class="token punctuation">{</span> <span class="token number">5</span> <span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// Copy list initialization, creating a variable named 'width' and setting its value to 5.</span>

<span class="token keyword">int</span> width<span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// Value initialization (defaults to 0).</span>

<span class="token keyword">int</span> width<span class="token punctuation">{</span> <span class="token number">4.5</span> <span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// Will result in an error because you're attempting to set width (for which we expect an integer) to 4.5</span>
                  <span class="token comment">// (which is a decimal and would require the type to be double).</span>
</code></pre>
<p>Some best practices to follow are to favor direct list initialization whenever possible and to initialize your variables upon creation (preferably to perform instantiation and initialization in the same statement).</p>
<h4 id="note-on-uninitialized-variables-and-undefined-behaviour">Note on Uninitialized Variables and Undefined Behaviour</h4>
<p>A variable that is uninitialized is a variable that has not been given a value. Recall that when a variable is initialized, it is given a value at definition (the statement which defined the variable). Another way for a variable to acquire a value is by assignment in which it is given a value in some statement that occurs after definition. If a variable is declared without being given a value via initialization or assignment, it is considered <strong>uninitialized</strong>. Using an uninitialized variable can lead to <strong>undefined behaviour</strong>, because when a variable is declared but not initialized, your code will just use whatever value is already located at the location in memory used for that variable. This can lead to your program producing different results every run, producing incorrect results consistently, your program behaving inconsistently, your program crashing unexpectedly, and more. It’s best to avoid this entirely by sticking to the best practice of always initializing your variables.</p>
<h3 id="output-and-input-with-the-console">Output and Input with the Console</h3>
<p>Note that in order to receive keyboard input from the console and to output data to the console, we’ll need to use the input/output library from the C++ standard library. To do so, be sure to include it by having <code>#include &lt;iostream&gt;</code> at the top of your code.</p>
<p>The variable <code>std::cout</code> (where <em>cout</em> means character output) is used to send data to the console to be printed as text. Use the insertion operator (<code>&lt;&lt;</code>) to send text to the console to be printed.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token comment">// Include the standard input/output library to be able to output text to the console.</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
  std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Hello world!"</span><span class="token punctuation">;</span> <span class="token comment">// Send the text "Hello world!" to the console to be printed.</span>
  <span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span> <span class="token comment">// Return 0 to indicate that main() has run successfully.</span>
<span class="token punctuation">}</span>
</code></pre>
<p>The value of variables can also be printed to the console using <code>std::cout</code>.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
  <span class="token keyword">int</span> x <span class="token operator">=</span> <span class="token number">5</span><span class="token punctuation">;</span>
  std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> x<span class="token punctuation">;</span> <span class="token comment">// Will output '5' to the console.</span>
  <span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>The insertion operator can be used multiple times in a chain to combine multiple strings or combine strings and values of variables.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
  <span class="token keyword">int</span> x <span class="token operator">=</span> <span class="token number">5</span><span class="token punctuation">;</span>
  std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"x ="</span> <span class="token operator">&lt;&lt;</span> x<span class="token punctuation">;</span> <span class="token comment">// Will output 'x = 5' to the console.</span>
  <span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>The <code>\n</code> character in a string will cause the console to print whatever comes after on a new line.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Hello World\n"</span> <span class="token operator">&lt;&lt;</span> <span class="token string">"My name is Brandon."</span><span class="token punctuation">;</span>
    <span class="token comment">/* 
    *  Output:
    *  Hello World
    *  My name is Brandon.
    */</span> 
<span class="token punctuation">}</span>
</code></pre>
<p>The variable <code>std::cin</code> is used to receive keyboard input from the console. The extraction operator (<code>&gt;&gt;</code>) is used to read the keyboard input from this variable and store it in another variable.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>string user<span class="token punctuation">{</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>  <span class="token comment">// Use direct list initialization to initialize the variable user</span>
                          <span class="token comment">// containing an empty string.</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Hello, what is your name: "</span><span class="token punctuation">;</span>  <span class="token comment">// Output to the console prompting the user to</span>
                                                <span class="token comment">// type their name.</span>
    std<span class="token operator">::</span>cin <span class="token operator">&gt;&gt;</span> user<span class="token punctuation">;</span>  <span class="token comment">// Initialize the name that the user typed to the variable named user.</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Hi, "</span> <span class="token operator">&lt;&lt;</span> user <span class="token operator">&lt;&lt;</span> <span class="token string">" my name is Jarvis."</span><span class="token punctuation">;</span>  <span class="token comment">// Print introduction addressing</span>
                                                           <span class="token comment">// the user by name.</span>
<span class="token punctuation">}</span>
</code></pre>
<h3 id="literals-operators-and-expressions">Literals, Operators, and Expressions</h3>
<p><strong>Literals</strong> are fixed values that are inserted directly into the source code.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Hello World!"</span>  <span class="token comment">// "Hello World!" is a literal</span>
<span class="token keyword">int</span> x<span class="token punctuation">{</span> <span class="token number">5</span> <span class="token punctuation">}</span>                   <span class="token comment">// 5 is a literal</span>
</code></pre>
<p>An <strong>operator</strong> is a symbol that denotes a specific operation to be performed. <strong>Operands</strong> are the input values upon which the operation is performed. <em>Unary</em>, <em>binary</em>, and <em>ternary</em> operators act on one, two, and three operands, respectively.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">x <span class="token operator">=</span> <span class="token operator">-</span><span class="token number">5</span>  <span class="token comment">// The operator- is unary, acting only on 5 to make it -5.</span>
y <span class="token operator">=</span> <span class="token number">3</span> <span class="token operator">+</span> <span class="token number">4</span> <span class="token comment">// The operator+ is binary, taking the left operand of 3 and </span>
          <span class="token comment">// the right operand of 4 and summing the two to produce 7.</span>
</code></pre>
<p>Mathematical operators follow the same order of order of operations as they do in mathematics: parenthesis, exponents, multiplication/division, addition/subtraction.</p>
<p><strong>Expressions</strong> are combinations of literals, variables, and explicit function calls that can be evaluated to a single result. You can use expressions wherever C++ expects a single value.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> z<span class="token punctuation">{</span> <span class="token punctuation">(</span><span class="token number">2</span> <span class="token operator">*</span> <span class="token number">3</span><span class="token punctuation">)</span> <span class="token operator">+</span> <span class="token number">4</span> <span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// (2 * 3) + 4 is the expression that evaluates </span>
                      <span class="token comment">// to 10 before being used as the value to </span>
                      <span class="token comment">// initialize z.</span>
</code></pre>
<h2 id="functions">Functions</h2>
<h3 id="defining-functions">Defining Functions</h3>
<p><strong>Functions</strong> are reusable sequences of statements designed to do a particular job. When executing statements inside a function, the program may encounter a <strong>function call</strong>, which tells the CPU to interrupt the current function, execute another function, and then return. The function initiating the function call is referred to as the <strong>caller</strong> and the function being initiated is referred to as the <strong>callee</strong>.</p>
<p>The syntax of a function is as follows, starting with the return-type, followed by the function identifier, followed by parentheses, and followed by brackets containing the code, known as the <strong>function body</strong>, that will be run when that function is called.</p>
<h4 id="function-format">Function Format</h4>
<pre><code>return-type identifier()
{
	// code to be executed
}
</code></pre>
<p>Note that functions cannot be defined within other functions, unlike in Python.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">int</span>  <span class="token function">foo</span><span class="token punctuation">(</span><span class="token punctuation">)</span>  <span class="token comment">// Illegal: this function is nested inside function main()</span>
	<span class="token punctuation">{</span>
		std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"foo!\n"</span><span class="token punctuation">;</span>
		<span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token function">foo</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>  <span class="token comment">// function call to foo()</span>
	<span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h3 id="return-values">Return Values</h3>
<p>When defining a function, we have to define the <strong>return-type</strong>. Once that is defined, we know what type of value to expect when a function is executed. Therefore, in the function body, we expect a <strong>return statement</strong> followed by a value of the same type as the function’s return-type.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">foo</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">return</span> <span class="token number">2</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">double</span> <span class="token function">bar</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">return</span> <span class="token number">0.2</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Wherever we see a function call, we can treat it as an expression with the same type as the function’s return-type.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"foo() returns "</span> <span class="token operator">&lt;&lt;</span> <span class="token function">foo</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>  <span class="token comment">// foo() can be treated as an expression that</span>
	<span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>                                <span class="token comment">// evaluates to an integer.</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>foo() returns 2
</code></pre>
<p>The return-type <strong>void</strong> is used when a function doesn’t need to return a value.</p>
<p>Note that failing to return a value in a function for which we expect a non-void return value will lead to undefined behavior. Therefore, it’s best practice to always explicitly return a value for non-void return-type functions.</p>
<p>Notice that <code>main()</code> is a function with an integer return-type. The integer returned from <code>main()</code> is called the <strong>status code</strong>, and is used to indicate whether or not the program ran successfully. Non-zero status codes generally indicate a failure of some sort.</p>
<p>The C++ standard library defines the meaning of 3 status codes: <code>0</code>, <code>EXIT_SUCCESS</code>, and <code>EXIT_FAILURE</code>. To use them, be sure to include <code>&lt;cstdlib&gt;</code> in your code. <code>EXIT_SUCCESSS</code> is used to indicate that the program terminated successfully and <code>EXIT_FAILURE</code> is used to indicate that the program did not execute successfully.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;cstdlib&gt;</span> </span><span class="token comment">// for EXIT_SUCCESS and EXIT_FAILURE</span>

<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">return</span>  EXIT_SUCCESS<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Once a function executes a return statement, the called function will stop and the code will continue from the callee function.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">int</span> <span class="token function">foo</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token number">2</span><span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"last line of foo()"</span><span class="token punctuation">;</span>	<span class="token comment">// This line will not be executed because it is after</span>
<span class="token punctuation">}</span>                                       <span class="token comment">// the execution of the return statement.</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"foo() returns "</span> <span class="token operator">&lt;&lt;</span> <span class="token function">foo</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>A good guideline to follow when determining whether a segment of code should be converted into a function is to <strong>DRY</strong>, which stands for <strong>don’t repeat yourself</strong>. If you find yourself reusing the same segment of code, it can probably be turned into a function for simplicity.</p>
<h3 id="parameters-and-arguments">Parameters and Arguments</h3>
<p><strong>Function parameters</strong> are variables used in a function that are initialized with a value provided by the caller of the function and are specified in the parentheses of the function definition. You can specify multiple</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">multiplier</span><span class="token punctuation">(</span><span class="token keyword">int</span> x<span class="token punctuation">,</span> <span class="token keyword">int</span> y<span class="token punctuation">)</span>	<span class="token comment">// The function has two parameters: x and y</span>
<span class="token punctuation">{</span>                               <span class="token comment">// both of which the function expects to be </span>
    <span class="token keyword">return</span> x <span class="token operator">*</span> y<span class="token punctuation">;</span>               <span class="token comment">// integers.</span>
<span class="token punctuation">}</span>
</code></pre>
<p>An <strong>argument</strong> is the value passed from the caller into the function when the function call is made.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token comment">// 2 and 3 are the arguments of the function call of multiplier().</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"foo() returns "</span> <span class="token operator">&lt;&lt;</span> <span class="token function">doubler</span><span class="token punctuation">(</span><span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">)</span><span class="token punctuation">;</span>  
<span class="token punctuation">}</span>
</code></pre>
<p>Note that function arguments may not always be evaluated left to right. If several parameters consist of function outputs, ensure that the order in which they are called doesn’t matter. If it does matter, run the functions separately and define their outputs as variables in the correct order before passing them in as arguments.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token function">func</span><span class="token punctuation">(</span><span class="token function">a</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">,</span> <span class="token function">b</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// a() or b() may be called first.</span>
</code></pre>
<pre class=" language-cpp"><code class="prism  language-cpp">a_var <span class="token operator">=</span> <span class="token function">a</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>	
b_var <span class="token operator">=</span> <span class="token function">b</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token function">func</span><span class="token punctuation">(</span><span class="token function">a</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">,</span> <span class="token function">b</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>	<span class="token comment">//a() will be called before b().</span>
</code></pre>
<h3 id="local-scope">Local Scope</h3>
<p>Function parameters and variables defined within a function body are called <strong>local variables</strong>.  The <strong>lifetime</strong> of local variables is from the variable’s point of instantiation to the end of the function execution. A variable is considered <strong>in scope</strong> if the identifier can be accessed and is considered <strong>out of scope</strong> if it cannot be accessed.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token comment">// Neither x nor y are in scope at this line.</span>
	<span class="token keyword">int</span> x <span class="token operator">=</span> <span class="token number">3</span><span class="token punctuation">;</span>	<span class="token comment">// x is in scope from this line until the end brace of main().</span>
	x <span class="token operator">=</span> <span class="token number">2</span> <span class="token operator">*</span> x<span class="token punctuation">;</span>	<span class="token comment">// y is not in the scope.</span>

	<span class="token keyword">int</span> y <span class="token operator">=</span> <span class="token number">2</span><span class="token punctuation">;</span>	<span class="token comment">// y is in scope from this line until the end brace of main().</span>
	y <span class="token operator">=</span> <span class="token number">2</span> <span class="token operator">*</span> y<span class="token punctuation">;</span>	<span class="token comment">// x is also in the scope here.</span>
<span class="token punctuation">}</span>	<span class="token comment">// x and y leave the scope at this line.</span>
</code></pre>
<p>Another thing to consider when determining a variable’s scope is <strong>functional separation</strong>. When a function is called from another function, the called function will only work with variables within its local scope. That means the called function can share the same identifiers as those present in the caller function and there will be no issues, because when statements are being executed in the called function, they will only reference variables local to that called function.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">double_and_add</span><span class="token punctuation">(</span><span class="token keyword">int</span> x<span class="token punctuation">,</span> <span class="token keyword">int</span> y<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	x <span class="token operator">=</span> <span class="token number">2</span> <span class="token operator">*</span> x<span class="token punctuation">;</span>		<span class="token comment">// Although x is an identifier in main, this reassignment won't change</span>
	y <span class="token operator">=</span> <span class="token number">2</span> <span class="token operator">*</span> y<span class="token punctuation">;</span>		<span class="token comment">// the value of x from main. Same for y.</span>
	<span class="token keyword">return</span> x <span class="token operator">+</span> y<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">int</span> x <span class="token operator">=</span> <span class="token number">3</span><span class="token punctuation">;</span>
	<span class="token keyword">int</span> y <span class="token operator">=</span> <span class="token number">4</span><span class="token punctuation">;</span>
	<span class="token keyword">int</span> z <span class="token operator">=</span> <span class="token function">double_and_add</span><span class="token punctuation">(</span>x<span class="token punctuation">,</span> y<span class="token punctuation">)</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"x: "</span> <span class="token operator">&lt;&lt;</span> x <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"y: "</span> <span class="token operator">&lt;&lt;</span> y <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"z: "</span> <span class="token operator">&lt;&lt;</span> z <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>x: 3
y: 4
z: 14
</code></pre>
<p>As a best practice, local variables should be defined as close to their first use as possible.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"Enter an integer: "</span><span class="token punctuation">;</span>
	<span class="token keyword">int</span>  x<span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>  <span class="token comment">// x defined here</span>
	std<span class="token operator">::</span>cin  <span class="token operator">&gt;&gt;</span>  x<span class="token punctuation">;</span>  <span class="token comment">// and used here</span>

	std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"Enter another integer: "</span><span class="token punctuation">;</span>
	<span class="token keyword">int</span>  y<span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>  <span class="token comment">// y defined here</span>
	std<span class="token operator">::</span>cin  <span class="token operator">&gt;&gt;</span>  y<span class="token punctuation">;</span>  <span class="token comment">// and used here</span>

	<span class="token keyword">int</span>  sum<span class="token punctuation">{</span>  x  <span class="token operator">+</span>  y  <span class="token punctuation">}</span><span class="token punctuation">;</span>  <span class="token comment">// sum defined here</span>
	std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"The sum is: "</span>  <span class="token operator">&lt;&lt;</span>  sum  <span class="token operator">&lt;&lt;</span>  <span class="token string">'\n'</span><span class="token punctuation">;</span>  <span class="token comment">// and used here</span>
	
	<span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h3 id="using-functions-effectively">Using Functions Effectively</h3>
<p>The general guidelines for determining when to refactor a set of code into a function and establishing the structure of the function is as follows.</p>
<ul>
<li>Statements that reappear multiple times within your code should be made into a function (DRY: don’t repeat yourself).</li>
<li>Code that has a well defined input and output are good candidates to be turned into a function, especially if the code is complex.</li>
<li>A function should generally perform one, and only one, task.</li>
<li>When a function becomes too long, it could be advantageous to split that function into multiple, smaller sub-functions.</li>
</ul>
<p>The advantages to separating your code into functions in accordance with the above guidelines is as follows.</p>
<ul>
<li>Organization: Separating code into functions makes it more readable, less complex, and more manageable.</li>
<li>Reusability: Functions can be reused in your code, reducing copy/paste errors and duplicate code.</li>
<li>Testing: By reducing code redundancy, there is less code to test. By testing and ensuring that a function works, we can be confident that it will perform properly at every instance that it is called.</li>
<li>Extensibility: Functions can be extended to handle cases that we didn’t initially account for by modifying just the function body.</li>
<li>Abstraction: You only need to know a function’s name, its inputs, its outputs, and where it’s located to use the function effectively, lowering the amount of knowledge by other people to effectively use a function.</li>
</ul>
<h2 id="formatting">Formatting</h2>
<h3 id="whitespace-and-basic-formatting">Whitespace and Basic Formatting</h3>
<p>Characters used for formatting purposes are known as <strong>whitespace</strong>. This mostly consists of spaces, tabs, and newlines. C++ is a whitespace-independent language, meaning the compiler ignores the whitespace when compiling code (except for those within text literals). As a result, the following functions, despite being formatted differently, all perform the same action.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span>  <span class="token keyword">int</span>  y<span class="token punctuation">)</span>  <span class="token punctuation">{</span>  <span class="token keyword">return</span>  x  <span class="token operator">+</span>  y<span class="token punctuation">;</span>  <span class="token punctuation">}</span>
</code></pre>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span>  <span class="token keyword">int</span>  y<span class="token punctuation">)</span>  <span class="token punctuation">{</span>
<span class="token keyword">return</span>  x  <span class="token operator">+</span>  y<span class="token punctuation">;</span>  <span class="token punctuation">}</span>
</code></pre>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span>  <span class="token keyword">int</span>  y<span class="token punctuation">)</span>
<span class="token punctuation">{</span>  <span class="token keyword">return</span>  x  <span class="token operator">+</span>  y<span class="token punctuation">;</span>  <span class="token punctuation">}</span>
</code></pre>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span>  <span class="token keyword">int</span>  y<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
<span class="token keyword">return</span>  x  <span class="token operator">+</span>  y<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Within text literals, newlines are not allowed.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> "Hello
World<span class="token operator">!</span>"<span class="token punctuation">;</span> <span class="token comment">//not allowed</span>
</code></pre>
<p>Text literals separated by nothing but whitespace will be concatenated.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Hello "</span>
<span class="token string">"World!"</span><span class="token punctuation">;</span> <span class="token comment">// "Hello " and "World!" will be concatenated to "Hello World!"</span>
</code></pre>
<pre><code>Hello World!
</code></pre>
<p>Because C++ is a whitespace-independent language, convention generally dictates following styles that produce the most readable code and provide the most consistency.</p>
<p>Using tabs or spaces comes down to personal preference, although it would probably be best to set an IDE to produce a certain number of spaces upon pressing tab to ensure that comments and code are still readable when viewed by different text editors.</p>
<p>There are two generally accepted styles for function braces. The Google C++ style guide recommends having the open curly brace in the same line as the statement defining the function. This reduces vertical whitespace and allows you to fit more code on the screen.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>         <span class="token comment">// Google C++ style guide has open curly brace in the same</span>
    <span class="token function">do_something</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>  <span class="token comment">// line as function header.</span>
<span class="token punctuation">}</span>
</code></pre>
<p>The alternative is to have the open brace on its own line. This makes the code more readable and makes it easier to catch brace mismatch errors.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>                    <span class="token comment">// Open curly brace on its own line.</span>
    <span class="token function">do_something</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Each statement within a curly brace should be on its own line that is one indentation level below that containing the curly brace.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token function">do_something</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>  <span class="token comment">// This statement is one indentation beyond that of the</span>
<span class="token punctuation">}</span>                    <span class="token comment">// curly braces.</span>
</code></pre>
<p>Lines should not be longer than 80 characters. If a line is longer, split the line, in a reasonable place, into multiple lines. Common conventions include having the following line at one indentation level beyond that of the initial line or aligning the following line with some similar/reasonable code in the preceding line.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"What the fuck did you just fucking say about me, you little"</span> 
        <span class="token string">"bitch? I'll have you know I graduated top of my class."</span><span class="token punctuation">;</span>
        <span class="token comment">// Having the continuing line at one indentation beyond the initial.</span>
<span class="token punctuation">}</span>
</code></pre>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"What the fuck did you just fucking say about me, you little"</span> 
                 <span class="token string">"bitch? I'll have you know I graduated top of my class."</span><span class="token punctuation">;</span>
                 <span class="token comment">// Aligning the continuing line with the beginning of the text</span>
                 <span class="token comment">// from the preceding line.</span>
<span class="token punctuation">}</span>
</code></pre>
<p>If splitting a line at a place containing an operator, the operator should start at the beginning of the following line.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token number">3</span> <span class="token operator">*</span> <span class="token number">4</span> <span class="token operator">*</span> <span class="token number">5</span>
                 <span class="token operator">+</span> <span class="token number">5</span> <span class="token operator">*</span> <span class="token number">6</span> <span class="token operator">*</span> <span class="token number">7</span>
                 <span class="token operator">+</span> <span class="token number">8</span> <span class="token operator">*</span> <span class="token number">9</span> <span class="token operator">*</span> <span class="token number">10</span><span class="token punctuation">;</span>
</code></pre>
<p>When defining multiple variables or commenting on multiple lines, whitespace can be used to align the assignment operator or the beginning of the comments to make things more readable.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">alpha <span class="token operator">=</span> <span class="token number">1</span>  <span class="token comment">// Defining a constant, alpha</span>
d_theta_dt <span class="token operator">=</span> <span class="token number">4</span>  <span class="token comment">// Defining the derivative of theta.</span>
</code></pre>
<p>This is more readable:</p>
<pre class=" language-cpp"><code class="prism  language-cpp">alpha      <span class="token operator">=</span> <span class="token number">1</span>  <span class="token comment">// Defining a constant, alpha</span>
d_theta_dt <span class="token operator">=</span> <span class="token number">4</span>  <span class="token comment">// Defining the derivative of theta.</span>
</code></pre>
<p>It can be helpful to separate blocks of code with whitespace to promote readability.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token comment">// cout lives in the iostream library</span>
std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"Hello world!\n"</span><span class="token punctuation">;</span>
<span class="token comment">// these comments make the code hard to read</span>
std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"It is very nice to meet you!\n"</span><span class="token punctuation">;</span>
<span class="token comment">// especially when all bunched together</span>
std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"Yeah!\n"</span><span class="token punctuation">;</span>
</code></pre>
<p>This is more readable:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token comment">// cout lives in the iostream library</span>
std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"Hello world!\n"</span><span class="token punctuation">;</span>

<span class="token comment">// these comments make the code hard to read</span>
std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"It is very nice to meet you!\n"</span><span class="token punctuation">;</span>

<span class="token comment">// especially when all bunched together</span>
std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"Yeah!\n"</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="forward-declarations-and-definitions">Forward Declarations and Definitions</h3>
<p>Consider the following code.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"The sum of 3 and 4 is: "</span>  <span class="token operator">&lt;&lt;</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token number">3</span><span class="token punctuation">,</span>  <span class="token number">4</span><span class="token punctuation">)</span>  <span class="token operator">&lt;&lt;</span>  <span class="token string">'\n'</span><span class="token punctuation">;</span>
    <span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span>  <span class="token keyword">int</span>  y<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">return</span>  x  <span class="token operator">+</span>  y<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>If you attempt to compile this code, it will result in the following error.</p>
<pre><code>error C3861: 'add': identifier not found
</code></pre>
<p>This is because the code starts with <code>main()</code> and encounters the first statement where a call to the function <code>add()</code>. The issue is that <code>add()</code> has not been defined yet, because the code started with <code>main()</code> and add isn’t defined until after <code>main()</code>. One simple fix to this is to simply move the function definition for <code>add()</code> before the function definition for <code>main()</code>.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span>  <span class="token keyword">int</span>  y<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">return</span>  x  <span class="token operator">+</span>  y<span class="token punctuation">;</span>
<span class="token punctuation">}</span>  <span class="token comment">// Since add() is defined before main(), our code will compile and run.</span>

<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"The sum of 3 and 4 is: "</span>  <span class="token operator">&lt;&lt;</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token number">3</span><span class="token punctuation">,</span>  <span class="token number">4</span><span class="token punctuation">)</span>  <span class="token operator">&lt;&lt;</span>  <span class="token string">'\n'</span><span class="token punctuation">;</span>
    <span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Another solution is to use a <strong>forward declaration</strong>, which is used to declare a function, object, variable, etc. before it is defined. The forward declaration for a function is called a <strong>function prototype</strong> and consists of the function header followed by a semicolon. This is especially useful if we have several functions that rely on one another.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span>  <span class="token keyword">int</span>  y<span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// This function prototype is the forward</span>
                           <span class="token comment">// declaration for our function, add().</span>
<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"The sum of 3 and 4 is: "</span>  <span class="token operator">&lt;&lt;</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token number">3</span><span class="token punctuation">,</span>  <span class="token number">4</span><span class="token punctuation">)</span>  <span class="token operator">&lt;&lt;</span>  <span class="token string">'\n'</span><span class="token punctuation">;</span>
    <span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>  <span class="token comment">// When this is ran, add() will have already been declared</span>
<span class="token punctuation">}</span>               <span class="token comment">// and is defined in the lines below.</span>

<span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span>  <span class="token keyword">int</span>  y<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">return</span>  x  <span class="token operator">+</span>  y<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Note that a function with the same identifier and different number/type of parameters is treated as an entirely different function. The following example has two functions with the identifier <code>add</code>, but will compile and execute without error because one function definition has two integer parameters and the other has three integer parameters.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">int</span> <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span> x<span class="token punctuation">,</span> <span class="token keyword">int</span> y<span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token keyword">int</span> <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span> x<span class="token punctuation">,</span> <span class="token keyword">int</span> y<span class="token punctuation">,</span> <span class="token keyword">int</span> z<span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"The sum of 3 and 4 is: "</span> <span class="token operator">&lt;&lt;</span> <span class="token function">add</span><span class="token punctuation">(</span><span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> <span class="token string">'\n'</span><span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"The sum of 3, 4, and 5 is: "</span> <span class="token operator">&lt;&lt;</span> <span class="token function">add</span><span class="token punctuation">(</span><span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">5</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> <span class="token string">'\n'</span><span class="token punctuation">;</span>
    <span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span> <span class="token keyword">int</span>  y<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">return</span>  x <span class="token operator">+</span> y<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span> <span class="token keyword">int</span>  y<span class="token punctuation">,</span> <span class="token keyword">int</span> z<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">return</span>  x <span class="token operator">+</span> y <span class="token operator">+</span> z<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>The sum of 3 and 4 is: 7
The sum of 3, 4, and 5 is: 12
</code></pre>
<p>Note the <strong>one definition rule</strong>:</p>
<ol>
<li>Within a given file, a function, object, type, or template can only have one definition.</li>
<li>Within a given program (which can span over multiple files), an object or normal function can have only one definition.</li>
<li>Types, templates, inline functions, and variables are allowed to have identical definitions in multiple files.</li>
</ol>
<h3 id="separating-a-program-across-multiple-files">Separating a Program Across Multiple Files</h3>
<p>For organization and reusability, it may be a good idea to split your codes into multiple files. Consider the following example.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span>  <span class="token keyword">int</span>  y<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">return</span>  x  <span class="token operator">+</span>  y<span class="token punctuation">;</span>
<span class="token punctuation">}</span>  <span class="token comment">// Since add() is defined before main(), our code will compile and run.</span>

<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"The sum of 3 and 4 is: "</span>  <span class="token operator">&lt;&lt;</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token number">3</span><span class="token punctuation">,</span>  <span class="token number">4</span><span class="token punctuation">)</span>  <span class="token operator">&lt;&lt;</span>  <span class="token string">'\n'</span><span class="token punctuation">;</span>
    <span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Let’s say we want to move <code>add()</code> into another file entitled <em>add.cpp</em>. Start by right clicking on the project on the right side of the Visual Studio IDE, &gt;&gt; Add &gt;&gt; New Item. Create a new .cpp file and move the function into that file. In your main file, use a forward declaration to ensure that your program knows to look for and define the <code>add()</code> function.</p>
<p><strong>add.cpp</strong></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span> <span class="token keyword">int</span>  y<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">return</span>  x <span class="token operator">+</span> y<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>main.cpp</strong></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">int</span> <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span> x<span class="token punctuation">,</span> <span class="token keyword">int</span> y<span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"The sum of 3 and 4 is: "</span> <span class="token operator">&lt;&lt;</span> <span class="token function">add</span><span class="token punctuation">(</span><span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> <span class="token string">'\n'</span><span class="token punctuation">;</span>
    <span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Compiling and running will produce the following, expected, output.</p>
<pre><code>The sum of 3 and 4 is: 7
</code></pre>
<h3 id="naming-collisions-and-namespaces">Naming Collisions and Namespaces</h3>
<h4 id="naming-collision">Naming Collision</h4>
<p>A <strong>naming collision</strong> is a type of error that occurs when two identical identifiers are introduced into the same program such that the compiler is unable to differentiate the two.</p>
<p>Consider the following two files that exist in the same directory:</p>
<p><strong>a.cpp</strong></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">void</span>  <span class="token function">myFcn</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  x<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>main.cpp</strong></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">void</span>  <span class="token function">myFcn</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token number">2</span>  <span class="token operator">*</span>  x<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>The compiler will be able to compile both <em>a.cpp</em> and <em>main.cpp</em> just fine but when the linker attempts to execute, it’ll find conflicting definitions for <code>myFcn()</code> and result in an error.</p>
<p>Naming collisions are often introduced in separate files of a program or in the same file often when using <code>#include</code> and resulting in there being multiple definitions of a function or global variable.</p>
<h4 id="namespace">Namespace</h4>
<p>A <strong>namespace</strong> is a region that allows you to declare names inside for the purpose of disambiguation. This ensures that any identifier declared inside the namespace won’t be mistaken for another identical name outside the scope of the namespace.</p>
<p>Any name defined outside of a function, class, and namespace is considered part of the <strong>global namespace</strong>. In the above example, both <code>main()</code> and <code>myFcn()</code> existed inside the global namespace, however because of conflicting definitions within that namespace, we received an error.</p>
<p><code>std</code> in <code>std::cout</code> and <code>std::cin</code> is the name of the namespace used for the C++ standard library. This ensures that the identifiers of new code doesn’t conflict with the existing identifiers for those in the C++ standard library and result in an error.</p>
<p>Consider that in <code>std::cout</code> and <code>std::cin</code>, when we want to access the <code>cout</code> and <code>cin</code> operators, we started with the name of the namespace, followed by the <strong>scope resolution operator</strong> (<code>::</code>), followed by the names of the variable or functions within that namespace. In this way, we explicitly tell the program to access this specific variable in this specific namespace.</p>
<p>An alternative (although less preferred) method of accessing variables within a namespace is by using a <em>using directive</em> statement. This allows access to all the names within that namespace without having to explicitly specify the namespace every time, effectively importing all names in that namespace into the global namespace. However, this practice defeats the purpose of using namespaces in the first place, and is not preferred.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">using</span>  <span class="token keyword">namespace</span>  std<span class="token punctuation">;</span>  <span class="token comment">// this is a using directive telling the compiler to check the std</span>
                        <span class="token comment">// namespace when resolving identifiers with no prefix</span>

<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"Hello world!"</span><span class="token punctuation">;</span>  <span class="token comment">// cout has no prefix, so the compiler will check to see</span>
    <span class="token comment">// if cout is defined locally or in namespace std</span>
    <span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h3 id="preprocessor-and-directives">Preprocessor and Directives</h3>
<p>Prior to compilation, your code is run through a process called <strong>translation</strong>, which involves a <strong>preprocessor</strong>, which can be thought of as a program that manipulates the text in each code file. <strong>Preprocessor directives</strong> are instructions that start with the <code>#</code> symbol and end with a newline. These instructions tell the preprocessor to perform some text manipulation on the code. Note that directives have their own syntax and do not follow C++ syntax.</p>
<h4 id="include">Include</h4>
<p>The <code>#include</code> directive replaces that line with the contents of the included file. The included contents are then preprocessed and the rest of your file are preprocessed and compiled.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span>  </span><span class="token comment">// Preprocessed contents of file entitled `iostream` are placed here. </span>

<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout  <span class="token operator">&lt;&lt;</span>  <span class="token string">"Hello, world!"</span><span class="token punctuation">;</span>
    <span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h4 id="macro-defines">Macro Defines</h4>
<p>The <code>#define</code> directive can be used to create a <strong>macro</strong>, which is a rule that defines how input text is converted into replacement output text.</p>
<p>Object-like macros are created by starting with <code>#define</code>, followed by the macro identifier, and potentially followed by substitution text. By convention, the macro identifier is typically typed in all caps.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">define</span> identifier                    </span><span class="token comment">// Without substitution text</span>
<span class="token macro property">#<span class="token directive keyword">define</span> identifier substitution_text  </span><span class="token comment">// With substitution text</span>
</code></pre>
<h5 id="object-like-macros-with-substitution-text">Object-Like Macros with Substitution Text</h5>
<p>When the preprocessor encounters a directive with substitution text, it directly replaces future occurrences of the macro identifier with the substitution text.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token macro property">#<span class="token directive keyword">define</span> MY_NAME "Brandon"  </span><span class="token comment">// Object-like macro with substitution text. Wherever MY_NAME is</span>
                           <span class="token comment">// is present in the code after this line, it will be replaced with </span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>                 <span class="token comment">// "Brandon".</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"My name is "</span> <span class="token operator">&lt;&lt;</span> MY_NAME<span class="token punctuation">;</span>
    <span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>After preprocessing:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token comment">// Preprocessed contents of iostream...</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"My name is "</span> <span class="token operator">&lt;&lt;</span> <span class="token string">"Brandon"</span><span class="token punctuation">;</span>  <span class="token comment">// MY_NAME is detected and the text is replaced</span>
    <span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>                                 <span class="token comment">// with "Brandon".</span>
<span class="token punctuation">}</span>
</code></pre>
<h5 id="object-like-macros-without-substitution-text">Object-Like Macros without Substitution Text</h5>
<p>Object-like macros such as the one below are defined without any substitution text and can be used for things such as conditional compilation. They are not used for text substitution like those with text following the identifier.</p>
<h4 id="conditional-compilation">Conditional Compilation</h4>
<p>Conditional compilation determines whether specific segments of code will be compiled or not. Using the directives <code>#ifdef</code>, <code>#ifndef</code>, and <code>#endif</code>, you can specify code blocks that will only be compiled if a certain macro is defined. By convention, the directives for the conditional blocks within a function are written at the same indentation level as the function header.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token macro property">#<span class="token directive keyword">define</span> PRINT_AARON  </span><span class="token comment">// PRINT_AARON is now defined such that all code within conditional</span>
                     <span class="token comment">// directive blocks seeing if PRINT_AARON is defined will run.</span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
<span class="token macro property">#<span class="token directive keyword">ifdef</span> PRINT_BRANDON  </span><span class="token comment">// Since PRINT_BRANDON is not defined, we do not expect this to run.</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"My name is Brandon."</span><span class="token punctuation">;</span>
<span class="token macro property">#<span class="token directive keyword">endif</span></span>

<span class="token macro property">#<span class="token directive keyword">ifdef</span> PRINT_AARON  </span><span class="token comment">// Since PRINT_AARON is defined, we do expect this to run.</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"My name is Aaron."</span><span class="token punctuation">;</span>
<span class="token macro property">#<span class="token directive keyword">endif</span></span>
    
    <span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>After preprocessing:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token operator">/</span> Preprocessed contents of iostream<span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"My name is Aaron."</span><span class="token punctuation">;</span>
    <span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Console output:</p>
<pre><code>My name is Aaron.
</code></pre>
<p>The directive, <code>#ifdef 0</code>, will evaluate to False and run without code contained within that conditional block. This has the same effect as commenting out the code within the conditional block.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
<span class="token macro property">#<span class="token directive keyword">ifdef</span> 0</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"This will not print."</span>  <span class="token comment">// This line will not print.</span>
<span class="token macro property">#<span class="token directive keyword">endif</span></span>
    
    <span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h4 id="scope-of-directives">Scope of Directives</h4>
<p>Directives are only within that file so when defining a macro, it will only exist for a code within the same file as that macro. Additionally, they do not need to be called to take effect like an ordinary variable or function definition as the preprocessor doesn’t understand C++ syntax.</p>
<p>Also note that directives only apply to the code in the lines following the directive.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token macro property">#<span class="token directive keyword">define</span> PRINT_AARON  </span><span class="token comment">// PRINT_AARON is now defined such that all code within conditional</span>
                     <span class="token comment">// directive blocks seeing if PRINT_AARON is defined will run.</span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
<span class="token macro property">#<span class="token directive keyword">ifdef</span> PRINT_BRANDON  </span><span class="token comment">// Since PRINT_BRANDON is not defined, we do not expect this to run.</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"My name is Brandon."</span><span class="token punctuation">;</span>
<span class="token macro property">#<span class="token directive keyword">endif</span></span>

<span class="token macro property">#<span class="token directive keyword">ifdef</span> PRINT_AARON  </span><span class="token comment">// Since PRINT_AARON is defined, we do expect this to run.</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"My name is Aaron."</span><span class="token punctuation">;</span>
<span class="token macro property">#<span class="token directive keyword">endif</span></span>

<span class="token macro property">#<span class="token directive keyword">define</span> PRINT_BRANDON  </span><span class="token comment">// PRINT_BRANDON is now defined such that all code within conditional  </span>
                       <span class="token comment">// directive blocks seeing if PRINT_BRANDON is defined will run.</span>

<span class="token macro property">#<span class="token directive keyword">ifdef</span> PRINT_BRANDON  </span><span class="token comment">// Since PRINT_BRANDON is now defined, so we do expect this to run.</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"My name is Brandon."</span><span class="token punctuation">;</span>
<span class="token macro property">#<span class="token directive keyword">endif</span></span>

    <span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h3 id="header-files">Header Files</h3>
<p>Header files are used to propagate declarations to code files and usually end with a .h extension.</p>
<h4 id="using-header-files">Using Header Files</h4>
<p>Consider the example below that prints <code>Hello, World!</code> to the console.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Hello, world!"</span><span class="token punctuation">;</span>
	<span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p><code>std::cout</code> is able to be used because it has been forward declared in the <code>iostream</code> header file after <code>#include &lt;iostream&gt;</code>.</p>
<h4 id="writing-header-files">Writing Header Files</h4>
<p>Header files typically only contain function and variable declarations and not their definitions. This is done to ensure that the <em>one definition rule</em> isn’t violated. For example, a header file containing a function definition could result in a collision with the function declaration in a .cpp file somewhere.</p>
<p>Header files contain two parts:</p>
<ol>
<li>A header guard</li>
<li>The forward declaration for all identifiers</li>
</ol>
<p>Header files are usually paired with a code file and provide the forward declarations for that corresponding code file. It’s best practice to name the header file the same name as its paired code file (e.g. <code>add.h</code> would contain the forward declarations for <code>add.cpp</code>).</p>
<p>Consider the following example from <a href="#separating-a-program-across-multiple-files">3.3</a> consisting of a main code file, <code>main.cpp</code>, and another file, <code>add.cpp</code>, where <code>main.cpp</code> uses a function declared in <code>add.cpp</code>.</p>
<p><strong>add.cpp</strong></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span> <span class="token keyword">int</span>  y<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">return</span>  x <span class="token operator">+</span> y<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>main.cpp</strong></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">int</span> <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span> x<span class="token punctuation">,</span> <span class="token keyword">int</span> y<span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"The sum of 3 and 4 is: "</span> <span class="token operator">&lt;&lt;</span> <span class="token function">add</span><span class="token punctuation">(</span><span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> <span class="token string">'\n'</span><span class="token punctuation">;</span>
    <span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Consider that for this example, instead of including the forward declaration for <code>add()</code> in <code>main.cpp</code>, we want to use a header file to forward declare <code>add()</code>. We would create a header file named <code>add.h</code> (since we’re forward declaring a function defined in <code>add.cpp</code>) and simply include the forward declaration in there instead of in <code>main.cpp</code>. In <code>main.cpp</code>, we would need to include that header file using <code>#include</code> followed by the header file name in quotations (<code>#include "add.h"</code>) in this case.</p>
<p><strong>add.h</strong></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span> x<span class="token punctuation">,</span> <span class="token keyword">int</span> y<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>add.cpp</strong></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span>  <span class="token function">add</span><span class="token punctuation">(</span><span class="token keyword">int</span>  x<span class="token punctuation">,</span> <span class="token keyword">int</span>  y<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">return</span>  x <span class="token operator">+</span> y<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>main.cpp</strong></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">"add.h"</span></span>

<span class="token keyword">int</span>  <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"The sum of 3 and 4 is: "</span> <span class="token operator">&lt;&lt;</span> <span class="token function">add</span><span class="token punctuation">(</span><span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> <span class="token string">'\n'</span><span class="token punctuation">;</span>
    <span class="token keyword">return</span>  <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>It’s good practice to write a header file for a source file even if the functions in that source file are not being used immediately to promote forward compatibility.</p>
<p><code>#include</code>'s that specify a header file with angled brackets (<code>&lt;&gt;</code>) instead of double quotations (<code>""</code>) will search for header files in a specified <code>include directories</code>, which are configured as part of a project or IDE’s settings. Those specified with double quotations will search for header files in the current directory or specified search directory (specified by the IDE project settings) first before searching the <code>include directories</code>.</p>
<p>Although header files can also include other header files (known as transitive includes) this is not best practice as these includes become implicit rather than explicit when your header file is included somewhere.</p>
<p>Best practice for order of <code>#include</code> statements is first user-defined headers, followed by 3rd party headers, followed by standard library headers. Each section should be sorted alphabetically.</p>
<h4 id="header-guards">Header Guards</h4>
<h2 id="data-types">Data Types</h2>
<h3 id="integer-types">Integer Types</h3>
<p>Integer types are used to store whole numbers. There are four main integer types: <code>short</code>, <code>int</code>, <code>long</code> and <code>long long</code>. These each can either be <code>signed</code>, meaning positive integers, negative integers and zero can be stored, or <code>unsigned</code>, meaning only non-negative integers can be stored. The difference between these data types is the amount of memory required and the range of values they can store. The greater the range of values, the greater the memory required. The range of each type, <code>signed</code> and <code>unsigned</code> is listed in the table below.</p>

<table>
<thead>
<tr>
<th>Type</th>
<th>Range</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>signed short</code></td>
<td>-32,768 to 32,767</td>
</tr>
<tr>
<td><code>unsigned short</code></td>
<td>0 to 65,535</td>
</tr>
<tr>
<td><code>signed int</code></td>
<td>-2,147,483,648 to 2,147,483,647</td>
</tr>
<tr>
<td><code>unsigned int</code></td>
<td>0 to 4,294,967,295</td>
</tr>
<tr>
<td><code>signed long</code></td>
<td>-2,147,483,648 to 2,147,483,647</td>
</tr>
<tr>
<td><code>unsigned long</code></td>
<td>0 to 4,294,967,295</td>
</tr>
<tr>
<td><code>signed long long</code></td>
<td>-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</td>
</tr>
<tr>
<td><code>unsigned long long</code></td>
<td>0 to 18,446,744,073,709,551,615</td>
</tr>
</tbody>
</table><h3 id="floating-point-types">Floating-Point Types</h3>
<p>Floating-point types are used to store numbers that contain decimal or fractional components. There are three floating-point types: <code>float</code>, <code>double</code>, and <code>long double</code>. <code>float</code> has 4 bytes of precision while <code>double</code> and <code>long double</code> have 8 bytes of precision. The higher the precision, the more accurate the numerical representation but the more memory required. For general use, <code>double</code> is usually sufficient.</p>
<p>Floating-points variables can be initialized using scientific notation.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">double</span> avogadros_number <span class="token operator">=</span> <span class="token number">6.0221409e23</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="character-types">Character Types</h3>
<p>Character types are used to store a single character. There are four types: <code>char</code>, <code>char16_t</code>, <code>char32_t</code>, and <code>wchar_t</code>. <code>char</code> can either be <code>signed</code> or <code>unsigned</code>.</p>
<ul>
<li><code>char</code>: The default type. Used for 1 byte character sets such as ASCII.</li>
<li><code>char16_t</code>: Used for 2-byte character sets such as UTF-16.</li>
<li><code>char32_t</code>: Used for 4-byte character sets such as UTF-32.</li>
</ul>
<p>A character literal is declared by enclosing the specific character within a set of single quotations (’).</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">char</span> favorite_letter <span class="token operator">=</span> <span class="token string">'e'</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="boolean-types">Boolean Types</h3>
<p>Booleans use the <code>bool</code> type and simply store <code>true</code> or <code>false</code>. They are usually the result of some sort of comparison expression.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">bool</span> name_is_brandon <span class="token operator">=</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
</code></pre>
<h4 id="comparison-operators">Comparison Operators</h4>
<p>Common operators that are used to compare the values of different variables are listed below.</p>

<table>
<thead>
<tr>
<th>Operation</th>
<th>Operator</th>
</tr>
</thead>
<tbody>
<tr>
<td>Equality</td>
<td><code>==</code></td>
</tr>
<tr>
<td>Inequality</td>
<td><code>!=</code></td>
</tr>
<tr>
<td>Greater Than</td>
<td><code>&gt;</code></td>
</tr>
<tr>
<td>Less Than</td>
<td><code>&lt;</code></td>
</tr>
<tr>
<td>Greater Than or Equal To</td>
<td><code>&gt;=</code></td>
</tr>
<tr>
<td>Less Than or Equal To</td>
<td><code>&lt;=</code></td>
</tr>
</tbody>
</table><pre class=" language-cpp"><code class="prism  language-cpp"><span class="token function">printf</span><span class="token punctuation">(</span><span class="token string">"69 &gt;= 429 evaluates to: %d"</span><span class="token punctuation">,</span> <span class="token number">69</span> <span class="token operator">&gt;=</span> <span class="token number">420</span><span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// Evaluates to false</span>
</code></pre>
<h4 id="logical-operators">Logical Operators</h4>
<p>Common operators used to evaluate Boolean logic on <code>bool</code> types are listed below.</p>

<table>
<thead>
<tr>
<th>Operation</th>
<th>Operator</th>
</tr>
</thead>
<tbody>
<tr>
<td>NOT</td>
<td><code>!</code></td>
</tr>
<tr>
<td>AND</td>
<td><code>&amp;&amp;</code></td>
</tr>
<tr>
<td>OR</td>
<td><code>||</code></td>
</tr>
</tbody>
</table><pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">bool</span> i_am_lactose <span class="token operator">=</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
<span class="token keyword">bool</span> food_has_lactose <span class="token operator">=</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
<span class="token keyword">bool</span> i_can_eat_food <span class="token operator">=</span> food_has_lactose <span class="token operator">&amp;&amp;</span> <span class="token operator">!</span>i_am_lactose<span class="token punctuation">;</span>

<span class="token function">printf</span><span class="token punctuation">(</span><span class="token string">"I can eat the food?: %d"</span><span class="token punctuation">,</span> i_can_eat_food<span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// Evaluates to false </span>
</code></pre>
<h3 id="the-size_t-type">The <code>size_t</code> Type</h3>
<p>The <code>size_t</code> type is used to encode the size of objects. The maximum value it can represent is such that it’s sufficient to represent the maximum size of all objects. It is commonly used as the type of the iterator variable when iterating through arrays.</p>
<h3 id="arrays">Arrays</h3>
<p>Arrays are used to store multiple elements of the same type. They are initialized in the same way you declare an ordinary variable of some type except following the identifier are brackets containing the number of elements in the array. <strong>Note that in doing it this way, each element in the array is uninitialized.</strong></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> my_numbers<span class="token punctuation">[</span><span class="token number">100</span><span class="token punctuation">]</span><span class="token punctuation">;</span> <span class="token comment">// Creates an array that can store 100 int values.</span>
</code></pre>
<p>Another way to initialize an array is by equating it to a  comma, separated list of values contained within a curly braces and neglecting the number inside the brackets.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> my_numbers<span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<p>A specific element in an array is accessed by its index (starting at 0). Use the identifier, followed by brackets containing the index of the value in the array you wish to access.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> value <span class="token operator">=</span> my_numbers<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">;</span> <span class="token comment">// Retrieves the second value of my_numbers</span>
<span class="token function">printf</span><span class="token punctuation">(</span><span class="token string">"The value is %d"</span><span class="token punctuation">,</span> value<span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// Will print out `The value is 3`</span>
</code></pre>
<p>Using brace initialization, you can create an array and initialize all its elements to 0. To do this, declare an array with the number of elements within the brackets and follow it with a set of empty braces. If you use a set of braces containing values, it’ll initialize the first few elements of the array to those and all remaining, undefined elements in the array to 0.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> zeros<span class="token punctuation">[</span><span class="token number">100</span><span class="token punctuation">]</span><span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// Creates a 100-element array where all elements are 0.</span>
<span class="token keyword">int</span> mostly_zeros<span class="token punctuation">[</span><span class="token number">100</span><span class="token punctuation">]</span><span class="token punctuation">{</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">3</span> <span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// Creates a 100-element array where the first</span>
                                  <span class="token comment">// three elements are defined and the rest are</span>
                                  <span class="token comment">// 0.</span>
</code></pre>
<p>A note that arrays created must have a known size beforehand at compile time (in other words you can’t use a non-constant variable to define the size of an array). To create arrays of custom sizes determined at runtime, see the section on <a href="#dynamic-arrays">dynamic arrays</a>.</p>
<h3 id="strings">Strings</h3>
<p>Strings can be thought of as an array of characters. To declare a string literal, enclose the text you wish to convert into a string within a set of double quotations (").</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">char</span> navy_seal_copy_pasta<span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token string">"I'll have you know I graduated top of my class in the Navy Seals."</span><span class="token punctuation">;</span>
</code></pre>
<p>When declaring especially long strings, it is okay to separate them by only whitespace. This can be especially useful for separating strings into multiple lines.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">char</span> expression<span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token string">"Roses are red, "</span>
     <span class="token string">"I forget how this goes, "</span>
     <span class="token string">"I think there's something "</span>
     <span class="token string">"up your nose."</span><span class="token punctuation">;</span>
</code></pre>
<p>Strings can also be declared by equating a char pointer to the string. See the section on pointers for more information.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">char</span><span class="token operator">*</span> name <span class="token operator">=</span> <span class="token string">"Brandon"</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="enumerations">Enumerations</h3>
<p>Enumerations are a type of user-defined type that you can set to a set of predefined values, which is great for modeling categorical concepts. The categories for an enumeration are declared by <code>enum class</code> followed by the name for the user-defined type followed by curly brackets containing a comma, separated list of categories that a variable of that type can be set to.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">enum</span> <span class="token keyword">class</span> <span class="token class-name">Language</span> <span class="token punctuation">{</span>
	English<span class="token punctuation">,</span>
	Spanish<span class="token punctuation">,</span>
	Vietnamese<span class="token punctuation">,</span>
	Cantonese<span class="token punctuation">,</span>
	Mandarin
<span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<p>To assign an enumeration variable to a value, start with the type, followed by the variable identifier, followed by an assignment operator, followed by the category from within the namespace of the type using the <code>::</code>.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">Language my_language <span class="token operator">=</span> Language<span class="token operator">::</span>English<span class="token punctuation">;</span>
</code></pre>
<p>This can be especially useful when using if statements with an  equality operator or switch statements.</p>
<h3 id="classes">Classes</h3>
<p><em>Classes</em> are user-defined types that contain data and functions.</p>
<h4 id="plain-old-data-pod-classes">Plain-Old-Data (POD) Classes</h4>
<p><em>Plain-old-data (POD) classes</em> are a simple type of class that only stores data. They can store data of different types and can be used to represent something. They are defined by the keyword <code>struct</code> followed by the identifier for the class, followed by a set of curly braces initializing the <em>members</em>, which are the different elements of data stored by the class.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;string&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">struct</span> School <span class="token punctuation">{</span>
	std<span class="token operator">::</span>string name<span class="token punctuation">;</span>
	std<span class="token operator">::</span>string country<span class="token punctuation">;</span>
	<span class="token keyword">int</span> student_population<span class="token punctuation">;</span>
	<span class="token keyword">double</span> latitude<span class="token punctuation">;</span>
	<span class="token keyword">double</span> longitude<span class="token punctuation">;</span>
	<span class="token keyword">bool</span> public_institution<span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// Note that the definition must be proceeded by a semicolon.</span>
</code></pre>
<p>Members are accessed by using the dot operator (<code>.</code>).</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	School UCSD<span class="token punctuation">;</span>
	UCSD<span class="token punctuation">.</span>name <span class="token operator">=</span> <span class="token string">"University of California, San Diego"</span><span class="token punctuation">;</span>
	UCSD<span class="token punctuation">.</span>country <span class="token operator">=</span> <span class="token string">"US"</span><span class="token punctuation">;</span>
	UCSD<span class="token punctuation">.</span>student_population <span class="token operator">=</span> <span class="token number">35</span>'<span class="token number">821</span><span class="token punctuation">;</span>
	UCSD<span class="token punctuation">.</span>latitude <span class="token operator">=</span> <span class="token number">32.8328</span><span class="token punctuation">;</span>
	UCSD<span class="token punctuation">.</span>longitude <span class="token operator">=</span> <span class="token operator">-</span><span class="token number">117.2713</span><span class="token punctuation">;</span>
	UCSD<span class="token punctuation">.</span>public_institution <span class="token operator">=</span> <span class="token boolean">true</span><span class="token punctuation">;</span>

	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Name: \t\t"</span> <span class="token operator">&lt;&lt;</span> UCSD<span class="token punctuation">.</span>name <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Country: \t"</span> <span class="token operator">&lt;&lt;</span> UCSD<span class="token punctuation">.</span>country <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Students: \t"</span> <span class="token operator">&lt;&lt;</span> UCSD<span class="token punctuation">.</span>student_population <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Coordinate: \t"</span> <span class="token operator">&lt;&lt;</span> UCSD<span class="token punctuation">.</span>latitude <span class="token operator">&lt;&lt;</span> <span class="token string">", "</span> <span class="token operator">&lt;&lt;</span> UCSD<span class="token punctuation">.</span>longitude 
	<span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Public: \t"</span> <span class="token operator">&lt;&lt;</span> UCSD<span class="token punctuation">.</span>public_institution <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>

	<span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>Name:           University of California, San Diego
Country:        US
Students:       35821
Coordinate:     32.8328, -117.271
Public:         1
</code></pre>
<h5 id="braced-initialization">Braced Initialization</h5>
<p>A POD can be initialized using braces containing the data to be stored in its members. If there is nothing between the braces, all members will be initialized to 0. If there are, it will be assigned to the members in the order in which they are defined within the POD. Any members with unassigned values will be zeroed.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> Restaurant<span class="token punctuation">{</span>
	std<span class="token operator">::</span>string restauraunt_name<span class="token punctuation">;</span>
	<span class="token keyword">int</span> number_of_reviews
	<span class="token keyword">double</span> average_rating<span class="token punctuation">;</span> 
<span class="token punctuation">}</span><span class="token punctuation">;</span>

<span class="token keyword">int</span> main <span class="token punctuation">{</span>
	Restaurant placeA<span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// All fields will be zeroed</span>
	Restaurant placeB<span class="token punctuation">{</span> <span class="token string">"McDonalds"</span><span class="token punctuation">,</span> <span class="token number">9203</span><span class="token punctuation">,</span> <span class="token number">4.67</span> <span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// All fields defined</span>
	Restaurant placeB<span class="token punctuation">{</span> <span class="token string">"ChickFilA"</span><span class="token punctuation">,</span> <span class="token number">651</span> <span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// Name and number of reviews defined</span>
	                                       <span class="token comment">// but average rating is zeroed.</span>
	
	<span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h5 id="structured-binding-declaration">Structured Binding Declaration</h5>
<p>PODs can be used to establish a return type consisting of multiple members. This way, a function can be used to return multiple variables instead of one. The syntax for unpacking multiple variables from a function call is the keyword <code>auto</code> followed by brackets containing a comma separated list of the variables to which you would like to unpack to. <strong>Note that in VS Studio, you have to be using C++17 to do this.</strong></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> ReturnValue <span class="token punctuation">{</span>
    <span class="token comment">// Establish return type containing multiple members.</span>
    <span class="token keyword">int</span> number<span class="token punctuation">;</span>
    <span class="token keyword">bool</span> true_or_false<span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>

ReturnValue <span class="token function">some_function</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment">// Implicitly return the return type with specified members.</span>
    <span class="token keyword">return</span> <span class="token punctuation">{</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token boolean">true</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token comment">// Unpack using auto followed by brackets containing</span>
    <span class="token comment">// variables to unpack to.</span>
    <span class="token keyword">auto</span> <span class="token punctuation">[</span>my_number<span class="token punctuation">,</span> my_truth<span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token function">some_function</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h4 id="unions">Unions</h4>
<p>The <em>union</em> is a special type of class that can be used when a particular variable can be interpreted in several different types.  It is defined similar to POD’s but using the keyword <code>union</code>.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">union</span> Grade <span class="token punctuation">{</span>
	<span class="token keyword">char</span> letter_grade<span class="token punctuation">;</span>
	<span class="token keyword">int</span> score<span class="token punctuation">;</span>
	<span class="token keyword">double</span> percentage<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>To assign a variable of the specified union type, write out the type, followed by the identifier followed by a semicolon to declare it. To specify which format to store the information as, use the dot operator on the newly created variable followed by the member of the format that you want to save the information and assign it. The same can be done for accessing the information.</p>
<p>Note that it’s possible to access a union type variable data using the wrong type, leading to unexpected output. For this reason, using this class type to store and access information is not recommended unless absolutely required.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	Grade my_letter_grade<span class="token punctuation">;</span>
	my_letter_grade<span class="token punctuation">.</span>letter_grade <span class="token operator">=</span> <span class="token string">'A'</span><span class="token punctuation">;</span>
	Grade my_score<span class="token punctuation">;</span>
	my_score<span class="token punctuation">.</span>score <span class="token operator">=</span> <span class="token number">94</span><span class="token punctuation">;</span>
	Grade my_percentage<span class="token punctuation">;</span>
	my_percentage<span class="token punctuation">.</span>percentage <span class="token operator">=</span> <span class="token number">0.94</span><span class="token punctuation">;</span>

	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Letter Grade:  "</span> <span class="token operator">&lt;&lt;</span> my_letter_grade<span class="token punctuation">.</span>letter_grade <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"       Score:  "</span> <span class="token operator">&lt;&lt;</span> my_score<span class="token punctuation">.</span>score <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"  Percentage:  "</span> <span class="token operator">&lt;&lt;</span> my_percentage<span class="token punctuation">.</span>percentage <span class="token operator">&lt;&lt;</span> <span class="token string">"\n\n"</span><span class="token punctuation">;</span>

	<span class="token comment">// This will interpret incorrectly because the type with which the grade</span>
	<span class="token comment">// was saved is not the same as the type with which it is being accessed.</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Incorrect Interpretation:"</span> <span class="token operator">&lt;&lt;</span> my_percentage<span class="token punctuation">.</span>letter_grade 
	<span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>

	<span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>Letter Grade:  A
       Score:  94
  Percentage:  0.94

Incorrect Interpretation:¶
</code></pre>
<h4 id="fully-featured-classes">Fully-Featured Classes</h4>
<p>Fully-featured classes, in addition to storing information in members, have <em>methods</em>, which are functions that can access, manipulate, and return information from members within the class. They are declared in the same way that ordinary functions outside of classes are. They already have access to members.</p>
<p>Consider the following example which models a jar in which you can put in and remove individual jelly beans.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> JellyBeanJar <span class="token punctuation">{</span>
	<span class="token keyword">int</span> jelly_beans <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>

	<span class="token keyword">bool</span> <span class="token function">add_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>jelly_beans <span class="token operator">&lt;</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token keyword">return</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
		jelly_beans <span class="token operator">+</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
		<span class="token keyword">return</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token keyword">bool</span> <span class="token function">remove_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>jelly_beans <span class="token operator">&lt;=</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token keyword">return</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
		jelly_beans <span class="token operator">-</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
		<span class="token keyword">return</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<p>Running the following represents starting with an empty jar, checking the count, adding a bean, and checking the count.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	JellyBeanJar jar<span class="token punctuation">;</span>

	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Start with an empty jar.\n"</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Bean Count: "</span> <span class="token operator">&lt;&lt;</span> jar<span class="token punctuation">.</span>jelly_beans <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Add a bean.\n"</span><span class="token punctuation">;</span>
	jar<span class="token punctuation">.</span><span class="token function">add_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Bean Count: "</span> <span class="token operator">&lt;&lt;</span> jar<span class="token punctuation">.</span>jelly_beans <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>

	<span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>Start with an empty jar.
Bean Count: 0
Add a bean.
Bean Count: 1
</code></pre>
<h5 id="access-control">Access Control</h5>
<p>The problem with the above class is that anyone can just access the <code>jelly_beans</code> member and modify it to an invalid value.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">jar<span class="token punctuation">.</span>jelly_beans <span class="token operator">=</span> <span class="token operator">-</span><span class="token number">3</span><span class="token punctuation">;</span>
</code></pre>
<p>Access control allows you to specify whether certain members or methods are accessible from outside the class. When using a <code>struct</code> to specify private members and methods, use <code>private:</code> and define members and methods after to  make those private.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> JellyBeanJar <span class="token punctuation">{</span>
	<span class="token keyword">bool</span> <span class="token function">add_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>jelly_beans <span class="token operator">&lt;</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token keyword">return</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
		jelly_beans <span class="token operator">+</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
		<span class="token keyword">return</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token keyword">bool</span> <span class="token function">remove_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>jelly_beans <span class="token operator">&lt;=</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token keyword">return</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
		jelly_beans <span class="token operator">-</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
		<span class="token keyword">return</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token keyword">int</span> <span class="token function">count</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">return</span> jelly_beans<span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	
	<span class="token keyword">private</span><span class="token operator">:</span>
		<span class="token comment">// The number of jelly beans is not directly accessible because</span>
		<span class="token comment">// jelly_beans is declared in this private section. All the methods</span>
		<span class="token comment">// defined above are outside of this section and are considered public.</span>
		<span class="token keyword">int</span> jelly_beans <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<p>By default, members and methods in <code>struct</code> are public unless specified after <code>private:</code>. Instead of using <code>struct</code>, you can also use <code>class</code>, which is identical in function except members and methods are private by default unless specified after <code>public:</code>.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">class</span> <span class="token class-name">JellyBeanJar</span> <span class="token punctuation">{</span>
	<span class="token comment">// By default, jelly_beans is private.</span>
	<span class="token keyword">int</span> jelly_beans <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>

	<span class="token keyword">public</span><span class="token operator">:</span>
		<span class="token comment">// These functions declared in the public section are accessible from</span>
		<span class="token comment">// outside the class.</span>
		<span class="token keyword">bool</span> <span class="token function">add_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">if</span> <span class="token punctuation">(</span>jelly_beans <span class="token operator">&lt;</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token keyword">return</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
			jelly_beans <span class="token operator">+</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
			<span class="token keyword">return</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>

		<span class="token keyword">bool</span> <span class="token function">remove_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">if</span> <span class="token punctuation">(</span>jelly_beans <span class="token operator">&lt;=</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token keyword">return</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
			jelly_beans <span class="token operator">-</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
			<span class="token keyword">return</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>

		<span class="token keyword">int</span> <span class="token function">count</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">return</span> jelly_beans<span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<h5 id="constructors">Constructors</h5>
<p>Constructors are used to create an instance of a class with members specified from a set of inputs. This can be useful in employing logic to verify inputs and specify members based on those inputs.</p>
<p>Constructors are specified within a class definition by the class identifier, followed by a set of parentheses with specified inputs, followed by curly braces containing statements to assign class members.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> JellyBeanJar <span class="token punctuation">{</span>
	<span class="token comment">// If no inputs are specified, the inital jelly bean count is 0.</span>
	<span class="token function">JellyBeanJar</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		jelly_beans <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token comment">// If an input is specified, make sure it is a valid number before</span>
	<span class="token comment">// assigning the initial jelly bean count. If it is invalid, default</span>
	<span class="token comment">// the number of jelly beans to 0.</span>
	<span class="token function">JellyBeanJar</span><span class="token punctuation">(</span><span class="token keyword">int</span> initial_count<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>initial_count <span class="token operator">&gt;=</span> <span class="token number">0</span><span class="token punctuation">)</span> jelly_beans <span class="token operator">=</span> initial_count<span class="token punctuation">;</span>
		<span class="token keyword">else</span> jelly_beans <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token keyword">bool</span> <span class="token function">add_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>jelly_beans <span class="token operator">&lt;</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token keyword">return</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
		jelly_beans <span class="token operator">+</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
		<span class="token keyword">return</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token keyword">bool</span> <span class="token function">remove_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>jelly_beans <span class="token operator">&lt;=</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token keyword">return</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
		jelly_beans <span class="token operator">-</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
		<span class="token keyword">return</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token keyword">int</span> <span class="token function">count</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">return</span> jelly_beans<span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token keyword">private</span><span class="token operator">:</span>
		<span class="token keyword">int</span> jelly_beans<span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	JellyBeanJar jar1<span class="token punctuation">;</span> <span class="token comment">// By default, initializes to 0 jelly beans.</span>
	JellyBeanJar jar2<span class="token punctuation">{</span> <span class="token number">4</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>

	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Initial Jar Counts\n"</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Jar1: "</span> <span class="token operator">&lt;&lt;</span> jar1<span class="token punctuation">.</span><span class="token function">count</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> <span class="token string">"\t"</span> 
			  <span class="token operator">&lt;&lt;</span> <span class="token string">"Jar2: "</span> <span class="token operator">&lt;&lt;</span> jar2<span class="token punctuation">.</span><span class="token function">count</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Add a bean to each.\n"</span><span class="token punctuation">;</span>
	jar1<span class="token punctuation">.</span><span class="token function">add_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	jar2<span class="token punctuation">.</span><span class="token function">add_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Jar1: "</span> <span class="token operator">&lt;&lt;</span> jar1<span class="token punctuation">.</span><span class="token function">count</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> <span class="token string">"\t"</span>
		      <span class="token operator">&lt;&lt;</span> <span class="token string">"Jar2: "</span> <span class="token operator">&lt;&lt;</span> jar2<span class="token punctuation">.</span><span class="token function">count</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>

	<span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>Initial Jar Counts
Jar1: 0 Jar2: 4
Add a bean to each.
Jar1: 1 Jar2: 5
</code></pre>
<h5 id="destructors">Destructors</h5>
<p>Destructors are functions that execute before the instance is destroyed. To define a destructor, specify a function in the class with the same name as the class except with a tilde (<code>~</code>) before and with a set of empty parentheses (no arguments).</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> SomeClass <span class="token punctuation">{</span>
	<span class="token operator">--</span>snip<span class="token operator">--</span>

	<span class="token operator">~</span><span class="token function">SomeClass</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token comment">// Statements to be executed before the destruction of an instance of</span>
		<span class="token comment">// this class.</span>
		statements<span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token operator">--</span>snip<span class="token operator">--</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<p>Note on members of a class: Members are constructed before the class instance’s constructor is called and they are destructed after the class instance’s destructor is called.</p>
<h5 id="copy-constructors">Copy Constructors</h5>
<p>Copying an instance of a class will simply copy, by value, the members of one class into the other. This is not great practice, particularly when working with classes which have pointer members, as the resulting copy and original will actually point to the same variable, where modifications to one will lead to changes in the other. The solution around this is to implement a <em>copy constructor</em>. This is simply an ordinary constructor that takes its own class as an argument (by reference and usually <code>const</code> to ensure no modifications of the original are made during the process) and creates a new copy with members which are same by value.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> MyString <span class="token punctuation">{</span>
    <span class="token function">MyString</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        name <span class="token operator">=</span> <span class="token keyword">nullptr</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token function">MyString</span><span class="token punctuation">(</span><span class="token keyword">const</span> <span class="token keyword">char</span> name<span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token function">change_name</span><span class="token punctuation">(</span>name<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token comment">// Here is the copy constructor</span>
    <span class="token function">MyString</span><span class="token punctuation">(</span><span class="token keyword">const</span> MyString<span class="token operator">&amp;</span> other<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        std<span class="token operator">::</span><span class="token function">strncpy</span><span class="token punctuation">(</span>name<span class="token punctuation">,</span> other<span class="token punctuation">.</span>name<span class="token punctuation">,</span> <span class="token function">strlen</span><span class="token punctuation">(</span>other<span class="token punctuation">.</span>name<span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token keyword">void</span> <span class="token function">change_name</span><span class="token punctuation">(</span><span class="token keyword">const</span> <span class="token keyword">char</span> name<span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        std<span class="token operator">::</span><span class="token function">strncpy</span><span class="token punctuation">(</span><span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>name<span class="token punctuation">,</span> name<span class="token punctuation">,</span> <span class="token function">strlen</span><span class="token punctuation">(</span>name<span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>name<span class="token punctuation">[</span><span class="token function">strlen</span><span class="token punctuation">(</span>name<span class="token punctuation">)</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token keyword">char</span><span class="token operator">*</span> name <span class="token operator">=</span> <span class="token keyword">new</span> <span class="token keyword">char</span><span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    MyString string_1<span class="token punctuation">{</span> <span class="token string">"Hello World!"</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
    MyString string_2<span class="token punctuation">{</span> <span class="token string">"Goodbye World!"</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
    MyString string_3<span class="token punctuation">{</span> string_1 <span class="token punctuation">}</span><span class="token punctuation">;</span>
    <span class="token comment">// string_1 name is "Hello World!" and string_3 name is "Hello World!" but</span>
    <span class="token comment">// they do not point to the same location in memory.</span>
    string_3<span class="token punctuation">.</span><span class="token function">change_name</span><span class="token punctuation">(</span><span class="token string">"Disney World!"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token comment">// string_3 name is changed, but this does not change that of string_1</span>

    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"string_1: "</span> <span class="token operator">&lt;&lt;</span> string_1<span class="token punctuation">.</span>name <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"string_2: "</span> <span class="token operator">&lt;&lt;</span> string_2<span class="token punctuation">.</span>name <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"string_3: "</span> <span class="token operator">&lt;&lt;</span> string_3<span class="token punctuation">.</span>name <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>string_1: Hello World!
string_2: Goodbye World!
string_3: Disney World!
</code></pre>
<p>Commenting out the copy constructor from the above example yields the following result. <code>name</code> of <code>string_1</code> and <code>string_3</code> refer to the same location in memory, so modifying one changes the other, which is not the behavior that we want.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">string_1<span class="token operator">:</span> Disney World<span class="token operator">!</span>
string_2<span class="token operator">:</span> Goodbye World<span class="token operator">!</span>
string_3<span class="token operator">:</span> Disney World<span class="token operator">!</span>
</code></pre>
<h5 id="copy-assignment-operators">Copy Assignment Operators</h5>
<p>Copy assignment operators allow us to overwrite an existing instance with the contents of another using the copy operator (<code>=</code>). The syntax for this is to specify a constructor with the class’s type followed by an <code>&amp;</code> (to indicate you are returning a reference to this instance) followed by <code>operator=</code>. Within the arguments, take a <code>const</code> reference to the instance being copied.</p>
<p>Within the copy constructors, it is generally good practice to check if the instance being passed as an argument is actually itself. See the example below for details.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> MyString <span class="token punctuation">{</span>
    <span class="token function">MyString</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        name <span class="token operator">=</span> <span class="token keyword">nullptr</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token function">MyString</span><span class="token punctuation">(</span><span class="token keyword">const</span> <span class="token keyword">char</span> name<span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token function">assign_name</span><span class="token punctuation">(</span>name<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token function">MyString</span><span class="token punctuation">(</span><span class="token keyword">const</span> MyString<span class="token operator">&amp;</span> other<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        std<span class="token operator">::</span><span class="token function">strncpy</span><span class="token punctuation">(</span>name<span class="token punctuation">,</span> other<span class="token punctuation">.</span>name<span class="token punctuation">,</span> <span class="token function">strlen</span><span class="token punctuation">(</span>other<span class="token punctuation">.</span>name<span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token comment">// Here is the copy assignment constructor</span>
    MyString<span class="token operator">&amp;</span> <span class="token keyword">operator</span><span class="token operator">=</span><span class="token punctuation">(</span><span class="token keyword">const</span> MyString<span class="token operator">&amp;</span> other<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token comment">// Checks if other is actually this instance. If so,</span>
        <span class="token comment">// return this instance.</span>
        <span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token keyword">this</span> <span class="token operator">==</span> <span class="token operator">&amp;</span>other<span class="token punctuation">)</span> <span class="token keyword">return</span> <span class="token operator">*</span><span class="token keyword">this</span><span class="token punctuation">;</span>
        <span class="token function">change_name</span><span class="token punctuation">(</span>other<span class="token punctuation">.</span><span class="token function">get_name</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token keyword">return</span> <span class="token operator">*</span><span class="token keyword">this</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token keyword">void</span> <span class="token function">change_name</span><span class="token punctuation">(</span><span class="token keyword">const</span> <span class="token keyword">char</span> name<span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token keyword">delete</span><span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>name<span class="token punctuation">;</span>
        <span class="token function">assign_name</span><span class="token punctuation">(</span>name<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token keyword">char</span><span class="token operator">*</span> <span class="token function">get_name</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token keyword">const</span> <span class="token punctuation">{</span>
        <span class="token keyword">return</span> name<span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

<span class="token keyword">private</span><span class="token operator">:</span>

    <span class="token keyword">char</span><span class="token operator">*</span> name<span class="token punctuation">;</span>

    <span class="token keyword">void</span> <span class="token function">assign_name</span><span class="token punctuation">(</span><span class="token keyword">const</span> <span class="token keyword">char</span> name<span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>name <span class="token operator">=</span> <span class="token keyword">new</span> <span class="token keyword">char</span><span class="token punctuation">[</span><span class="token function">strlen</span><span class="token punctuation">(</span>name<span class="token punctuation">)</span> <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
        std<span class="token operator">::</span><span class="token function">strncpy</span><span class="token punctuation">(</span><span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>name<span class="token punctuation">,</span> name<span class="token punctuation">,</span> <span class="token function">strlen</span><span class="token punctuation">(</span>name<span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>name<span class="token punctuation">[</span><span class="token function">strlen</span><span class="token punctuation">(</span>name<span class="token punctuation">)</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    MyString string_1<span class="token punctuation">{</span> <span class="token string">"Hello World!"</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
    MyString string_2<span class="token punctuation">{</span> <span class="token string">"Goodbye World!"</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
    MyString string_3<span class="token punctuation">{</span> <span class="token string">"Disney World!"</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>

    <span class="token comment">// The string from string_1 is copied over to string_3, but</span>
    <span class="token comment">// they are independent. Modifications to string_3 are independent</span>
    <span class="token comment">// of that on string_1.</span>
    string_3 <span class="token operator">=</span> string_1<span class="token punctuation">;</span>
    <span class="token comment">// If they were not independent, we would expect the statement</span>
    <span class="token comment">// below to also change string_1.</span>
    string_3<span class="token punctuation">.</span><span class="token function">change_name</span><span class="token punctuation">(</span><span class="token string">"Jurassic World!"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"string_1: "</span> <span class="token operator">&lt;&lt;</span> string_1<span class="token punctuation">.</span><span class="token function">get_name</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"string_2: "</span> <span class="token operator">&lt;&lt;</span> string_2<span class="token punctuation">.</span><span class="token function">get_name</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"string_3: "</span> <span class="token operator">&lt;&lt;</span> string_3<span class="token punctuation">.</span><span class="token function">get_name</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>string_1: Hello World!
string_2: Goodbye World!
string_3: Jurassic World!
</code></pre>
<h5 id="default-copy">Default Copy</h5>
<p>By default, when copying one instance to an other, the members are copied over using either copy construction or copy assignment (depending on  if the instances involved were copied via construction or assignment). It is good practice to be explicit about how your class can be copied, either by specifying copy constructors and copy assignment constructors or by using <code>default</code>, which specifies that copying via the default method is acceptable.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> SomeClass <span class="token punctuation">{</span>
	<span class="token function">SomeClass</span><span class="token punctuation">(</span><span class="token keyword">const</span> SomeClass<span class="token operator">&amp;</span><span class="token punctuation">)</span> <span class="token operator">=</span> <span class="token keyword">default</span><span class="token punctuation">;</span>
	SomeClass<span class="token operator">&amp;</span> <span class="token keyword">operator</span><span class="token operator">=</span><span class="token punctuation">(</span><span class="token keyword">const</span> SomeClass<span class="token operator">&amp;</span><span class="token punctuation">)</span> <span class="token operator">=</span> <span class="token keyword">default</span><span class="token punctuation">;</span>
	<span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
<span class="token punctuation">}</span>
</code></pre>
<h5 id="delete-copy">Delete Copy</h5>
<p>To specify that an instance of a class cannot and should not be copied, use the <code>delete</code> in place of <code>default</code> when specifying copy constructors.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> SomeClass <span class="token punctuation">{</span>
	<span class="token function">SomeClass</span><span class="token punctuation">(</span><span class="token keyword">const</span> SomeClass<span class="token operator">&amp;</span><span class="token punctuation">)</span> <span class="token operator">=</span> <span class="token keyword">delete</span><span class="token punctuation">;</span>
	SomeClass<span class="token operator">&amp;</span> <span class="token keyword">operator</span><span class="token operator">=</span><span class="token punctuation">(</span><span class="token keyword">const</span> SomeClass<span class="token operator">&amp;</span><span class="token punctuation">)</span> <span class="token operator">=</span> <span class="token keyword">delete</span><span class="token punctuation">;</span>
	<span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
<span class="token punctuation">}</span>
</code></pre>
<h5 id="move-constructors-and-move-assignment-operators">Move Constructors and Move Assignment Operators</h5>
<p>Copying can be quite wasteful. Say we encounter a situation where we want to transfer ownership of resources from one object to another. By copying, while one object does acquire the data from the other object, the other object continues to exist, despite no longer being needed. What moving does is transfer the data from the one object to the other before setting the moved from object in a <em>moved-from</em> state. The only two things which can be done with an object in a <em>moved-from</em> state are to reassign them or destruct them (freeing up resources).</p>
<h6 id="rvalues-and-lvalues"><code>rvalues</code> and <code>lvalues</code></h6>
<p><code>rvalues</code> can be thought of as literals or initialized objects that have not been assigned. The reasoning behind the name is that they typically (although not always) reside on the right side of a copy assignment statement.</p>
<p><code>lvalues</code> can be thought of as objects that have been assigned an identifier and are now variables. They typically reside on the left side of a copy assignment statement.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> SomeObject <span class="token punctuation">{</span>
    <span class="token keyword">int</span> some_value<span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">int</span> x <span class="token operator">=</span> <span class="token number">3</span><span class="token punctuation">;</span> <span class="token comment">// x is an lvalue, 3 is an rvalue.</span>
    SomeObject object_A<span class="token punctuation">{</span> <span class="token number">5</span> <span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// object_A is an lvalue, 5 is an rvalue.</span>
    SomeObject object_B <span class="token operator">=</span> SomeObject<span class="token punctuation">{</span> <span class="token number">4</span> <span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// object_B is an lvalue,</span>
                                           <span class="token comment">// SomeObject{ 4 } is an rvalue.</span>
<span class="token punctuation">}</span>
</code></pre>
<h6 id="stdmove-function"><code>std::move</code> Function</h6>
<p>The <code>std::move()</code> function, which can be used after including the <code>&lt;utility&gt;</code> header, is used to convert an <code>lvalue</code> object to an <code>rvalue</code>. This is important because within functions and move constructors, you can specify that that an input be an <code>rvalue</code> object.</p>
<h6 id="move-constructors">Move Constructors</h6>
<p>To specify a <strong>move constructor</strong>, follow the argument data type with <code>&amp;&amp;</code> (versus a <code>const</code> reference like in copy and copy assignment constructors, although the return type should still be a reference). Additionally, include <code>noexcept</code> after argument list (because compilers cannot use exception-throwing move constructors). Within the move constructor, the values of the members of the input should be copied over before the input members are set to null.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">	<span class="token comment">// Move constructor</span>
    <span class="token function">MyString</span><span class="token punctuation">(</span>MyString<span class="token operator">&amp;&amp;</span> other<span class="token punctuation">)</span> <span class="token keyword">noexcept</span> <span class="token punctuation">{</span>
        <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>name <span class="token operator">=</span> other<span class="token punctuation">.</span>name<span class="token punctuation">;</span>
        other<span class="token punctuation">.</span>name <span class="token operator">=</span> <span class="token keyword">nullptr</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
</code></pre>
<h6 id="move-assignment-operator">Move Assignment Operator</h6>
<p>A similar syntax can be followed for the move assignment operator as the copy assignment constructor. Note the self check at the beginning just as in the copy assignment constructor and also note the <code>noexcept</code> after the arguments.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">	<span class="token comment">// Move assignment constructor</span>
    MyString<span class="token operator">&amp;</span> <span class="token keyword">operator</span><span class="token operator">=</span><span class="token punctuation">(</span>MyString<span class="token operator">&amp;&amp;</span> other<span class="token punctuation">)</span> <span class="token keyword">noexcept</span> <span class="token punctuation">{</span>
        <span class="token comment">// Checks if other is actually this instance. If so,</span>
        <span class="token comment">// return this instance.</span>
        <span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token keyword">this</span> <span class="token operator">==</span> <span class="token operator">&amp;</span>other<span class="token punctuation">)</span> <span class="token keyword">return</span> <span class="token operator">*</span><span class="token keyword">this</span><span class="token punctuation">;</span>
        <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>name <span class="token operator">=</span> other<span class="token punctuation">.</span>name<span class="token punctuation">;</span>
        other<span class="token punctuation">.</span>name <span class="token operator">=</span> <span class="token keyword">nullptr</span><span class="token punctuation">;</span>
        <span class="token keyword">return</span> <span class="token operator">*</span><span class="token keyword">this</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
</code></pre>
<h6 id="moving-an-object">Moving an Object</h6>
<p>To move an object after specifying the move constructors, use the <code>std::move()</code> function to convert the object to be moved into an <code>rvalue</code> before inputting that as an argument for initializing or copying to move to another object. This should result in the move constructor or the move assignment constructor being called instead of the copy constructor or copy assignment constructor.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    MyString string_1<span class="token punctuation">{</span> <span class="token string">"Hello World!"</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
    MyString string_2<span class="token punctuation">{</span> <span class="token string">"Goodbye World!"</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
    
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Initial Values:\n"</span><span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"string_1: "</span> <span class="token operator">&lt;&lt;</span> string_1<span class="token punctuation">.</span><span class="token function">get_name</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"string_2: "</span> <span class="token operator">&lt;&lt;</span> string_2<span class="token punctuation">.</span><span class="token function">get_name</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>

    <span class="token comment">// Move from string_1 into string_2. Then delete string_1.</span>
    string_2 <span class="token operator">=</span> std<span class="token operator">::</span><span class="token function">move</span><span class="token punctuation">(</span>string_1<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token keyword">delete</span> <span class="token operator">&amp;</span>string_1<span class="token punctuation">;</span>

    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Final Values:\n"</span><span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"string_1: No longer valid. Error occurs if you attempt to retrieve."</span><span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"string_2: "</span> <span class="token operator">&lt;&lt;</span> string_2<span class="token punctuation">.</span><span class="token function">get_name</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>Initial Values:
string_1: Hello World!
string_2: Goodbye World!
Final Values:
string_1: No longer valid. Error occurs if you attempt to retrieve.
string_2: Hello World!
</code></pre>
<h2 id="control-flow">Control Flow</h2>
<h3 id="if-statements">If Statements</h3>
<p>There are two general ways to write if statements depending on the number of statements to be executed for a given condition. If there is only one statement to be executed, the following format can be used.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">if</span> <span class="token punctuation">(</span>condition<span class="token punctuation">)</span> statement<span class="token punctuation">;</span>
</code></pre>
<p>If multiple statements are to be executed for a given condition, the statements to be executed are contained within a set of curly braces.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">if</span> <span class="token punctuation">(</span>condition<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	statement_1<span class="token punctuation">;</span>
	statement_2<span class="token punctuation">;</span>
	statement_3<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p><code>else if</code> and <code>else</code> statements can be used to evaluate and execute code based on alternate conditions.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">if</span> <span class="token punctuation">(</span>condition_1<span class="token punctuation">)</span> statement_1<span class="token punctuation">;</span>
<span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>condition_2<span class="token punctuation">)</span> statement_2<span class="token punctuation">;</span>
<span class="token keyword">else</span> statement_3<span class="token punctuation">;</span>

<span class="token keyword">if</span> <span class="token punctuation">(</span>condition_1<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	statement_1A<span class="token punctuation">;</span>
	statement_1B<span class="token punctuation">;</span>
<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>condition_2<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	statement_2A<span class="token punctuation">;</span>
	statement_2B<span class="token punctuation">;</span>
<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
	statement_3A<span class="token punctuation">;</span>
	statement_3B<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h3 id="switch-statements">Switch Statements</h3>
<p>Switch statements are used to evaluate if a condition matches a specific case and executes code depending on the case. The format for a <code>switch</code> block is shown below.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">switch</span> <span class="token punctuation">(</span>condition<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">case</span> <span class="token punctuation">(</span>case_a<span class="token punctuation">)</span><span class="token operator">:</span> <span class="token punctuation">{</span>
	<span class="token comment">// This code executes if condition == case_a is true.</span>
	statements_a<span class="token punctuation">;</span>
	<span class="token punctuation">}</span> <span class="token keyword">break</span><span class="token punctuation">;</span>
	<span class="token keyword">case</span> <span class="token punctuation">(</span>case_b<span class="token punctuation">)</span><span class="token operator">:</span> <span class="token punctuation">{</span>
	<span class="token comment">// This code executes if condition == case_b is true.</span>
	statements_b<span class="token punctuation">;</span>
	<span class="token punctuation">}</span> <span class="token keyword">break</span><span class="token punctuation">;</span>
	<span class="token keyword">case</span> <span class="token punctuation">(</span>case_c<span class="token punctuation">)</span><span class="token operator">:</span> <span class="token punctuation">{</span>
	<span class="token comment">// This code executes if condition == case_c is true.</span>
	statements_c<span class="token punctuation">;</span>
	<span class="token punctuation">}</span> <span class="token keyword">break</span><span class="token punctuation">;</span>
	<span class="token keyword">default</span><span class="token operator">:</span> <span class="token punctuation">{</span>
	<span class="token comment">// This code executes if condition does not match any of the above specified</span>
	<span class="token comment">// cases.</span>
	statements_default<span class="token punctuation">;</span>
	<span class="token punctuation">}</span> <span class="token keyword">break</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h3 id="for-loops">For Loops</h3>
<p>A <code>for</code> loop can be used to iterate over every item in a list. The format for a <code>for</code> loop is as follows.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">for</span> <span class="token punctuation">(</span>init<span class="token operator">-</span>statement<span class="token punctuation">;</span> conditional<span class="token punctuation">;</span> iteration<span class="token operator">-</span>statement<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	statements<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>The <code>init-statement</code> is a statement that is executed before the start of the loop. This is usually used to initialize the iterator variable (such as one used to access the elements in a list). <strong>Note: If accessing elements in an array, <code>size_t</code> should be the type of the iterator variable as <code>int</code> may not be able to store large enough values to iterate over a large list.</strong></p>
<p>The <code>conditional</code> is an expression that evaluates before each iteration. If it evaluates to <code>true</code>, then the iteration is executed and the loop continues. Otherwise, the loop is terminated.</p>
<p>The <code>iteration-statement</code> is executed at the end of each iteration and is typically used to increment the iterator variable.</p>
<h4 id="range-based-for-loop">Range-Based For Loop</h4>
<p>The <em>range-based for loop</em> is a way to iterate over all the elements in a list without having to deal with an iterator variable. The format is as follows.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">for</span> <span class="token punctuation">(</span>element_type element_name <span class="token operator">:</span> array_name<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	statements<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>It operates in a similar manner to for loops in Python where the loop will iterate through each element in <code>array_name</code> using <code>element_name</code> to modify or access the value of each element. <code>element_type</code> is simply the type of the elements in the array.</p>
<h3 id="try-catch-blocks">Try-Catch Blocks</h3>
<p>Try-catch blocks are segments of code used to check for errors that occur and handle them appropriately based on the type of error.</p>
<p>Try-catch blocks are made by using the keyword <code>try</code> followed by an enclosed code block, followed by any number of <code>catch</code> cases followed by enclosed code blocks. Notice that when working with exceptions, we are passing them into the catch blocks by reference (hence the <code>&amp;</code> after the variable type <code>std::runtime_error</code> or <code>std::logic_error</code>). A catch case enclosed with <code>...</code> will handle any exception (or any throwable object) not specified by other catch cases.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">try</span> <span class="token punctuation">{</span>
	<span class="token comment">//--some code--</span>
<span class="token punctuation">}</span> <span class="token keyword">catch</span> <span class="token punctuation">(</span><span class="token keyword">const</span> std<span class="token operator">::</span>runtime_error<span class="token operator">&amp;</span> e<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token comment">//--error handling case 1--</span>
<span class="token punctuation">}</span> <span class="token keyword">catch</span> <span class="token punctuation">(</span><span class="token keyword">const</span> std<span class="token operator">::</span>logic_error<span class="token operator">&amp;</span> e<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token comment">//--error handling case 2--</span>
<span class="token punctuation">}</span> <span class="token keyword">catch</span> <span class="token punctuation">(</span><span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token comment">//--error handling case 3--</span>
	<span class="token comment">// If the exception doesn't match either a runtime_error or logic_error,</span>
	<span class="token comment">// then handle the exception (or whatever it is) here.</span>
<span class="token punctuation">}</span>
</code></pre>
<p>To throw an object (typically an error. This is analogous to <code>raise</code> in Python), use the keyword <code>throw</code> followed by the object to be thrown. When throwing exceptions, you can initialize them with a string argument detailing exactly what went wrong. When catching errors, you can call their <code>what()</code> function, which returns that string description detailing the nature of the error.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;stdexcept&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">void</span> <span class="token function">some_function</span><span class="token punctuation">(</span><span class="token keyword">int</span> input<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span>input <span class="token operator">&lt;</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token keyword">throw</span> std<span class="token operator">::</span>logic_error<span class="token punctuation">{</span> <span class="token string">"Input to some_function cannot be"</span> 
	<span class="token string">"negative"</span> <span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// Exceptions can be initialized </span>
	<span class="token keyword">return</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">try</span> <span class="token punctuation">{</span>
		<span class="token function">some_function</span><span class="token punctuation">(</span><span class="token operator">-</span><span class="token number">1</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
		std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Success! We passed -1 into some_function()"</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">catch</span> <span class="token punctuation">(</span>std<span class="token operator">::</span>logic_error<span class="token operator">&amp;</span> err<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Error: "</span> <span class="token operator">&lt;&lt;</span> err<span class="token punctuation">.</span><span class="token function">what</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
</code></pre>
<h4 id="exceptions">Exceptions</h4>
<p><em>Exceptions</em> are used to communicate an error condition. All exceptions are a subclass of class <code>std::exception</code> class. The two main types of exceptions within that are <code>std::runtime_error</code> exceptions and <code>std::logic_error</code> exceptions. To use the standard library exceptions, include the <code>&lt;stdexcept&gt;</code> header.</p>
<p><code>logic_error</code> exceptions are usually caused when a logical precondition of a class or function is not satisfied. <code>logic_error</code> has several subclasses, which are listed below along with their use cases.</p>
<ul>
<li><code>domain_error</code>: Error related to valid input range. For example, this could be thrown when a function receives a negative number when its domain includes all non-negative numbers.</li>
<li><code>invalid_argument</code>: This is a general exception raised when a function receives an unexpected argument.</li>
<li><code>length_error</code>:  This exception is used when some action would violate a maximum size constraint.</li>
<li><code>out_of_range</code>: This exception is used to report that some value is not in some expected range, such as when referencing some index of an array (or other data structure) that does not exist.</li>
</ul>
<p><code>runtime_error</code> exceptions report error conditions outside the program’s scope.</p>
<ul>
<li><code>system_error</code>: This exception reports that the operating system encountered an error. This can be particular useful to catch as details about the nature of the error can be accessed using the <code>.code()</code> method. To use this exception, include the <code>&lt;system_error&gt;</code> header.</li>
<li><code>overflow_error</code>: Arithmetic overflow.</li>
<li><code>underflow_error</code>: Arithmetic underflow.</li>
</ul>
<h4 id="noexcept"><code>noexcept</code></h4>
<p>The keyword <code>noexcept</code> can be specified after a functions argument list before the function’s body. This allows for some optimization but it means you better be sure that it is impossible for the an exception to be thrown within the function.</p>
<h4 id="throwing-in-destructors">Throwing in Destructors</h4>
<p>Not even once.</p>
<h2 id="reference-types">Reference Types</h2>
<h3 id="pointers">Pointers</h3>
<p><strong>Pointers</strong> are variables that store the memory address of other variables.</p>
<p>Pointers are declared by appending an asterisk (<code>*</code>) to a data type following with the identifier for the pointer. The pointer should point to the memory address storing a variable of the specified data type.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span><span class="token operator">*</span> here_is_my_number<span class="token punctuation">;</span> <span class="token comment">// we expect here_is_my_number to point to a memory</span>
                        <span class="token comment">// address containing an int variable.</span>
</code></pre>
<h4 id="address-of-operator">Address-Of-Operator</h4>
<p>To get a variable’s memory address location to store in a pointer, prepend the variable identifier with the <em>address-of-operator</em> (<code>&amp;</code>).</p>
<pre class=" language-cpp"><code class="prism  language-cpp">std<span class="token operator">::</span>string my_house<span class="token punctuation">{</span> <span class="token string">"Welcome to my humble abode"</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
std<span class="token operator">::</span>string<span class="token operator">*</span> my_address <span class="token operator">=</span> <span class="token operator">&amp;</span>my_house<span class="token punctuation">;</span> <span class="token comment">// Pointer to the variable, my_house.</span>
</code></pre>
<h4 id="dereferencing-operator">Dereferencing Operator</h4>
<p>To access a variable from its pointer, prepend a pointer with a <em>dereferencing operator</em> (<code>*</code>).</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    std<span class="token operator">::</span>string my_house<span class="token punctuation">{</span> <span class="token string">"Welcome to my humble abode"</span> <span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// Initialize my_house</span>
    std<span class="token operator">::</span>string<span class="token operator">*</span> my_address <span class="token operator">=</span> <span class="token operator">&amp;</span>my_house<span class="token punctuation">;</span> <span class="token comment">// Get the address of my_house</span>
    cout <span class="token operator">&lt;&lt;</span> my_house <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
    cout <span class="token operator">&lt;&lt;</span> <span class="token string">"My Address: "</span> <span class="token operator">&lt;&lt;</span> my_address <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
    
    my_house <span class="token operator">=</span> <span class="token punctuation">{</span> <span class="token string">"I am now home"</span> <span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// Change the message of my_house</span>
    cout <span class="token operator">&lt;&lt;</span> <span class="token operator">*</span>my_address<span class="token punctuation">;</span> <span class="token comment">// Access my_house via its pointer. This is</span>
	                     <span class="token comment">// functionally the same as using my_house instead.</span>

    <span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>Welcome to my humble abode
My Address: 0x7ffef9569910
I am now home
</code></pre>
<h4 id="member-of-pointer-operator">Member-Of-Pointer Operator</h4>
<p>The <em>member-of-pointer operator</em> (<code>-&gt;</code>) is used to simultaneously access an object through its pointer and then access a member of that object.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	JellyBeanJar my_jar<span class="token punctuation">;</span>
	JellyBeanJar<span class="token operator">*</span> my_jars_location <span class="token operator">=</span> <span class="token operator">&amp;</span>my_jar<span class="token punctuation">;</span>
	<span class="token comment">// my_jar's functions are accessible directly through its pointer using the</span>
	<span class="token comment">// member-of-operator (-&gt;).</span>
	my_jars_location<span class="token operator">-</span><span class="token operator">&gt;</span><span class="token function">add_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"My jar has "</span> <span class="token operator">&lt;&lt;</span> my_jars_location<span class="token operator">-</span><span class="token operator">&gt;</span><span class="token function">count</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> <span class="token string">" beans!"</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h4 id="arrays-and-pointers">Arrays and Pointers</h4>
<p>Creating a pointer to an array is equivalent to creating a pointer to the first value of an array. The identifier for an array without brackets (<code>[]</code>) can be treated as a pointer to the array’s first value.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">int</span> my_numbers<span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">{</span> <span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">1</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
	<span class="token keyword">int</span><span class="token operator">*</span> my_numbers_location <span class="token operator">=</span> my_numbers<span class="token punctuation">;</span>

	<span class="token comment">//my_numbers_location should point to the first value in my_numbers.</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"First value in my_numbers: "</span> <span class="token operator">&lt;&lt;</span> <span class="token operator">*</span>my_numbers_location<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>First value in my_numbers: 5
</code></pre>
<p>Adding and subtracting to the pointer allows us to access the elements ahead or behind of the current value. This is called <em>pointer arithmetic</em>.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">int</span> my_numbers<span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">{</span> <span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">1</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
	<span class="token keyword">int</span><span class="token operator">*</span> my_numbers_location <span class="token operator">=</span> my_numbers<span class="token punctuation">;</span>
	<span class="token keyword">int</span><span class="token operator">*</span> my_second_number <span class="token operator">=</span> my_numbers <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">;</span>

	<span class="token comment">//my_second_number should point to the second value in my_numbers.</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Second value: "</span> <span class="token operator">&lt;&lt;</span> <span class="token operator">*</span>my_second_number<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>Second value: 4
</code></pre>
<p>Using bracket notation to access a value and pointer notation are functionally equivalent.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">int</span> my_numbers<span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">{</span> <span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">1</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>

	<span class="token comment">// From accessing the third value by bracket notation.</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"    my_numbers[2]: "</span> <span class="token operator">&lt;&lt;</span> my_numbers<span class="token punctuation">[</span><span class="token number">2</span><span class="token punctuation">]</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
	<span class="token comment">// From accessing the pointer to the third value and dereferencing.</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"*(my_numbers + 2): "</span> <span class="token operator">&lt;&lt;</span> <span class="token operator">*</span><span class="token punctuation">(</span>my_numbers <span class="token operator">+</span> <span class="token number">2</span><span class="token punctuation">)</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>    my_numbers[2]: 3
*(my_numbers + 2): 3
</code></pre>
<p><code>nullptr</code> is a literal for a pointer in which the pointer does not point to any address. Pointers have an implicit conversion to <code>bool</code> where a <code>nullptr</code> evaluates to <code>false</code> and everything else evaluates to <code>true</code>.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">int</span><span class="token operator">*</span> points_somewhere <span class="token operator">=</span> <span class="token keyword">nullptr</span><span class="token punctuation">;</span>

	<span class="token keyword">if</span> <span class="token punctuation">(</span>points_somewhere<span class="token punctuation">)</span> std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"I have direction!"</span><span class="token punctuation">;</span>
	<span class="token keyword">else</span> std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"I have no direction :("</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>I have no direction :(
</code></pre>
<h3 id="references">References</h3>
<h4 id="passing-arguments-by-value-vs-by-reference">Passing Arguments by Value vs by Reference</h4>
<p>When passing an object into a function by value, the value is essentially copied over and stored as a variable local to the function. This means that any attempts to modify the value using the function will only occur to the local variable and not the variable used as an argument.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">void</span> <span class="token function">add_and_print</span><span class="token punctuation">(</span><span class="token keyword">int</span> value<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	value <span class="token operator">+</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"value is "</span> <span class="token operator">&lt;&lt;</span> value <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">int</span> my_lucky_number <span class="token operator">=</span> <span class="token number">3</span><span class="token punctuation">;</span>
	<span class="token comment">// Pass my_lucky_number into add_and_print. The value of my_lucky_number is</span>
	<span class="token comment">// copied and value is assigned that value. Any changes to value are not </span>
	<span class="token comment">// received by my_lucky_number.</span>
	<span class="token function">add_and_print</span><span class="token punctuation">(</span>my_lucky_number<span class="token punctuation">)</span><span class="token punctuation">;</span>

	<span class="token comment">// We can see that my_lucky_number remains unchanged.</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"my_lucky_number is "</span> <span class="token operator">&lt;&lt;</span> my_lucky_number <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>value is 4
my_lucky_number is 3
</code></pre>
<p>To get around this, if we do want to modify the variable we are passing into the function, we can use pointers. Instead of passing the variable itself, we will pass a pointer to the variable. Within the function, we can dereference the pointer, allowing us to work directly with the variable.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">void</span> <span class="token function">add_and_print</span><span class="token punctuation">(</span><span class="token keyword">int</span><span class="token operator">*</span> value<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token operator">*</span>value <span class="token operator">+</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"value is "</span> <span class="token operator">&lt;&lt;</span> <span class="token operator">*</span>value <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">int</span> my_lucky_number <span class="token operator">=</span> <span class="token number">3</span><span class="token punctuation">;</span>
	<span class="token comment">// Pass the pointer for my_lucky_number into add_and_print. The function  </span>
	<span class="token comment">// then dereferences the pointer and is able to work directly with </span>
	<span class="token comment">// my_lucky_number.</span>
	<span class="token function">add_and_print</span><span class="token punctuation">(</span><span class="token operator">&amp;</span>my_lucky_number<span class="token punctuation">)</span><span class="token punctuation">;</span>

	<span class="token comment">// We can see that my_lucky_number accepts the change.</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"my_lucky_number is "</span> <span class="token operator">&lt;&lt;</span> my_lucky_number <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>value is 4
my_lucky_number is 4
</code></pre>
<p>It can be quite cumbersome to use the dereference operator or member-of-operator on the pointer for every statement involving the variable. Instead, we can use a <strong>reference</strong>.  This is done by appending an ampersand (<code>&amp;</code>) to the parameter type in the function definition. That way, when we pass a variable as an argument to a function, we can work directly with that variable within the function as if it were a local variable, eliminating the need to use the dereferencing operator within the function.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">void</span> <span class="token function">add_and_print</span><span class="token punctuation">(</span><span class="token keyword">int</span><span class="token operator">&amp;</span> value<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	value <span class="token operator">+</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"value is "</span> <span class="token operator">&lt;&lt;</span> value <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">int</span> my_lucky_number <span class="token operator">=</span> <span class="token number">3</span><span class="token punctuation">;</span>
	<span class="token comment">// By passing the variable by reference, add_and_print can work directly to</span>
	<span class="token comment">// modify my_lucky_numbers. Within add_and_print, it is as if we are working</span>
	<span class="token comment">// with a normal, local variable.</span>
	<span class="token function">add_and_print</span><span class="token punctuation">(</span>my_lucky_number<span class="token punctuation">)</span><span class="token punctuation">;</span>

	<span class="token comment">// We can see that my_lucky_number accepts the change.</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"my_lucky_number is "</span> <span class="token operator">&lt;&lt;</span> my_lucky_number <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>value is 4
my_lucky_number is 4
</code></pre>
<h4 id="use-cases">Use Cases</h4>
<p>Pointers and references are largely interchangeable, however, references cannot be assigned to null easily or be reseated, meaning changed such that it references another variable instead of the one originally set.</p>
<h3 id="this-pointers"><code>this</code> Pointers</h3>
<p>The <code>this</code> pointer is used within a class to distinguish the current object when accessing a member. This can be used to make explicit the instance of an object you are referring to (which can be especially useful when an object is interacting with other objects of the same type).</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> DoublyLinkedListObject <span class="token punctuation">{</span>
	DoublyLinkedListObject<span class="token operator">*</span> right_object<span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// Pointer to object on right.</span>
	DoublyLinkedListObject<span class="token operator">*</span> left_object<span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token comment">// Pointer to object on left.</span>
	<span class="token keyword">char</span><span class="token operator">*</span> name<span class="token punctuation">;</span>

	<span class="token function">DoublyLinkedListObject</span><span class="token punctuation">(</span><span class="token keyword">char</span><span class="token operator">*</span> name<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>name <span class="token operator">=</span> name<span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token keyword">void</span> <span class="token function">add_right</span><span class="token punctuation">(</span>DoublyLinkedListObject<span class="token operator">*</span> new_object<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token comment">// Link up this object's right_object to the new_object if it exists.</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>right_object<span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>right_object<span class="token operator">-</span><span class="token operator">&gt;</span>left_object <span class="token operator">=</span> new_object<span class="token punctuation">;</span>
			new_object<span class="token operator">-</span><span class="token operator">&gt;</span>right_object <span class="token operator">=</span> <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>right_object<span class="token punctuation">;</span>
		<span class="token punctuation">}</span>

		<span class="token comment">// Link up this object to new_object</span>
		new_object<span class="token operator">-</span><span class="token operator">&gt;</span>left_object <span class="token operator">=</span> <span class="token keyword">this</span><span class="token punctuation">;</span>
		<span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>right_object <span class="token operator">=</span> new_object<span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token keyword">void</span> <span class="token function">add_left</span><span class="token punctuation">(</span>DoublyLinkedListObject<span class="token operator">*</span> new_object<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token comment">// Link up this object's left_object to the new_object if it exists.</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>left_object<span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>left_object<span class="token operator">-</span><span class="token operator">&gt;</span>right_object <span class="token operator">=</span> new_object<span class="token punctuation">;</span>
			new_object<span class="token operator">-</span><span class="token operator">&gt;</span>left_object <span class="token operator">=</span> <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>left_object<span class="token punctuation">;</span>
		<span class="token punctuation">}</span>

		<span class="token comment">// Link up this object to new_object</span>
		new_object<span class="token operator">-</span><span class="token operator">&gt;</span>right_object <span class="token operator">=</span> <span class="token keyword">this</span><span class="token punctuation">;</span>
		<span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>left_object <span class="token operator">=</span> new_object<span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="const"><code>const</code></h3>
<p>The keyword <code>const</code>, short for “constant”, is used to specify that a particular variable cannot be modified.</p>
<h4 id="constant-methods">Constant Methods</h4>
<p>Using <code>const</code> in a method ensures that the execution of the method will not permit any change to the state of the object from which it is called. You can think of it as a read-only method.</p>
<p>To make a method <code>const</code>, specify include the keyword after the arguments list but before the method body.</p>
<p>Recall the <code>JellyBeanJar</code> class. The <code>count()</code> method, which reads and returns the number of jelly beans present in the jar would be a good method to make read-only.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> JellyBeanJar <span class="token punctuation">{</span>
	<span class="token comment">// If no inputs are specified, the inital jelly bean count is 0.</span>
	<span class="token function">JellyBeanJar</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		jelly_beans <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token comment">// If an input is specified, make sure it is a valid number before</span>
	<span class="token comment">// assigning the initial jelly bean count. If it is invalid, default</span>
	<span class="token comment">// the number of jelly beans to 0.</span>
	<span class="token function">JellyBeanJar</span><span class="token punctuation">(</span><span class="token keyword">int</span> initial_count<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>initial_count <span class="token operator">&gt;=</span> <span class="token number">0</span><span class="token punctuation">)</span> jelly_beans <span class="token operator">=</span> initial_count<span class="token punctuation">;</span>
		<span class="token keyword">else</span> jelly_beans <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token keyword">bool</span> <span class="token function">add_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>jelly_beans <span class="token operator">&lt;</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token keyword">return</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
		jelly_beans <span class="token operator">+</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
		<span class="token keyword">return</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token keyword">bool</span> <span class="token function">remove_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>jelly_beans <span class="token operator">&lt;=</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token keyword">return</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
		jelly_beans <span class="token operator">-</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
		<span class="token keyword">return</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

	<span class="token keyword">int</span> <span class="token function">count</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token keyword">const</span> <span class="token punctuation">{</span>
		<span class="token keyword">return</span> jelly_beans<span class="token punctuation">;</span>
	<span class="token punctuation">}</span>

<span class="token keyword">private</span><span class="token operator">:</span>
	<span class="token keyword">int</span> jelly_beans<span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<h4 id="constant-arguments">Constant Arguments</h4>
<p>The keyword <code>const</code> placed before the data type and identifier for arguments to a function will ensure that that variable remains unmodified throughout the execution of that function. Note that when an object is passed as <code>const</code> into a function, the object can only call <code>const</code> methods within that function.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">some_function</span><span class="token punctuation">(</span><span class="token keyword">const</span> JellyBeanJar<span class="token operator">&amp;</span> jar<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token comment">// Won't compile because jar is const but add_bean() is not const.</span>
	jar<span class="token punctuation">.</span><span class="token function">add_bean</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token keyword">return</span> jar<span class="token punctuation">.</span><span class="token function">count</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h4 id="constant--member-variables">Constant  Member Variables</h4>
<p>Constant variables can’t be modified after initialization. To use <code>const</code> for variables within a class initialized to values specified at construction, we need to use a <em>member initializer list</em>. To create a member initializer list, put a colon (<code>:</code>) after the arguments list for the constructor followed by a comma separated list containing the name of the member to be assigned followed by curly braces containing the argument assigned to the member.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> Student <span class="token punctuation">{</span>
	<span class="token function">Student</span><span class="token punctuation">(</span><span class="token keyword">char</span><span class="token operator">*</span> preferred_name<span class="token punctuation">,</span> <span class="token keyword">const</span> <span class="token keyword">int</span> id_number<span class="token punctuation">,</span> <span class="token keyword">int</span> current_age<span class="token punctuation">)</span>
		<span class="token operator">:</span> name<span class="token punctuation">{</span> preferred_name <span class="token punctuation">}</span><span class="token punctuation">,</span> id<span class="token punctuation">{</span> id_number <span class="token punctuation">}</span><span class="token punctuation">,</span> age<span class="token punctuation">{</span> current_age <span class="token punctuation">}</span> <span class="token punctuation">{</span>
		<span class="token comment">// This is where you could place logic to verify input parameters.</span>
	<span class="token punctuation">}</span> <span class="token comment">// the student's id is a constant as we don't expect this to change with</span>
	  <span class="token comment">// time.</span>

	<span class="token keyword">char</span><span class="token operator">*</span> name<span class="token punctuation">;</span>
	<span class="token keyword">const</span> <span class="token keyword">int</span> id<span class="token punctuation">;</span>
	<span class="token keyword">int</span> age<span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="auto-type-deduction"><code>auto</code> Type Deduction</h3>
<p><code>auto</code> can be used to automatically infer the type of a variable based on context.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">auto</span> number<span class="token punctuation">{</span> <span class="token number">2</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>       <span class="token comment">// number is an int.</span>
<span class="token keyword">auto</span> name<span class="token punctuation">{</span> <span class="token string">"Alfred"</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>  <span class="token comment">// name is a char[6].</span>
</code></pre>
<p>Modifiers such as <code>&amp;</code>, <code>*</code>, and <code>const</code>, when paired with auto, are used to specify if we should expect a variable to be a reference or pointer and whether it should be constant.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">auto</span> year <span class="token punctuation">{</span> <span class="token number">2021</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>             <span class="token comment">// int</span>
<span class="token keyword">auto</span><span class="token operator">&amp;</span> year_ref <span class="token operator">=</span> year<span class="token punctuation">;</span>          <span class="token comment">// int&amp; (reference)</span>
<span class="token keyword">const</span> <span class="token keyword">auto</span><span class="token operator">&amp;</span> year_cref <span class="token operator">=</span> year<span class="token punctuation">;</span>   <span class="token comment">// const int&amp; (constant reference)</span>
<span class="token keyword">auto</span><span class="token operator">*</span> year_ptr <span class="token operator">=</span> <span class="token operator">&amp;</span>year<span class="token punctuation">;</span>         <span class="token comment">// int* (pointer)</span>
<span class="token keyword">const</span> <span class="token keyword">auto</span><span class="token operator">*</span> year_cptr <span class="token operator">=</span> <span class="token operator">&amp;</span>year<span class="token punctuation">;</span>  <span class="token comment">// const int* (constant pointer)</span>
</code></pre>
<p>The main function of <code>auto</code> is to save time during code refactoring such that changing the type of some variable doesn’t require you to change data types everywhere in your code.</p>
<h2 id="object-life-cycle">Object Life Cycle</h2>
<p>Object’s have a life cycle starting from when they are declared (memory is allocated to store the object) and ending when their destructors are called (followed by the object’s storage being deallocated).</p>
<h3 id="automatic-storage">Automatic Storage</h3>
<p>An <em>automatic object</em> is allocated memory at the beginning of an enclosing code block (<code>{}</code>) and deallocated at the end of the enclosing code block.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token punctuation">{</span>
        <span class="token comment">// enclosed_number is only in scope within this enclosed code block.</span>
        <span class="token keyword">int</span> enclosed_number <span class="token operator">=</span> <span class="token number">3</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span> <span class="token comment">// by the end, enclosed_number has been deallocated.</span>

    <span class="token comment">// This won't compile because it's attempting to access a variable that</span>
    <span class="token comment">// no longer exists.</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Enclosed Number: "</span> <span class="token operator">&lt;&lt;</span> enclosed_number<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> <span class="token number">5</span><span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token comment">// i exists only within the for loop.</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> i <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    <span class="token punctuation">}</span> <span class="token comment">// i is deallocated by the time the for loop is completed.</span>

    <span class="token comment">// This won't compile because i no longer exists.</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Last iterator was "</span> <span class="token operator">&lt;&lt;</span> i<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>This is the reason why ordinary variables in functions only exists within the scope of the function.</p>
<h3 id="static-storage">Static Storage</h3>
<p>For a <em>static object</em>, the object is allocated when the program starts and is deallocated when the program ends. Because of this, they can be accessed from any function within the translation unit (consisting of the contents of the source file and all its headers).</p>
<p>Static objects are declared at the same level functions are declared (global scope). You declare one by prepending the variable type with the keyword <code>static</code>.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">static</span> <span class="token keyword">int</span> bean_count <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> <span class="token comment">// bean_count is static and should be accessible</span>
                           <span class="token comment">// throughout the duration of the program.</span>

<span class="token keyword">void</span> <span class="token function">add_beans</span><span class="token punctuation">(</span><span class="token keyword">int</span> new_beans<span class="token punctuation">)</span><span class="token punctuation">{</span>
    <span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> bean <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> bean <span class="token operator">&lt;</span> new_beans<span class="token punctuation">;</span> bean<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token comment">// bean_count can be accessed because it is static.</span>
        bean_count<span class="token operator">++</span><span class="token punctuation">;</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Added "</span> <span class="token operator">&lt;&lt;</span> bean <span class="token operator">+</span> <span class="token number">1</span>
            <span class="token operator">&lt;&lt;</span> <span class="token string">" beans. I now have "</span> <span class="token operator">&lt;&lt;</span> bean_count <span class="token operator">&lt;&lt;</span> <span class="token string">" beans."</span><span class="token punctuation">;</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token comment">// for every function call, bean_count is accessed and modified</span>
    <span class="token comment">// despite not passing a reference to bean_count.</span>
    <span class="token function">add_beans</span><span class="token punctuation">(</span><span class="token number">3</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token function">add_beans</span><span class="token punctuation">(</span><span class="token number">4</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>Added 1 beans. I now have 1 beans.
Added 2 beans. I now have 2 beans.
Added 3 beans. I now have 3 beans.

Added 1 beans. I now have 4 beans.
Added 2 beans. I now have 5 beans.
Added 3 beans. I now have 6 beans.
Added 4 beans. I now have 7 beans.
</code></pre>
<p>If a variable needs to be accessed from another translation unit (from another source file) the keyword <code>extern</code> would be used in place of <code>static</code>. Otherwise, they are functionally identical.</p>
<h4 id="local-static-variables">Local Static Variables</h4>
<p>Static variables declared within a function are only accessible within the context of that function, however, they continue to exists between function calls until they are deallocated at the end of the program. They are allocated at the first function call involving that static variable.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">void</span> <span class="token function">add_beans</span><span class="token punctuation">(</span><span class="token keyword">int</span> new_beans<span class="token punctuation">)</span><span class="token punctuation">{</span>
    <span class="token comment">// bean_count will initialize on the first function call. This statement</span>
    <span class="token comment">// is ignored for subsequent function calls and bean_count won't be reset</span>
    <span class="token comment">// to 0 every time add_beans() is called.</span>
    <span class="token keyword">static</span> <span class="token keyword">int</span> bean_count <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>

    <span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> bean <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> bean <span class="token operator">&lt;</span> new_beans<span class="token punctuation">;</span> bean<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        bean_count<span class="token operator">++</span><span class="token punctuation">;</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Added "</span> <span class="token operator">&lt;&lt;</span> bean <span class="token operator">+</span> <span class="token number">1</span>
            <span class="token operator">&lt;&lt;</span> <span class="token string">" beans. I now have "</span> <span class="token operator">&lt;&lt;</span> bean_count <span class="token operator">&lt;&lt;</span> <span class="token string">" beans."</span><span class="token punctuation">;</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token function">add_beans</span><span class="token punctuation">(</span><span class="token number">3</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token function">add_beans</span><span class="token punctuation">(</span><span class="token number">4</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

    <span class="token comment">// This won't compile because bean_count despite being static and existing</span>
    <span class="token comment">// between function calls is local to add_beans and can only be accessed</span>
    <span class="token comment">// within that function.</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"In total, I now have "</span> <span class="token operator">&lt;&lt;</span> bean_count <span class="token operator">&lt;&lt;</span> <span class="token string">"beans!"</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h4 id="static-members">Static Members</h4>
<p>Static members are not associated with a particular instance of a class but instead with all instances of the class.</p>
<p>Static variables declared in a class definition must be initialized outside at the global scope. Static members are accessed using the scope resolution operator (<code>::</code>).</p>
<p>Static methods can only work with the static variables and other static methods of the class.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> Planet <span class="token punctuation">{</span>
    <span class="token comment">// This static variable is declared here but must be initialized outside the</span>
    <span class="token comment">// class definition.</span>
    <span class="token keyword">static</span> <span class="token keyword">double</span> gravitational_constant<span class="token punctuation">;</span>
    <span class="token keyword">int</span> population<span class="token punctuation">;</span>

    <span class="token comment">// Constructors</span>
    <span class="token function">Planet</span><span class="token punctuation">(</span><span class="token keyword">int</span> population<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token keyword">if</span> <span class="token punctuation">(</span>population <span class="token operator">&gt;=</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>population <span class="token operator">=</span> population<span class="token punctuation">;</span>
        <span class="token punctuation">}</span>
        <span class="token keyword">else</span> <span class="token punctuation">{</span>
            <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>population <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span>
    <span class="token punctuation">}</span>

    <span class="token function">Planet</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>population <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token comment">// This ordinary method is able to work with non-static members of the class.</span>
    <span class="token keyword">bool</span> <span class="token function">change_population</span><span class="token punctuation">(</span><span class="token keyword">int</span> change_in_population<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token keyword">auto</span> new_population <span class="token operator">=</span> <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>population <span class="token operator">+</span> change_in_population<span class="token punctuation">;</span>
        <span class="token keyword">if</span> <span class="token punctuation">(</span>new_population <span class="token operator">&gt;=</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token keyword">this</span><span class="token operator">-</span><span class="token operator">&gt;</span>population <span class="token operator">=</span> new_population<span class="token punctuation">;</span>
            <span class="token keyword">return</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span>
        <span class="token keyword">else</span> <span class="token punctuation">{</span>
            <span class="token keyword">return</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span>
    <span class="token punctuation">}</span>

    <span class="token comment">// This static method can only work with static members of the class.</span>
    <span class="token keyword">static</span> <span class="token keyword">void</span> <span class="token function">change_gravitaitonal_constant</span><span class="token punctuation">(</span><span class="token keyword">double</span> new_gravitational_constant<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        gravitational_constant <span class="token operator">=</span> new_gravitational_constant<span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>

<span class="token comment">// The static variable gravitational_constant is initialized here at the global scale.</span>
<span class="token comment">// The scope resolution operator (::) is used to access and modify the static member.</span>
<span class="token keyword">double</span> Planet<span class="token operator">::</span>gravitational_constant <span class="token operator">=</span> <span class="token number">6.67430e-11</span><span class="token punctuation">;</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    Planet Earth<span class="token punctuation">{</span> <span class="token number">2</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
    <span class="token comment">// Reproduce</span>
    Earth<span class="token punctuation">.</span><span class="token function">change_population</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

    <span class="token comment">// Casually change the laws of the universe. The static method of the Planet class</span>
    <span class="token comment">// must be accessed by using the scope resolution operator (::).</span>
    Planet<span class="token operator">::</span><span class="token function">change_gravitaitonal_constant</span><span class="token punctuation">(</span><span class="token number">6.67430e-10</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h4 id="thread_local"><code>thread_local</code></h4>
<p><code>thread_local</code> is used to specify that a static variable is local to  a specific thread. This is mainly to make code <em>thread-safe</em>, because multiple threads accessing the same mutable global variable is a common source of issues when multithreading.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">void</span> <span class="token function">add_beans</span><span class="token punctuation">(</span><span class="token keyword">int</span> new_beans<span class="token punctuation">)</span><span class="token punctuation">{</span>
	<span class="token comment">// If running this function on multiple threads, each thread will acquire</span>
	<span class="token comment">// its own copy of bean_count.</span>
    <span class="token keyword">thread_local</span> <span class="token keyword">static</span> <span class="token keyword">int</span> bean_count <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>

    <span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> bean <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> bean <span class="token operator">&lt;</span> new_beans<span class="token punctuation">;</span> bean<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        bean_count<span class="token operator">++</span><span class="token punctuation">;</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Added "</span> <span class="token operator">&lt;&lt;</span> bean <span class="token operator">+</span> <span class="token number">1</span>
            <span class="token operator">&lt;&lt;</span> <span class="token string">" beans. I now have "</span> <span class="token operator">&lt;&lt;</span> bean_count <span class="token operator">&lt;&lt;</span> <span class="token string">" beans."</span><span class="token punctuation">;</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h3 id="dynamic-storage">Dynamic Storage</h3>
<p><em>Dynamic objects</em> are objects that you have manual control over when their lives begin and end.</p>
<p>To create a dynamic object, use the keyword <code>new</code> followed by the variable type, optionally followed by a curly brace with initialization arguments. This will return a pointer to the object which you can store to access the variable.</p>
<p>To destroy a dynamic object, use the keyword <code>delete</code> followed by the pointer pointing to the dynamic object.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">int</span><span class="token operator">*</span> secret_number <span class="token operator">=</span> <span class="token keyword">new</span> <span class="token keyword">int</span><span class="token punctuation">{</span> <span class="token number">12345124</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"The secret number is "</span> <span class="token operator">&lt;&lt;</span> <span class="token operator">*</span><span class="token punctuation">(</span>secret_number<span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token keyword">delete</span> secret_number<span class="token punctuation">;</span>

	<span class="token comment">// Results in an error because the dynamic object has already been destroyed.</span>
	std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"I recovered the secret numgber: "</span> <span class="token operator">&lt;&lt;</span> <span class="token operator">*</span><span class="token punctuation">(</span>secret_number<span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>The secret number is 12345124
C:\Users\Brand\source\repos\object lifecycle\Debug\object lifecycle.exe (process 20728) exited with code -1073741819.
</code></pre>
<h4 id="dynamic-arrays">Dynamic Arrays</h4>
<p>Creating a dynamic array is very similar to creating a dynamic object. Simply insert brackets following the object type specifying the number of elements.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">	<span class="token keyword">int</span> n <span class="token operator">=</span> <span class="token number">8</span><span class="token punctuation">;</span>
	<span class="token comment">// You can specify the length of a dynamic array using a variable.</span>
	<span class="token keyword">int</span><span class="token operator">*</span> secret_numbers <span class="token operator">=</span> <span class="token keyword">new</span> <span class="token keyword">int</span><span class="token punctuation">[</span>n<span class="token punctuation">]</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<p>When deleting a dynamic array, be sure to include brackets <code>[]</code> after the keyword <code>delete</code>.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">	<span class="token comment">// delete should include brackets when deleting dynamic arrays.</span>
	<span class="token keyword">delete</span><span class="token punctuation">[</span><span class="token punctuation">]</span> secret_numbers<span class="token punctuation">;</span>
</code></pre>
<h4 id="memory-leaks">Memory Leaks</h4>
<p>It’s important to delete dynamic variables sometime after creating them before the end of your program. Failure to do so could result in memory leaks where memory is not released, even after the conclusion of your program.</p>
<h2 id="runtime-polymorphism">Runtime Polymorphism</h2>
<p><strong>Interfaces</strong> can be thought of as contracts between classes that implement the interfaces and <em>consumers</em>, or classes that use the class implementing the interface. The consumers know what members are accessible of classes that implement the interfaces. Classes that implement the interface know what members must be implemented.</p>
<h3 id="virtual-methods">Virtual Methods</h3>
<p>Virtual methods are methods that are able to be overwritten by derived classes. A virtual method is declared by adding the keyword <code>virtual</code> to a method’s definition.</p>
<p>To overwrite the method in a derived class, use the keyword <code>override</code> after the function identifier and parentheses but before the function body.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> ParentClass <span class="token punctuation">{</span>
    <span class="token keyword">virtual</span> <span class="token keyword">void</span> <span class="token function">say</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"This function is in the ParentClass."</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token keyword">void</span> <span class="token function">gene</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"This is present in both parent and child."</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>

<span class="token keyword">struct</span> ChildClass <span class="token operator">:</span> ParentClass <span class="token punctuation">{</span>
    <span class="token keyword">void</span> <span class="token function">say</span><span class="token punctuation">(</span><span class="token punctuation">)</span> override <span class="token punctuation">{</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"This function is from the ChildClass overriding the ParentClass"</span> 
        <span class="token string">"function."</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    ParentClass <span class="token class-name">parent</span><span class="token punctuation">;</span>
    ChildClass <span class="token class-name">child</span><span class="token punctuation">;</span>

    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"ParentClass Function Results:\nsay(): "</span><span class="token punctuation">;</span>
    parent<span class="token punctuation">.</span><span class="token function">say</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"gene(): "</span><span class="token punctuation">;</span>
    parent<span class="token punctuation">.</span><span class="token function">gene</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>

    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"ChildClass Function Results:\nsay(): "</span><span class="token punctuation">;</span>
    child<span class="token punctuation">.</span><span class="token function">say</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"gene(): "</span><span class="token punctuation">;</span>
    child<span class="token punctuation">.</span><span class="token function">gene</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>ParentClass Function Results:
say(): This function is in the ParentClass.
gene(): This is present in both parent and child.

ChildClass Function Results:
say(): This function is from the ChildClass overriding the ParentClass function.
gene(): This is present in both parent and child.
</code></pre>
<h3 id="pure-virtual-classes">Pure-Virtual Classes</h3>
<p>A <em>pure-virtual method</em> specified such that it must be override in its derived classes. They are established by omitting a function body and appending the method header with <code>= 0;</code>.</p>
<p>A <em>pure-virtual class</em> is a class that consists of only pure-virtual methods. These are the bases of interfaces as they make clear what members should be implemented for classes implementing the interface and what members should be used by consumers.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token comment">// BasePerson is a pure-virtual class and serves as an interface.</span>
<span class="token keyword">struct</span> BasePerson <span class="token punctuation">{</span>
    <span class="token keyword">virtual</span> <span class="token keyword">void</span> <span class="token function">say_the_thing</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>

<span class="token comment">// These are the classes that implement the interface.</span>
<span class="token keyword">struct</span> Unggoy <span class="token operator">:</span> BasePerson <span class="token punctuation">{</span>
    <span class="token keyword">void</span> <span class="token function">say_the_thing</span><span class="token punctuation">(</span><span class="token punctuation">)</span> override <span class="token punctuation">{</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"I see  bad guy!"</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>

<span class="token keyword">struct</span> Sangheili <span class="token operator">:</span> BasePerson <span class="token punctuation">{</span>
    <span class="token keyword">void</span> <span class="token function">say_the_thing</span><span class="token punctuation">(</span><span class="token punctuation">)</span> override <span class="token punctuation">{</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"WORT, WORT, WORT!"</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>

<span class="token keyword">struct</span> Jiralhanae <span class="token operator">:</span> BasePerson <span class="token punctuation">{</span>
    <span class="token keyword">void</span> <span class="token function">say_the_thing</span><span class="token punctuation">(</span><span class="token punctuation">)</span> override <span class="token punctuation">{</span>
        std<span class="token operator">::</span>cout <span class="token operator">&lt;&lt;</span> <span class="token string">"I will sniff you out, Demon!"</span> <span class="token operator">&lt;&lt;</span> std<span class="token operator">::</span>endl<span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>

<span class="token comment">// This is the consumer.</span>
<span class="token keyword">struct</span> CharactersList <span class="token punctuation">{</span>
    <span class="token keyword">void</span> <span class="token function">add_character</span><span class="token punctuation">(</span>BasePerson<span class="token operator">&amp;</span> character<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token keyword">auto</span> new_characters_list <span class="token operator">=</span> <span class="token keyword">new</span> BasePerson<span class="token operator">*</span><span class="token punctuation">[</span>number_of_characters <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
        <span class="token keyword">for</span> <span class="token punctuation">(</span>size_t i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> number_of_characters<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            <span class="token comment">// Copy over existing characters into new character list.</span>
            new_characters_list<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">=</span> characters<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span>
        <span class="token comment">// Add address of new character into new character list.</span>
        new_characters_list<span class="token punctuation">[</span>number_of_characters<span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token operator">&amp;</span>character<span class="token punctuation">;</span>
        <span class="token keyword">if</span> <span class="token punctuation">(</span>characters<span class="token punctuation">)</span> <span class="token keyword">delete</span> characters<span class="token punctuation">;</span> <span class="token comment">// Delete old character list if it exists.</span>
        characters <span class="token operator">=</span> new_characters_list<span class="token punctuation">;</span>
        number_of_characters<span class="token operator">++</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token keyword">void</span> <span class="token function">everyone_say_the_thing</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token keyword">for</span> <span class="token punctuation">(</span>size_t i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> number_of_characters<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
            characters<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token function">say_the_thing</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span>
    <span class="token punctuation">}</span>

<span class="token keyword">private</span><span class="token operator">:</span>
    BasePerson<span class="token operator">*</span><span class="token operator">*</span> characters<span class="token punctuation">{</span> <span class="token keyword">nullptr</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
    size_t number_of_characters<span class="token punctuation">{</span> <span class="token number">0</span> <span class="token punctuation">}</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    Unggoy grunt<span class="token punctuation">;</span>
    Sangheili elite<span class="token punctuation">;</span>
    Jiralhanae brute<span class="token punctuation">;</span>

    CharactersList Halo<span class="token punctuation">;</span>

    Halo<span class="token punctuation">.</span><span class="token function">add_character</span><span class="token punctuation">(</span>grunt<span class="token punctuation">)</span><span class="token punctuation">;</span>
    Halo<span class="token punctuation">.</span><span class="token function">add_character</span><span class="token punctuation">(</span>elite<span class="token punctuation">)</span><span class="token punctuation">;</span>
    Halo<span class="token punctuation">.</span><span class="token function">add_character</span><span class="token punctuation">(</span>brute<span class="token punctuation">)</span><span class="token punctuation">;</span>
    Halo<span class="token punctuation">.</span><span class="token function">everyone_say_the_thing</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<pre><code>I see  bad guy!
WORT, WORT, WORT!
I will sniff you out, Demon!
</code></pre>
<h4 id="virtual-destructors">Virtual Destructors</h4>
<p>If dynamically implementing classes implementing an interface, it’s a good idea to specify a default destructor in the interface to prevent from leaking resources.</p>
<pre class=" language-cpp"><code class="prism  language-cpp">BaseClass <span class="token punctuation">{</span>
	<span class="token keyword">virtual</span> <span class="token operator">~</span><span class="token function">BaseClass</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=</span> <span class="token keyword">default</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="implementing-interfaces">Implementing Interfaces</h3>
<p>When implementing a class where a field is an instance of a class using the interface, there are two ways to <em>inject</em> the member: <strong>constructor injection</strong> or <strong>property injection</strong>.</p>
<p>In constructor injection, the member is initialized as a reference to the class implementing the interface. Remember that references cannot be reseated. If you need the class being implemented to be reseated, use property injection instead.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> MyCharacter <span class="token punctuation">{</span>
    <span class="token function">MyCharacter</span><span class="token punctuation">(</span>BasePerson<span class="token operator">&amp;</span> character<span class="token punctuation">)</span> <span class="token operator">:</span> my_character<span class="token punctuation">{</span> character <span class="token punctuation">}</span> <span class="token punctuation">{</span><span class="token punctuation">}</span>
<span class="token keyword">private</span><span class="token operator">:</span>
    BasePerson<span class="token operator">&amp;</span> my_character<span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<p>In property injection, the member is initialized as a pointer to the class implementing the interface. A setter function can be used to reseat the member.</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">struct</span> MyCharacter <span class="token punctuation">{</span>
	<span class="token function">MyCharacter</span><span class="token punctuation">(</span>BasePerson<span class="token operator">*</span> character_ptr<span class="token punctuation">)</span> <span class="token operator">:</span> my_character_ptr<span class="token punctuation">{</span> character_ptr <span class="token punctuation">}</span> <span class="token punctuation">{</span><span class="token punctuation">}</span>
	<span class="token keyword">void</span> <span class="token function">set_character</span><span class="token punctuation">(</span>BasePerson<span class="token operator">*</span> new_character_ptr<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		my_character_ptr <span class="token operator">=</span> new_character_ptr<span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
<span class="token keyword">private</span><span class="token operator">:</span>
	BasePerson<span class="token operator">*</span> my_character_ptr<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>

