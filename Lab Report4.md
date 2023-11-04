# Part 1: We are analyzing reverseInPlace from the ArrayExamples class
Successful Test
```
@Test
public void testReversedInPlaceSuccess() {
  int[] input = {1, 2, 3};
  ArrayExamples.reverseInPlace(input);
  assertArrayEquals(new int[] {3,2,1}, input);
}
```

Failed Test
```
@Test
public void testReversedInPlaceFailure() {
  int[] input = {2, 3, 4, 5, 6, 7};
  ArrayExamples.reverseInPlace(input);
  assertArrayEquals(new int[] {7,6,5,4,3,2}, input);
}
```
Symptom output in JUnit
![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/bb8f75b9-7345-423f-b089-0114717d85ff)

The Bug change before:
```
  static void reverseInPlace(int[] arr) {
    int temp;
    for(int i = 0; i < arr.length/2; i += 1) {
      temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length-1] = temp;
    }
  }
```
After:
```
  static void reverseInPlace(int[] arr) {
    int temp;
    for(int i = 0; i < arr.length/2; i += 1) {
      temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length-1 - i] = temp; //arr index is also subtracted with i to match the index range
    }
  }
```
The change made to the code is that we subtracted i in the index of arr[arr.length-1] in order to match the corresponding range
of the element that we want to switch with arr[i]. Since the method uses a for loop that splits the list in half, the reflected element
is the array size subtracted by the index. This should give us the correct output in order to reverse the elements.

---
# Part 2 using grep:
Examples cited from man7.org [Link](https://man7.org/linux/man-pages/man1/grep.1.html)
According to man7, we can use -v to invert the matching of patterns; meaning that grep will print patterns that do not use the matching pattern.
For instance, applying this to the file find-results.txt which contains text files within technical/biomed, if we were to avoid any text files containing 14,
we get:
```
batma@BLD MINGW64 /g/docsearch
$ grep -v "14*" find-results.txt
technical/biomed
technical/biomed/ar297.txt
technical/biomed/ar309.txt
technical/biomed/ar328.txt
technical/biomed/ar383.txt
technical/biomed/ar387.txt
technical/biomed/ar407.txt
technical/biomed/ar408.txt
technical/biomed/ar409.txt
technical/biomed/ar422.txt
technical/biomed/ar429.txt
technical/biomed/ar430.txt
technical/biomed/ar624.txt
technical/biomed/ar68.txt
technical/biomed/ar745.txt
technical/biomed/ar750.txt
technical/biomed/ar774.txt
technical/biomed/ar778.txt
technical/biomed/ar79.txt
technical/biomed/ar792.txt
technical/biomed/ar795.txt
technical/biomed/ar799.txt
technical/biomed/ar93.txt
technical/biomed/bcr273.txt
technical/biomed/bcr284.txt
technical/biomed/bcr285.txt
technical/biomed/bcr294.txt
technical/biomed/bcr303.txt
technical/biomed/bcr45.txt
technical/biomed/bcr458.txt
technical/biomed/bcr567.txt
technical/biomed/bcr568.txt
technical/biomed/bcr570.txt
technical/biomed/bcr583.txt
technical/biomed/bcr588.txt
technical/biomed/bcr602.txt
technical/biomed/bcr605.txt
technical/biomed/bcr607.txt
technical/biomed/bcr620.txt
technical/biomed/bcr635.txt
technical/biomed/cc2358.txt
technical/biomed/cc3.txt
technical/biomed/cc300.txt
technical/biomed/cc303.txt
technical/biomed/cc343.txt
technical/biomed/cc350.txt
technical/biomed/cc367.txt
technical/biomed/cc4.txt
technical/biomed/cc973.txt
technical/biomed/cvm-2-6-278.txt
technical/biomed/cvm-2-6-286.txt
technical/biomed/gb-2002-3-2-research0008.txt
technical/biomed/gb-2002-3-2-research0009.txt
technical/biomed/gb-2002-3-5-research0020.txt
technical/biomed/gb-2002-3-5-research0022.txt
technical/biomed/gb-2002-3-5-research0023.txt
technical/biomed/gb-2002-3-5-research0024.txt
technical/biomed/gb-2002-3-5-research0025.txt
technical/biomed/gb-2002-3-6-research0029.txt
technical/biomed/gb-2002-3-7-research0032.txt
technical/biomed/gb-2002-3-7-research0035.txt
technical/biomed/gb-2002-3-7-research0036.txt
technical/biomed/gb-2002-3-7-research0037.txt
technical/biomed/gb-2002-3-8-research0038.txt
technical/biomed/gb-2002-3-8-research0039.txt
technical/biomed/gb-2002-3-8-research0040.txt
technical/biomed/gb-2002-3-9-research0043.txt
technical/biomed/gb-2002-3-9-research0044.txt
technical/biomed/gb-2002-3-9-research0045.txt
technical/biomed/gb-2002-3-9-research0046.txt
technical/biomed/gb-2002-3-9-research0048.txt
technical/biomed/gb-2002-3-9-research0049.txt
technical/biomed/gb-2003-4-2-r8.txt
technical/biomed/gb-2003-4-2-r9.txt
technical/biomed/gb-2003-4-3-r20.txt
technical/biomed/gb-2003-4-4-r24.txt
technical/biomed/gb-2003-4-4-r26.txt
technical/biomed/gb-2003-4-4-r28.txt
technical/biomed/gb-2003-4-5-r30.txt
technical/biomed/gb-2003-4-5-r32.txt
technical/biomed/gb-2003-4-5-r34.txt
technical/biomed/gb-2003-4-6-r37.txt
technical/biomed/gb-2003-4-6-r39.txt
technical/biomed/gb-2003-4-7-r42.txt
technical/biomed/gb-2003-4-7-r43.txt
technical/biomed/gb-2003-4-7-r46.txt
technical/biomed/gb-2003-4-8-r50.txt
technical/biomed/gb-2003-4-9-r57.txt
technical/biomed/gb-2003-4-9-r58.txt
technical/biomed/gb-2003-4-9-r60.txt
technical/biomed/rr37.txt
technical/biomed/rr73.txt
technical/biomed/rr74.txt
```
This shows that we can use this to avoid certain terms or lines that we don't want to have.
When using it on a directory, we are instead told that the pattern is a directory:
```
batma@BLD MINGW64 /g/docsearch/technical
$ grep -v "911report" biomed
grep: biomed: Is a directory
```
We could use this to recursively search for directories that do not contain a certain pattern.

---
Another option we can use is -F (Case Sensitive) which views the patterns as a fixed set of patterns.
In the same text file, if we use this command to find a set of strings such as "2105" we get:
```
batma@BLD MINGW64 /g/docsearch
$ grep -F "2105" find-results.txt
technical/biomed/1471-2105-1-1.txt
technical/biomed/1471-2105-2-1.txt
technical/biomed/1471-2105-2-8.txt
technical/biomed/1471-2105-2-9.txt
technical/biomed/1471-2105-3-12.txt
technical/biomed/1471-2105-3-14.txt
technical/biomed/1471-2105-3-16.txt
technical/biomed/1471-2105-3-17.txt
technical/biomed/1471-2105-3-18.txt
technical/biomed/1471-2105-3-2.txt
technical/biomed/1471-2105-3-22.txt
technical/biomed/1471-2105-3-23.txt
technical/biomed/1471-2105-3-24.txt
technical/biomed/1471-2105-3-26.txt
technical/biomed/1471-2105-3-28.txt
technical/biomed/1471-2105-3-3.txt
technical/biomed/1471-2105-3-30.txt
technical/biomed/1471-2105-3-34.txt
technical/biomed/1471-2105-3-37.txt
technical/biomed/1471-2105-3-38.txt
technical/biomed/1471-2105-3-4.txt
technical/biomed/1471-2105-3-6.txt
technical/biomed/1471-2105-4-13.txt
technical/biomed/1471-2105-4-24.txt
technical/biomed/1471-2105-4-25.txt
technical/biomed/1471-2105-4-26.txt
technical/biomed/1471-2105-4-27.txt
technical/biomed/1471-2105-4-28.txt
technical/biomed/1471-2105-4-31.txt
```
This is useful for if you want to exclusively search for a certain string in a file or make a count of how much of the same term is used.
When used on a directory, we get:
```
batma@BLD MINGW64 /g/docsearch/technical
$ grep -F "biomed" *
grep: 911report: Is a directory
grep: biomed: Is a directory
grep: government: Is a directory
grep: plos: Is a directory
```
Which doesn't appear to function correctly, but I assume that if we were to have a directory containing a large amount of other directories, we can use this to tell
if the directory we want is located here.

---
We can also use --color for grep which outputs the lines containing the patttern while also highlighting the mentioned pattern in a different color.
On a file, we get:
```
batma@BLD MINGW64 /g/docsearch
$ grep --color "rr" find-results.txt
technical/biomed/rr166.txt
technical/biomed/rr167.txt
technical/biomed/rr171.txt
technical/biomed/rr172.txt
technical/biomed/rr191.txt
technical/biomed/rr196.txt
technical/biomed/rr37.txt
technical/biomed/rr73.txt
technical/biomed/rr74.txt
```
![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/4d048267-45e4-4e13-b7f5-9d363f97d9f6)
This is useful for if we want to find where the patterns are located but the line is too large to locate where the pattern is located exactly.
Doing it on a directory just outputs that the directory input is a directory:
```
batma@BLD MINGW64 /g/docsearch
$ grep --color "tech" technical
grep: technical: Is a directory
```
Though I assume that we can use --color on a directory that contains a long name so that we can locate where the pattern is located in the directory name.
Another command that we can use is -c which counts the lines that contain the matching pattern and outputs them in the terminal.
When used on a text file, we get
```
batma@BLD MINGW64 /g/docsearch
$ grep -c "2003" find-results.txt
27
```
This is useful for finding how many lines in the code contain that pattern.
When used on a directory, we get:
```
batma@BLD MINGW64 /g/docsearch
$ grep -c "t*" technical
grep: technical: Is a directory
0
```
Since directories do not contain lines, -c displays 0 even if we make a pattern. There is no clear use of using -c on directories
other than doing a recursive search for a directory containing other directories that contain the same pattern in the directory names.

