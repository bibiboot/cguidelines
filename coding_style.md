https://www.kernel.org/doc/Documentation/CodingStyle

	switch (suffix) {
	case 'G':
	case 'g':
		mem <<= 30;
		break;
	case 'M':
	case 'm':
		mem <<= 20;
		break;
	case 'K':
	case 'k':
		mem <<= 10;
		/* fall through */
	default:
		break;
	}

	if (x is true) {
		we do y
	}

	int function(int x)
	{
		body of function
	}

	if (x == y) {
		..
	} else if (x > y) {
		...
	} else {
		....
	}

Do not unnecessarily use braces where a single statement will do.

if (condition)
	action();

and

if (condition)
	do_this();
else
	do_that();

This does not apply if only one branch of a conditional statement is a single
statement; in the latter case use braces in both branches:

if (condition) {
	do_this();
	do_that();
} else {
	otherwise();
}

Do not add spaces around (inside) parenthesized expressions.  This example is
*bad*:

	s = sizeof( struct file );

When declaring pointer data or a function that returns a pointer type, the
preferred use of '*' is adjacent to the data name or function name and not
adjacent to the type name.  Examples:

	char *linux_banner;
	unsigned long long memparse(char *ptr, char **retptr);
	char *match_strdup(substring_t *s);

Use one space around (on each side of) most binary and ternary operators,
such as any of these:

	=  +  -  <  >  *  /  %  |  &  ^  <=  >=  ==  !=  ?  :

		Chapter 4: Naming

C is a Spartan language, and so should your naming be.  Unlike Modula-2
and Pascal programmers, C programmers do not use cute names like
ThisVariableIsATemporaryCounter.  A C programmer would call that
variable "tmp", which is much easier to write, and not the least more
difficult to understand.

HOWEVER, while mixed-case names are frowned upon, descriptive names for
global variables are a must.  To call a global function "foo" is a
shooting offense.

GLOBAL variables (to be used only if you _really_ need them) need to
have descriptive names, as do global functions.  If you have a function
that counts the number of active users, you should call that
"count_active_users()" or similar, you should _not_ call it "cntusr()".

Encoding the type of a function into the name (so-called Hungarian
notation) is brain damaged - the compiler knows the types anyway and can
check those, and it only confuses the programmer.  No wonder MicroSoft
makes buggy programs.

LOCAL variable names should be short, and to the point.  If you have
some random integer loop counter, it should probably be called "i".
Calling it "loop_counter" is non-productive, if there is no chance of it
being mis-understood.  Similarly, "tmp" can be just about any type of
variable that is used to hold a temporary value.

If you are afraid to mix up your local variable names, you have another
problem, which is called the function-growth-hormone-imbalance syndrome.
See chapter 6 (Functions).


