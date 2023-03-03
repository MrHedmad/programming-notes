# General programming concepts

In this lesson, we will go over the main concepts in computer science that you
need to effectively know what you're doing while programming.

We will cover:
- What is a computer;
- How does a computer work (from a very general point of view);
- What a program is;
- What a programming language is;

## A computer is a what?
You're almost certainly reading this on a computer screen, so you kind of know
what a computer is. However, you might not know the various bits and pieces that
make a computer do its thing.

A generic computer is composed of the following:
- A power source (e.g. a battery or the power outlet);
- A motherboard, a generally large board that physically holds all of the other
  components on it, connecting them as well as providing key functionality
  when the computer has to boot up.
- Some sticks of Random Access Memory, or RAM, which can hold data while the
  computer is turned on and running, and get wiped as soon as the computer turns
  off;
- A Central Processing Unit, or CPU, which is a chip that can perform a few
  basic operations, like reading some data from the RAM, writing to it,
  or adding/subtracting values from the data that it is reading.

  A CPU has inside of it the so-called *registries*, which are specialized
  RAM-like data storage containers where the CPU can actually act on (i.e. 
  before say, adding two numbers together, they have to be first copied from
  the RAM to the registry, then added, then copied back to the RAM).

  Modern CPUs can execute a massive number of these operations every second.
  So high, in fact, that we routinely use GIGA-Hertz (measuring the number of 
  things per second) to measure them. For example, a modern CPU easily runs at
  a frequency of 4.5 GHz.

Optionally, but very commonly, you find other components:
- A Graphical Processing Unit, or GPU. A GPU is similar to a CPU in the fact 
  that it can run computations, but its architecture is better suited to the
  kinds of computations needed to display graphics (i.e. it's a CPU but better
  at rendering images). There are some computations, other than graphical ones,
  that can run better on a GPU than a CPU, so it could happen that you might
  want to use a GPU to run your program instead of the CPU.
- Hard drives, which are permanent storage for data. These allow you to not lose
  everything when the computer turns off. Modern hard drives use Solid State
  Drives (SSDs) instead of the older Hard Disks (which are actual disks that
  have to spin), which are faster and less prone to breaking.

  Even more recently, in 2012, Non-Volatile Memory express (NVMe) drives came about, offering even faster performance.
- Many other bits and pieces, like chips for internet access, bluetooth, etc...

Other than the physical computer, you need a way to read and send commands to
the machine itself, so a computer is often outfitted with *peripherals*, like:
- A screen, to display output;
- A keyboard, to accept input in the form of text;
- A mouse, to navigate interfaces;
- Speakers, to play sounds.

It feels stupid to say, but keep in mind that a computer can run perfectly fine
without peripherals. Servers and supercomputers, for example, are not commonly
outfitted with screens, but are accessed, in many cases, through the internet 
from another PC.

## Computers go beep
Now we know what each part of the computer is, but we still have no clue of what
they do. I find that the boot process of the computer is a good way to cover
all the major "moving parts" of the computer.

How does a computer start up? You push the power button, then:
- The motherboard starts up. It is hard-wired to supply power to its components.
  Most motherboards run a series of tests as they start to check that every 
  component is correctly working, and are not faulty.
- The ram turns on, and is ready to accept data from the CPU.
- The CPU gets power, and starts up. It is hard-wired to do just a single thing:
  read whatever is is a very specific chip, the Basic Input/Output System 
  (BIOS).
- The BIOS contains a program, also usually referred to as the BIOS, that in
  turn looks for another program in one of the computer hard-drives, usually
  called the *bootloader*. When it finds it, it starts it, then stops.
  Most modern computers now use UEFI/BIOS, instead of the "old" BIOS, to start.
  Just so you know that if you read UEFI somewhere, you have to think of the 
  BIOS.
- The bootloader takes over. The bootloader does many things, like finding the
  various hard-drives and getting them ready for further access, but it mainly
  does one thing. It looks around for a program called the *kernel*, and starts
  it.
- The kernel is the "mother program" in a computer. When it starts, it has the
  task of accessing and making every physical component of the computer work,
  like GPUs, keyboards, internet chips, and the like. When it finishes setting
  everything up, it usually looks for a program that it can start to give 
  human users access to the computer.

At this point we can say that the computer has started successfully. The kernel
stays on and "hosts" the other programs that have to run on the computer.
Any other program has to "ask" the kernel to run operations on the CPU, to get
memory to use, etc.. Imagine the kernel as the layer between the actual hardware
and every other program.

Using the kernel directly was a very hard task. For this reason, we invented a
program called the *shell* to access in a more "user-friendly" way the kernel
and, in turn, use the computer. Shells are still used today, and we will cover
them in a later lesson.
Shells are purely keyboard-based: you write a *command*, the computer executes
it, and then it *returns* the output of that command.

As computers tried to be more and more user-friendly, shells were generally
dropped in favour of Graphical User Interfaces, which are the desktops and 
windowed programs that we use every day.

## Programs and programming languages

A *program* is a set of instructions that the computer follows to end up to
achieve some goal set out by the programmer.

As we said, the CPU can only perform a few basic operations. A question that you
could have is how to combine these operations to obtain more complex behavior,
like displaying this page on your screen. 
The very first programs were on punching cards (paper cards where you had to
literally punch holes in in order to "write" data), and interfaced with the
CPU directly in the language of bits (zeroes and ones). A very tedious exercise.

This is where programs and programming languages come in. Early computer
scientists invented assembly, a more human-like language (e.g. with actual 
letters) that could easily be converted to the bits that the CPU could run with
by another program, the *assembler*.

Each different CPU has a different set of instructions, and they are run in a
different way, so you would need different assembly languages and assemblers.
Assembly, in any case, was the first programming language.

With "programming language" we main a set of rules (a *grammar*) that can be
followed to write a text file (literally!) containing instructions that another
program can read and eventually have executed by the CPU.
Examples of programming languages include C, C++, Go, Rust, Python, R, Haskell, 
and many many more. They are all, in essence, programs that can be used to write
other programs without having to directly write CPU instructions.

Modern, complex programs would not exist without programming languages.

### Types of programming languages
We can split programming languages (PLs) in different categories. First of all,
a language can be "high level" or "low level". Assembly is an example of a 
low-level PL. "Low" as in "really similar to CPU instructions". In the modern
conception of low and high PLs, "low" has come to mean "similar to assembly",
since it is unthinkable to write code directly for the CPU.
High-level PLs are instead closer to human speech, and are generally easier to
write.

The general trade-off between high and low PLs is that high languages get rid
of complexity by generally offering less performance and a reduced ability to
manage the fine details of the program.
Python, a high-level language, is around 100x slower than C, a low-level
language, when performing some tasks. However, Python is much easier to learn
and write than C.
High-level programs are also usually faster to actually write. If the 100x
speed-up is no real problem (which, generally, it is not), taking ten times less
time to actually write the program might be worth the run-time speed penalty.

Examples of high-level PLs include Python, R and Julia. Examples of
low-level PLs include C/C++, Rust, Go, and Java.

Another characteristic we can use to divide PLs is if their "converter program"
(e.g. the assembler) is a compiler or an interpreter.
A compiler takes the program text file as a whole and processes it to generate
a new file that can be immediately run. This has the advantage that the
compiler can inspect the code and apply optimizations to it, making the 
resulting executable file more efficient. Compilers also "condense" the whole
program (which, when written out, may span multiple files) into just a single,
portable executable.
A compiler has to produce a compiled executable that can run on just one
particular type of CPU, however. Modern CPUs fall into three or four main
types (or architectures, with just two dominating the vast majority of
computer), so this is not really a problem in practice.
Compilers can also take a very long time to compile programs. The Rust compiler,
at the time of writing, is notoriously very slow (but produces very fast 
executable programs).

Interpreted languages, on the other hand, require no compilation. The compiler
is replaced by the *interpreter*. Interpreters dynamically run the program by
sequentially reading the program's files and immediately executing the
instructions. In practice, then, if you want to run an interpreted program you
need to have the interpreter for that language installed in your system.
In general, higher level languages are interpreted.

Interpretation makes you lose the chance of optimizing your code, and therefore
makes the run-time of the program generally slower than compiled languages.
The main benefit of interpreted languages is that you can run your program
interactively as you are writing it, or run it manually one line at a time to
inspect it or find bugs. It is therefore great if you want to, for instance,
run an analysis and you want to try out different approaches in real-time.

Usually listed as an advantage, but to my opinion a disadvantage, interpreted
languages need the user to have the interpreter installed on their system.
This is generally a "problem" for interpreted languages, especially in
scientific computation. But it is not a discussion that we will have right now.

Examples of compiled languages include C/C++, Rust, and Go. Example of
interpreted languages include Python and Rust. Julia is one of the rare examples
of a language that supports both compilation and interpretation.
