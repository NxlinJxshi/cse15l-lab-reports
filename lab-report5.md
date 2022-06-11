# Week 10 Lab report 5

## How you found the tests with different results (Did you use diff on the results of running a bash for loop? Did you search through manually? Did you use some other programmatic idea?)
- I used diff
- Then selected which difference to use

## Test 1: Test file 495
#### Ouput of the given implementation of the test file 
```

[foo(and(bar))]

```

#### My program output:

```

[foo(and(bar]

```

#### Expected Output:

```

[foo(and(bar))]

```


#### Describe which implementation is correct, or if you think neither is correct, by showing both actual outputs and indicating what the expected output is.
- The provided matches the expected outcome. My output is incorrect. The last line of the implementation needs to be edited. 
```

int nextOpenBracket = markdown.indexOf("[", currentIndex),
    nextCloseBracket = markdown.indexOf("]", currentIndex),
    openParen = markdown.indexOf("(", nextCloseBracket),
    closeParen = markdown.indexOf(")", openParen);      //Following line caused the error
    

```


- To fix my code I will add a stack program, to find the matching brackets/parenthesis.

## Test 1: Test file 12
#### Ouput of provided implementation
```

[]

```

#### Output of my program

```

[\]

```

#### Expected Output

```

[]

```


#### Describe which implementation is correct, or if you think neither is correct, by showing both actual outputs and indicating what the expected output is.
- The provided implementation is correct as it matches the expected output. My output is incorrect. the following line needs to be corrected 

```

int openParen = link.indexOf("(");
if(link.subsstring(openParen, link.length() -1).contains(" "){
  link = link.substring(0,link.indexOf(" ", openParen));
}
int closeParen = link.lastIndexOf(")");

```

- In order for my code to generate the correct ouctome, I will have my program check for paarenthesis after the close brackets 
