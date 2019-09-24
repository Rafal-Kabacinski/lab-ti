# 01 - Hello World

## Classroom scripts guide

Each subject discussed during Information Engineering Laboratory classes will be accompanied by a tutorial/script like the one below. Sometimes the tutor will guide you threw the script, sometimes you will be encouraged to read it by yourself and perform parts of the exercise by your own.

In course of the scripts you will encounter blocks marked as:

---

#### :hammer: :fire: Assignment :fire: :hammer:

---

These are the tasks that you will have to perform during classes. You can always ask the tutor for help or explanation of the assignment. Bare in mind that the teacher can modify the assignments, omit, or add an additional one - so **PAY ATTENTION**.

Most of the class scripts will finish with:

## Final assignments :fire: :hammer:

These are the tasks that you will be performing after finishing tutor-guided script. If you do not finish all assignments during the class remember to complete them at home!

Sometimes a homework will be included in the script, marked as:

## Homework :boom: :house:

**HOMEWORK SOMETIMES CAN BE GRADED!**, also your teacher can assign you with additional homework apart from the one included in script.

## Used Tools

During this classed a **Qt Creator** IDE will be our main tool for writing and compiling our programs ([https://www.qt.io/](https://www.qt.io/)). All the tools needed are already installed on laboratory computers. If you wish to install the same set of tools on your home computer see tutorial: [00 - Installing Qt Creator at your home computer](./00%20-%20Installing%20Qt%20Creator%20at%20your%20home%20computer.html).

Additional external tool for code editing and preview, with syntax highlighting can come in handy, choose one you like the most. Recommendations:

- **Visual Studio Code** (Windows, Linux, OS X) - [https://code.visualstudio.com/](https://code.visualstudio.com/)
- Atom (Windows, Linux, OS X) - [https://atom.io/](https://atom.io/)
- Notepad++ (Windows) - [https://notepad-plus-plus.org/](https://notepad-plus-plus.org/)
- Programmer's Notepad (Windows) - [https://www.pnotepad.org/](https://www.pnotepad.org/)
- gedit (Linux) - [https://wiki.gnome.org/Apps/Gedit](https://wiki.gnome.org/Apps/Gedit)
- BBEdit (OS X) - [https://www.barebones.com/products/bbedit/](https://www.barebones.com/products/bbedit/)

## Crating new Qt Creator C++ project

---

#### :hammer: :fire: Assignment :fire: :hammer:

Create a new Qt Creator C++ project using the instruction below

---

Open Qt Creator, select **Welcome**(1) tab, than **Projects**(2) and **New Project**(3). You can also select **File** &rarr; **New File or Project...**

![1_new_project](../images/01/1_new_project.png)

In *New Project* popup select **Non-Qt Project**(1), than **Plain C++ Application**(2) and **Choose**(3):

![2_select_project](../images/01/2_select_project.png)

Next we have to name the project(1) - *hello_world* in this case. You can also change the destination folder. **CAUTION**: In project names and localization do **NOT** use special signs (like polish letters) and additional spaces (use underscore if needed). Select **Next**(2).

![3_project_name](../images/01/3_project_name.png)

Now you have to select a Build System - it is a set of tool that will be responsible for preparing a project for each compilation process. While working with Qt it is the easiest to use **qmake**. Make sure it is selected(1), and click **Next**(2).

![4_build_system](../images/01/4_build_system.png)

**Next wizard window can differ on different machines**. In this step you will be choosing a set of compiler and debugger tools that will be used in created project. During our classes we will be using **MinGW 64-bit**. Make sure that this, and only this one, kit is selected by ticking the box left to the kit name(1). At home also use *MinGW 64-bit* in order to avoid incompatibilities. Click **Next**(2).

![5_kit_selection](../images/01/5_kit_selection.png)

On the last step just hit **Finish**.

![6_version_control](../images/01/6_version_control.png)

## First Program - Hello World!

Qt Creator will always create a *Hello World* program:

```cpp
#include <iostream>

using namespace std;

int main()
{
    cout << "Hello World!" << endl;
    return 0;
}
```

Entry function `int main()` is usually placed in *main.cpp* file - see a project tree. 

In order to build the program select a hammer icon ![7_build](../images/01/7_build.png) or hit a keyboard combination: *Ctrl+B*. If a compilation process is a success you will see a green progress bar in right corner to fill completely:

![8_build_finished](../images/01/8_build_finished.png)

To run the program click the play button: ![9_run](../images/01/9_run.png) or hit a keyboard combination: *Ctrl+R*. A comment window displaying "Hello World!" should pop up.

---

#### :hammer: :fire: Assignment :fire: :hammer:

Build and run the "Hello World!" program.

---

## Commenting code

C++ offers two types of comment styles:

- one-line comments:

```c++
// can be used to temporarily deactivate a line of code
// cout << "Hello World!" << endl;

// or can be used to add a line description
cout << "Hello World!" << endl; // prints "Hello World!" and a new line
```

- multi-line comments:

```c++
/*  
used primarely  
for longer comments
*/

/* can also be used to deactivate a block of code
    cout << "Hello World!" << endl;
    return 0;
*/
```

**ATTENTION** Comment your code! It will help you to understand what each line means. It is always easier to understand commented code on return after few days!

---

#### :hammer: :fire: Assignment :fire: :hammer:

Try inserting one-line and multi-line comments into the code. Deactivate line `cout << "Hello World!" << endl;` using both types of comment, re-build the program and run. What is the result?

Add one-line comments describing selected lines.

Add multi-line comment:

```cpp
/*
The main function is
a starting point of application
*/
```

above `int main()` line.

---

## Code errors handling

In order for program to work a syntax of the written code have to be strict with a guidelines of particular programming language. While writing a code Qt Creator will highlight potential errors in our code. Eg. in C++ each instruction have to be ended with `;`. After deleting the semicolon, after few seconds, editor will highlight this line red and suggest potential mistake:

![10_semicolon_error](../images/01/10_semicolon_error.png)

---

#### :hammer: :fire: Assignment :fire: :hammer:

Imitate various code errors, read the error comment suggested by Qt Creator, fix it back and try another one:

- delete `;` (semicolon) from any line in the code
- delete `}` (curly bracket) from the last line of the code
- modify `int` to `inta` from line `int main()`
- add `foo = 1;` in line below `cout << "Hello World!" << endl;`

---

If one tries to build the program containing errors Qt Creator will not compile it. *Issues* tab will be opened with a list of potential errors. You can double click any of the raised errors for editor to jump to a faulty line. Try compiling the code containing errors.

![11_issues](../images/01/11_issues.png)

**ATTENTION** It is very important to read the errors! Most of the mistakes in code can be easily fixed by reading the error message and applying the suggested solution.

## Final assignments :fire: :hammer:

#### 1. Easy code manipulation

- Try changing the code in a way that it displays more than one "Hello World!" message:

> Hello World!  
> Hello World!  
> Hello World!  
> Hello World!

- Modify the displayed text:

> My name is AAA BBB  
> I am from CCC  
> I am YYY years old  
> My hobby is ZZZ

- Modify the code so each line is separated by additional line:

> Hello World!  
>  
> Hello World!  
>  
> Hello World!  
>  
> Hello World!

#### 2. Install Qt Creator at your home computer

---

Authors: *Tomasz Mańkowski*
