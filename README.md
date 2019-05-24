# Guup
Guup (pronounced "goop") is a programming language where everything is an object!

## Why is Guup?
I created Guup as a simple idea for a summer project, but then I decided that I actually wanted to do something with it. I had a brilliant idea.

What if a program was an object?

Suddenly I could see everything layed out before me, and I was happy with myself. I knew what I wanted Guup to be. Guup was to be an object oriented programming language where everything is an object. 

It is heavily inspired by programming languages like Lisp, Python, and Java. 

## Syntax
The Guup syntax is not super complex, but it has several main parts to it. First, is the idea that a Guup program is also a Guup variable.

### Programs

```
pro hello = {
  println("Hello, World!");
};

fun _main = int () {
  %hello;

  return 0;
};
```

The above Guup code can be executed, and the output is very simple.

```
Hello, World!
```

Essentially, you can store a code block as a variable and call it as a way to run code. This is effectively a way to store a simple program within a program.

### Functions
Also, a `prog` is not a function. 

```
fun add = int (int a, int b) {
  return $a + $b;
}

fun _main = int () {
  %(%(1,2)add)println;

  returb 0;
};
```

It's output

```
3
```

The above code is also pretty simple, and it outlines the function structure. One important thing to remember is that a `func` *is* a `prog`. Earlier I said that programs are objects. What is happening is that a function is like a `prog` with command line arguments. In the example case, it assigns the variables `a` and `b` to `1` and `2` before letting the function run. These are local variables, so they don't get assigned to the global context.

Another thing you can do with a function is to add default arguments.

```
fun sayHello = nul (str name<"World">) {
  %("Hello, ":$name:"!")println
}

fun _main = int () {
  %()sayHello;

  return 0;
}

### Other data types.
The rest of the code is actually pretty simple. You have the standard data types, such as integers, doubles, floats, chars, strings, arrays, etc., defined as follows.

```
int bin1 = b0#100101;       // 37 in binary
int hex1 = x0#25;           // 37 in hexadecimal
int oct1 = o0#45;           // 37 in octal
int num1 = 1;               // integer
dub num2 = 2.5;             // double
flo num3 = 3.2f;            // float
chr letter1 = 'a';          // character initialized via character
chr letter2 = 97;           // character initialized via integer
chr letter3 = x0#67;        // character initialized via hexadecimal int
str txt1 = "hello";         // string initalized via standard string syntax
str txt2 =
  chr['h' 'e' 'l' 'l' 'o']; // string initialize via character array.
```

Now for the list definitions.

```
int[] numArr = int[1 2 3 4 5 6];
```

The list syntax is simple. There are no commas for lists. Only space separation.

### Referencing
Referencing variables is pretty easy.

```
fun _main = int () {
  int a = 22;
  %($a)println;
  
  return 0;
}
```

You just use the `$` character followed by the name of the variable.

As you might've seen, you can execute a `fun`ction or a `pro`gram by using the `%` selector. You can also reference them by using the `$` selector.

```
pro oopsie = {
  %('oops')println;
};

fun doWhatThing = nul (pro thatThing) {
  %thatThing;
};

fun _main = int () {
  %($oopsie)doWhatThing;

  return 0;
};
```