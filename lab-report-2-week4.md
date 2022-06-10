# Test 1

## Below is a code change that fixed the initial bug in the code

<img width="1189" alt="Screen Shot 2022-06-09 at 8 44 25 PM" src="https://user-images.githubusercontent.com/103763994/172986592-e33ea459-406a-4910-a2b7-68edc9f3c771.png">

[Link to test file]https://github.com/NxlinJxshi/markdown-parser/commit/2ca31954a39da4ec65a7e148e8f4892eb02aa3a2





## Test 2

The second failure-inducing input causes an bug on strings without parentheses. 
When there is no parentheses in the text file, the program assigns the parentheses to an index value of -1, 
which is out of bounds for the string's length. The symptom of this is a StringIndexOutOfBoundsException.

<img width="954" alt="Screen Shot 2022-06-09 at 9 08 46 PM" src="https://user-images.githubusercontent.com/103763994/172988676-a772f254-cc87-47a2-ac95-e291b8420de4.png">

Test file 2 contains the test case without the parentheses:
https://github.com/NxlinJxshi/markdown-parser/blob/2ca31954a39da4ec65a7e148e8f4892eb02aa3a2/test-file2.md

Heres the block of code that I added to remove the error:
<img width="937" alt="Screen Shot 2022-06-09 at 9 17 15 PM" src="https://user-images.githubusercontent.com/103763994/172990962-64f4f493-a92a-4abb-a1c4-eee0eafec345.png">




