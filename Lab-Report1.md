![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/8ed003ca-83f5-4b66-a5f5-4e48d4efa12e)
No arguments in the directory meant the terminal will take the directory back to the root directory.
Applying `cd` with a path to a directory directs the terminal to a folder that the user lists, not an error. 
Using `cd` with a path to a file will result in an error since the command only changes directories and thus a file cannot be a working directory.
When the command was run, the working directory for the first line was ~/lecture1. The second was ~.
The third was ~/lecture1. If we were to input "`cd` lecture1" in the working directory ~/lecture1, we would get an error.

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/e799fddd-888f-4877-8ad8-ed4c868d72b3)
Using no arguments in the command will always tell us what files or folders there are in the current directory. 
In this case, the first line uses the root directory as its working directory and lists the lecture1 folder. The third line still uses
the root directory as its working directory but instead lists the contents within lecture1 after adding a path as an argument.
The sixth line uses ~/lecture1/messages as its working directory and when used without any arguments will result in the first case where
it lists everything in the current directory. However, using `ls` on a text file results in printing the file name, no errors.
The command with a path to a directory lists the files and folders located in the mentioned directory, no errors.

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/337b2f31-8a63-453d-8455-949c9eb28617)
![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/e158f280-6359-48bc-ba7d-0b4422316801)
![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/1f45c2fb-583b-4028-8c1e-b5df9ee11265)
Using `cat` with no args results in the terminal outputting the user's inputs: when the user types in anything on the console and hit "enter," it outputs the same response the user put in, no errors.
In the first screenshot I typed "salw" and it returned "salw."
Using `cat` with a directory outputs the terminal that the directory is a directory which is an error.
Using `cat` with a file reads the file contents and outputs them, no errors.
All of the `cat` working directories used in the screenshots were the root directory.
