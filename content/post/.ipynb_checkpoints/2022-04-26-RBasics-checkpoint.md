---
title: "Very Basic Coding"
author: ''
date: '2019-04-25'
output:
  html_document:
    highlight: textmate
    theme: simplex
    toc: yes
  pdf_document:
    toc: yes
categories:
- data analysi
- data manipulation
tags:
- conditions
- control structures
slug: Very Basic Coding
jupyter:
  jupytext:
    formats: ipynb,md,Rmd
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.13.7
  kernelspec:
    display_name: R
    language: R
    name: ir
---

<!-- #region toc=true -->
<h1>Table of Contents<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#Types-of-Operators" data-toc-modified-id="Types-of-Operators-1">Types of Operators</a></span><ul class="toc-item"><li><span><a href="#Logical-AND-(&amp;&amp;)-and-Logical-OR-(||)" data-toc-modified-id="Logical-AND-(&amp;&amp;)-and-Logical-OR-(||)-1.1">Logical AND (<code>&amp;&amp;</code>) and Logical OR (<code>||</code>)</a></span></li><li><span><a href="#%in%-Operator" data-toc-modified-id="%in%-Operator-1.2"><code>%in%</code> Operator</a></span></li></ul></li><li><span><a href="#Control-Structures-or-Conditional-Statements" data-toc-modified-id="Control-Structures-or-Conditional-Statements-2">Control Structures or Conditional Statements</a></span><ul class="toc-item"><li><ul class="toc-item"><li><span><a href="#If-Condition" data-toc-modified-id="If-Condition-2.0.1">If Condition</a></span></li><li><span><a href="#If..Else" data-toc-modified-id="If..Else-2.0.2">If..Else</a></span></li><li><span><a href="#If...Else...If" data-toc-modified-id="If...Else...If-2.0.3">If...Else...If</a></span></li></ul></li><li><span><a href="#For-and-While" data-toc-modified-id="For-and-While-2.1">For and While</a></span><ul class="toc-item"><li><span><a href="#For-Loop" data-toc-modified-id="For-Loop-2.1.1">For Loop</a></span></li><li><span><a href="#While-Loop" data-toc-modified-id="While-Loop-2.1.2">While Loop</a></span></li></ul></li><li><span><a href="#repeat,-break,-next-and-switch" data-toc-modified-id="repeat,-break,-next-and-switch-2.2">repeat, break, next and switch</a></span><ul class="toc-item"><li><span><a href="#Repeat-statement" data-toc-modified-id="Repeat-statement-2.2.1">Repeat statement</a></span></li><li><span><a href="#Break-Statement" data-toc-modified-id="Break-Statement-2.2.2">Break Statement</a></span></li><li><span><a href="#Next-Statment" data-toc-modified-id="Next-Statment-2.2.3">Next Statment</a></span></li><li><span><a href="#Switch-Statment" data-toc-modified-id="Switch-Statment-2.2.4">Switch Statment</a></span></li></ul></li></ul></li><li><span><a href="#Vectorization-and-recycling-concepts" data-toc-modified-id="Vectorization-and-recycling-concepts-3">Vectorization and recycling concepts</a></span></li></ul></div>
<!-- #endregion -->

<!-- #raw -->
---
title: "RBasics"
author: ''
date: '2022-04-26'
output:
  html_document:
    highlight: textmate
    theme: simplex
    toc: yes
  pdf_document:
    toc: yes
categories:
- data manipulations
- data visualizations
tags:
- dplyr
- ggplot2
slug: RBasics
---
<!-- #endraw -->

```R
install.packages(c("formatR", "jsonlite"), repos="http://cran.rstudio.com")

```

<h1>Table of Contents<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#Types-of-Operators" data-toc-modified-id="Types-of-Operators-1">Types of Operators</a></span><ul class="toc-item"><li><span><a href="#Logical-AND-(&amp;&amp;)-and-Logical-OR-(||)" data-toc-modified-id="Logical-AND-(&amp;&amp;)-and-Logical-OR-(||)-1.1">Logical AND (<code>&amp;&amp;</code>) and Logical OR (<code>||</code>)</a></span></li><li><span><a href="#%in%-Operator" data-toc-modified-id="%in%-Operator-1.2"><code>%in%</code> Operator</a></span></li></ul></li><li><span><a href="#Control-Structures-or-Conditional-Statements" data-toc-modified-id="Control-Structures-or-Conditional-Statements-2">Control Structures or Conditional Statements</a></span><ul class="toc-item"><li><ul class="toc-item"><li><span><a href="#If-Condition" data-toc-modified-id="If-Condition-2.0.1">If Condition</a></span></li><li><span><a href="#If..Else" data-toc-modified-id="If..Else-2.0.2">If..Else</a></span></li><li><span><a href="#If...Else...If" data-toc-modified-id="If...Else...If-2.0.3">If...Else...If</a></span></li></ul></li><li><span><a href="#For-and-While" data-toc-modified-id="For-and-While-2.1">For and While</a></span><ul class="toc-item"><li><span><a href="#For-Loop" data-toc-modified-id="For-Loop-2.1.1">For Loop</a></span></li><li><span><a href="#While-Loop" data-toc-modified-id="While-Loop-2.1.2">While Loop</a></span></li></ul></li><li><span><a href="#repeat,-break,-next-and-switch" data-toc-modified-id="repeat,-break,-next-and-switch-2.2">repeat, break, next and switch</a></span><ul class="toc-item"><li><span><a href="#Repeat-statement" data-toc-modified-id="Repeat-statement-2.2.1">Repeat statement</a></span></li><li><span><a href="#Break-Statement" data-toc-modified-id="Break-Statement-2.2.2">Break Statement</a></span></li><li><span><a href="#Next-Statment" data-toc-modified-id="Next-Statment-2.2.3">Next Statment</a></span></li><li><span><a href="#Switch-Statment" data-toc-modified-id="Switch-Statment-2.2.4">Switch Statment</a></span></li></ul></li></ul></li><li><span><a href="#Vectorization-and-recycling-concepts" data-toc-modified-id="Vectorization-and-recycling-concepts-3">Vectorization and recycling concepts</a></span></li></ul></div>

# Types of Operators

Arithmetic Operators  `(+  -  *  /  %%` (modulo)  `%/%`(integer divide) ` ^`(raised to the power of))  
Relational Operators`(>  <  <=  >=  ==  !=  )`         
Logical Operators   `(&  |  !  &&  ||)`  
Assignment Operators `(<−  =  <<−  ->  ->>)`  
Miscellaneous Operators `(:  %in%  %*%)`
Arithmetic Operators

Operator    Description       Example
-           Subtraction       5 - 1 = 4
+           Addition          5 + 1 = 6
*           Multiplication    5 * 3 = 15
/           Division          10 / 2 = 5
^ or **     Exponentiation    2*2*2*2*2 as 2 to the power of 5
x%%y        Modulus           5%%2 is 1
x%/%y       Integer Division  5%/%2 is 2Relational and Logical Operators

Operator     Description                 Example
<            less than                   5 < 10
<=           less than or equal to       <= 5
>            greater than                10 > 5
>=           greater than or equal to    >= 10
==           exactly equal to            == 10
!=           not equal to                != 5
!x           not x                       x <- c(5), !x
x | y        x or y                      x <- c(5), y <- c(10), x | y
x & y        x and y                     x <- c(5), y <- c(10), x & y
isTRUE(x)    tests whether x is true     x <- TRUE, isTRUE(x)
                                                    [1] FALSE
## Logical AND (`&&`) and Logical OR (`||`)


```R
# Called Logical AND operator. Takes first element of both the vectors and gives the TRUE only if both are TRUE.
v <- c(3,0,TRUE,2+2i)
t <- c(1,3,TRUE,2+3i)
print(v&&t)
```

    [1] TRUE
    


```R
# Called Logical OR operator. Takes first element of both the vectors and gives the TRUE if one of them is TRUE.
v <- c(0,0,TRUE,2+2i)
t <- c(0,3,TRUE,2+3i)
print(v||t)
```

    [1] FALSE


## `%in%` Operator


```R
# This operator is used to identify if an element belongs to a vector.

v1 <- 8
v2 <- 12
t <- 1:10
print(v1 %in% t) 
print(v2 %in% t)
```

    [1] TRUE
    [1] FALSE


# Control Structures or Conditional Statements

(decision making statements)

![Imgur](https://i.imgur.com/YQfqXlY.png?1)

### If Condition
**IF statement associates a condition with a sequence of statements, The sequence of statements is executed only if the condition is true. If the condition is false or null, the IF statement does nothing. In either case, control passes to the next statement**


```R
num1=10
num2=20
 
if(num1<=num2){
print("Num1 is less or equal to Num2")
    }
```

    [1] "Num1 is less or equal to Num2"


### If..Else


```R
x <- 1:15
if (sample(x, 1) <= 10) {
    print("x is less than 10")
} else {
    print("x is greater than 10")
}
```

    [1] "x is less than 10"


**Another way in R**


```R
x <- 1:15
ifelse(x <= 10, "x less than 10", "x greater than 10")
```


<ol class=list-inline>
	<li>'x less than 10'</li>
	<li>'x less than 10'</li>
	<li>'x less than 10'</li>
	<li>'x less than 10'</li>
	<li>'x less than 10'</li>
	<li>'x less than 10'</li>
	<li>'x less than 10'</li>
	<li>'x less than 10'</li>
	<li>'x less than 10'</li>
	<li>'x less than 10'</li>
	<li>'x greater than 10'</li>
	<li>'x greater than 10'</li>
	<li>'x greater than 10'</li>
	<li>'x greater than 10'</li>
	<li>'x greater than 10'</li>
</ol>



### If...Else...If


```R
if (10==10)
    print('10 is equal to 10') else
    print('invalid')
```

    [1] "10 is equal to 10"
    


```R
x <- 3
y <- if(x>2){0}else{1}
y
```


0



```R
z <- 1:10
ifelse(z<2 | z>8, 1, 0)
```


<ol class=list-inline>
	<li>1</li>
	<li>0</li>
	<li>0</li>
	<li>0</li>
	<li>0</li>
	<li>0</li>
	<li>0</li>
	<li>0</li>
	<li>1</li>
	<li>1</li>
</ol>




```R
ifelse(z>5,'TRUE','FALSE')
```


<ol class=list-inline>
	<li>'FALSE'</li>
	<li>'FALSE'</li>
	<li>'FALSE'</li>
	<li>'FALSE'</li>
	<li>'FALSE'</li>
	<li>'TRUE'</li>
	<li>'TRUE'</li>
	<li>'TRUE'</li>
	<li>'TRUE'</li>
	<li>'TRUE'</li>
</ol>




```R
z <- 1:10
ifelse(z>4&z>8,"x","?")
```


<ol class=list-inline>
	<li>'?'</li>
	<li>'?'</li>
	<li>'?'</li>
	<li>'?'</li>
	<li>'?'</li>
	<li>'?'</li>
	<li>'?'</li>
	<li>'?'</li>
	<li>'x'</li>
	<li>'x'</li>
</ol>




```R
x <- c("what","is","truth")

if("Truth" %in% x) {
   print("Truth is found the first time")
} else if ("truth" %in% x) {
   print("truth is found the second time")
} else {
   print("No truth found")
}
```

    [1] "truth is found the second time"


## For and While

### For Loop
To repeats a statement or group of for a fixed number of times.


```R
vector <- c("aaa","bbb","ccc")
 for(i in vector){   
   print(i)   
}    
```

    [1] "aaa"
    [1] "bbb"
    [1] "ccc"
    


```R
for (year in c(2010,2011,2012,2013,2014,2015)){
  print(paste("The year is", year))
}
```

    [1] "The year is 2010"
    [1] "The year is 2011"
    [1] "The year is 2012"
    [1] "The year is 2013"
    [1] "The year is 2014"
    [1] "The year is 2015"
    


```R
for(i in 2:5){
    z <- i +1
    print(z)
}
```

    [1] 3
    [1] 4
    [1] 5
    [1] 6


| Instead of  | Use          |
|-------------|--------------|
| 1:length(x) | seq_along(x) |
| 1:n         | seq_len(n)   |


```R
x <- c('a', 'b', 'c', 'd')
for (i in seq_along(x)){
    print(x[i])
}

#alternatively
for (words in x){
    print(words)
}
```

    [1] "a"
    [1] "b"
    [1] "c"
    [1] "d"
    [1] "a"
    [1] "b"
    [1] "c"
    [1] "d"
    


```R
mymat <- matrix(1:9,3,3)
mymat

for (i in seq_len(nrow(mymat))){
    for (j in seq_len(ncol(mymat))){
        print(mymat[i,j])
    }
}
```


<table>
<tbody>
	<tr><td>1</td><td>4</td><td>7</td></tr>
	<tr><td>2</td><td>5</td><td>8</td></tr>
	<tr><td>3</td><td>6</td><td>9</td></tr>
</tbody>
</table>



    [1] 1
    [1] 4
    [1] 7
    [1] 2
    [1] 5
    [1] 8
    [1] 3
    [1] 6
    [1] 9
    


```R
x <- head(women,10)
x
mrnull <- NULL
for(i in seq_along(x[,1])){
    concat <- c(mrnull, mean(as.numeric(x[i, 1:2])))
    print(concat)
}

```


<table>
<thead><tr><th scope=col>height</th><th scope=col>weight</th></tr></thead>
<tbody>
	<tr><td>58 </td><td>115</td></tr>
	<tr><td>59 </td><td>117</td></tr>
	<tr><td>60 </td><td>120</td></tr>
	<tr><td>61 </td><td>123</td></tr>
	<tr><td>62 </td><td>126</td></tr>
	<tr><td>63 </td><td>129</td></tr>
	<tr><td>64 </td><td>132</td></tr>
	<tr><td>65 </td><td>135</td></tr>
	<tr><td>66 </td><td>139</td></tr>
	<tr><td>67 </td><td>142</td></tr>
</tbody>
</table>



    [1] 86.5
    [1] 88
    [1] 90
    [1] 92
    [1] 94
    [1] 96
    [1] 98
    [1] 100
    [1] 102.5
    [1] 104.5
    


```R
# Create your three-dimensional array
my_array <- array(1:20, dim=c(20, 20, 20))

for (i in 1:dim(my_array)[1]) {
  for (j in 1:dim(my_array)[2]) {
    for (k in 1:dim(my_array)[3]) {
      my_array[i,j,k] = i*j*k
    }
  }
}

# Show a 10x10x15 chunk of your array
print(my_array[1:10, 1:10, 1:15])
```

    , , 1
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]    1    2    3    4    5    6    7    8    9    10
     [2,]    2    4    6    8   10   12   14   16   18    20
     [3,]    3    6    9   12   15   18   21   24   27    30
     [4,]    4    8   12   16   20   24   28   32   36    40
     [5,]    5   10   15   20   25   30   35   40   45    50
     [6,]    6   12   18   24   30   36   42   48   54    60
     [7,]    7   14   21   28   35   42   49   56   63    70
     [8,]    8   16   24   32   40   48   56   64   72    80
     [9,]    9   18   27   36   45   54   63   72   81    90
    [10,]   10   20   30   40   50   60   70   80   90   100
    
    , , 2
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]    2    4    6    8   10   12   14   16   18    20
     [2,]    4    8   12   16   20   24   28   32   36    40
     [3,]    6   12   18   24   30   36   42   48   54    60
     [4,]    8   16   24   32   40   48   56   64   72    80
     [5,]   10   20   30   40   50   60   70   80   90   100
     [6,]   12   24   36   48   60   72   84   96  108   120
     [7,]   14   28   42   56   70   84   98  112  126   140
     [8,]   16   32   48   64   80   96  112  128  144   160
     [9,]   18   36   54   72   90  108  126  144  162   180
    [10,]   20   40   60   80  100  120  140  160  180   200
    
    , , 3
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]    3    6    9   12   15   18   21   24   27    30
     [2,]    6   12   18   24   30   36   42   48   54    60
     [3,]    9   18   27   36   45   54   63   72   81    90
     [4,]   12   24   36   48   60   72   84   96  108   120
     [5,]   15   30   45   60   75   90  105  120  135   150
     [6,]   18   36   54   72   90  108  126  144  162   180
     [7,]   21   42   63   84  105  126  147  168  189   210
     [8,]   24   48   72   96  120  144  168  192  216   240
     [9,]   27   54   81  108  135  162  189  216  243   270
    [10,]   30   60   90  120  150  180  210  240  270   300
    
    , , 4
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]    4    8   12   16   20   24   28   32   36    40
     [2,]    8   16   24   32   40   48   56   64   72    80
     [3,]   12   24   36   48   60   72   84   96  108   120
     [4,]   16   32   48   64   80   96  112  128  144   160
     [5,]   20   40   60   80  100  120  140  160  180   200
     [6,]   24   48   72   96  120  144  168  192  216   240
     [7,]   28   56   84  112  140  168  196  224  252   280
     [8,]   32   64   96  128  160  192  224  256  288   320
     [9,]   36   72  108  144  180  216  252  288  324   360
    [10,]   40   80  120  160  200  240  280  320  360   400
    
    , , 5
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]    5   10   15   20   25   30   35   40   45    50
     [2,]   10   20   30   40   50   60   70   80   90   100
     [3,]   15   30   45   60   75   90  105  120  135   150
     [4,]   20   40   60   80  100  120  140  160  180   200
     [5,]   25   50   75  100  125  150  175  200  225   250
     [6,]   30   60   90  120  150  180  210  240  270   300
     [7,]   35   70  105  140  175  210  245  280  315   350
     [8,]   40   80  120  160  200  240  280  320  360   400
     [9,]   45   90  135  180  225  270  315  360  405   450
    [10,]   50  100  150  200  250  300  350  400  450   500
    
    , , 6
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]    6   12   18   24   30   36   42   48   54    60
     [2,]   12   24   36   48   60   72   84   96  108   120
     [3,]   18   36   54   72   90  108  126  144  162   180
     [4,]   24   48   72   96  120  144  168  192  216   240
     [5,]   30   60   90  120  150  180  210  240  270   300
     [6,]   36   72  108  144  180  216  252  288  324   360
     [7,]   42   84  126  168  210  252  294  336  378   420
     [8,]   48   96  144  192  240  288  336  384  432   480
     [9,]   54  108  162  216  270  324  378  432  486   540
    [10,]   60  120  180  240  300  360  420  480  540   600
    
    , , 7
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]    7   14   21   28   35   42   49   56   63    70
     [2,]   14   28   42   56   70   84   98  112  126   140
     [3,]   21   42   63   84  105  126  147  168  189   210
     [4,]   28   56   84  112  140  168  196  224  252   280
     [5,]   35   70  105  140  175  210  245  280  315   350
     [6,]   42   84  126  168  210  252  294  336  378   420
     [7,]   49   98  147  196  245  294  343  392  441   490
     [8,]   56  112  168  224  280  336  392  448  504   560
     [9,]   63  126  189  252  315  378  441  504  567   630
    [10,]   70  140  210  280  350  420  490  560  630   700
    
    , , 8
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]    8   16   24   32   40   48   56   64   72    80
     [2,]   16   32   48   64   80   96  112  128  144   160
     [3,]   24   48   72   96  120  144  168  192  216   240
     [4,]   32   64   96  128  160  192  224  256  288   320
     [5,]   40   80  120  160  200  240  280  320  360   400
     [6,]   48   96  144  192  240  288  336  384  432   480
     [7,]   56  112  168  224  280  336  392  448  504   560
     [8,]   64  128  192  256  320  384  448  512  576   640
     [9,]   72  144  216  288  360  432  504  576  648   720
    [10,]   80  160  240  320  400  480  560  640  720   800
    
    , , 9
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]    9   18   27   36   45   54   63   72   81    90
     [2,]   18   36   54   72   90  108  126  144  162   180
     [3,]   27   54   81  108  135  162  189  216  243   270
     [4,]   36   72  108  144  180  216  252  288  324   360
     [5,]   45   90  135  180  225  270  315  360  405   450
     [6,]   54  108  162  216  270  324  378  432  486   540
     [7,]   63  126  189  252  315  378  441  504  567   630
     [8,]   72  144  216  288  360  432  504  576  648   720
     [9,]   81  162  243  324  405  486  567  648  729   810
    [10,]   90  180  270  360  450  540  630  720  810   900
    
    , , 10
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]   10   20   30   40   50   60   70   80   90   100
     [2,]   20   40   60   80  100  120  140  160  180   200
     [3,]   30   60   90  120  150  180  210  240  270   300
     [4,]   40   80  120  160  200  240  280  320  360   400
     [5,]   50  100  150  200  250  300  350  400  450   500
     [6,]   60  120  180  240  300  360  420  480  540   600
     [7,]   70  140  210  280  350  420  490  560  630   700
     [8,]   80  160  240  320  400  480  560  640  720   800
     [9,]   90  180  270  360  450  540  630  720  810   900
    [10,]  100  200  300  400  500  600  700  800  900  1000
    
    , , 11
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]   11   22   33   44   55   66   77   88   99   110
     [2,]   22   44   66   88  110  132  154  176  198   220
     [3,]   33   66   99  132  165  198  231  264  297   330
     [4,]   44   88  132  176  220  264  308  352  396   440
     [5,]   55  110  165  220  275  330  385  440  495   550
     [6,]   66  132  198  264  330  396  462  528  594   660
     [7,]   77  154  231  308  385  462  539  616  693   770
     [8,]   88  176  264  352  440  528  616  704  792   880
     [9,]   99  198  297  396  495  594  693  792  891   990
    [10,]  110  220  330  440  550  660  770  880  990  1100
    
    , , 12
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]   12   24   36   48   60   72   84   96  108   120
     [2,]   24   48   72   96  120  144  168  192  216   240
     [3,]   36   72  108  144  180  216  252  288  324   360
     [4,]   48   96  144  192  240  288  336  384  432   480
     [5,]   60  120  180  240  300  360  420  480  540   600
     [6,]   72  144  216  288  360  432  504  576  648   720
     [7,]   84  168  252  336  420  504  588  672  756   840
     [8,]   96  192  288  384  480  576  672  768  864   960
     [9,]  108  216  324  432  540  648  756  864  972  1080
    [10,]  120  240  360  480  600  720  840  960 1080  1200
    
    , , 13
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]   13   26   39   52   65   78   91  104  117   130
     [2,]   26   52   78  104  130  156  182  208  234   260
     [3,]   39   78  117  156  195  234  273  312  351   390
     [4,]   52  104  156  208  260  312  364  416  468   520
     [5,]   65  130  195  260  325  390  455  520  585   650
     [6,]   78  156  234  312  390  468  546  624  702   780
     [7,]   91  182  273  364  455  546  637  728  819   910
     [8,]  104  208  312  416  520  624  728  832  936  1040
     [9,]  117  234  351  468  585  702  819  936 1053  1170
    [10,]  130  260  390  520  650  780  910 1040 1170  1300
    
    , , 14
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]   14   28   42   56   70   84   98  112  126   140
     [2,]   28   56   84  112  140  168  196  224  252   280
     [3,]   42   84  126  168  210  252  294  336  378   420
     [4,]   56  112  168  224  280  336  392  448  504   560
     [5,]   70  140  210  280  350  420  490  560  630   700
     [6,]   84  168  252  336  420  504  588  672  756   840
     [7,]   98  196  294  392  490  588  686  784  882   980
     [8,]  112  224  336  448  560  672  784  896 1008  1120
     [9,]  126  252  378  504  630  756  882 1008 1134  1260
    [10,]  140  280  420  560  700  840  980 1120 1260  1400
    
    , , 15
    
          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
     [1,]   15   30   45   60   75   90  105  120  135   150
     [2,]   30   60   90  120  150  180  210  240  270   300
     [3,]   45   90  135  180  225  270  315  360  405   450
     [4,]   60  120  180  240  300  360  420  480  540   600
     [5,]   75  150  225  300  375  450  525  600  675   750
     [6,]   90  180  270  360  450  540  630  720  810   900
     [7,]  105  210  315  420  525  630  735  840  945  1050
     [8,]  120  240  360  480  600  720  840  960 1080  1200
     [9,]  135  270  405  540  675  810  945 1080 1215  1350
    [10,]  150  300  450  600  750  900 1050 1200 1350  1500
    
    

### While Loop
Loop until a specific condition is met


```R
i <- 1

while (i < 6) {
   print(i)
   i = i+1
}
```

    [1] 1
    [1] 2
    [1] 3
    [1] 4
    [1] 5
    


```R
a <- 0
b <- 1
print(a)
while (b < 50) {
    print(b)
    temp <- a + b
    a <- b
    b <- temp
}
```

    [1] 0
    [1] 1
    [1] 1
    [1] 2
    [1] 3
    [1] 5
    [1] 8
    [1] 13
    [1] 21
    [1] 34
    


```R
a <- 0
b <- 1
print(a)
while (b < 50) {
     print(b)
     temp <- a + b
     a <- b
     b <- temp
}
```

    [1] 0
    [1] 1
    [1] 1
    [1] 2
    [1] 3
    [1] 5
    [1] 8
    [1] 13
    [1] 21
    [1] 34


## repeat, break, next and switch

### Repeat statement
Iterate over a block of code multiple number of times.


```R
x <- 1

repeat {
   print(x)
   x = x+1
   if (x == 6){
       break
   }
}
```

    [1] 1
    [1] 2
    [1] 3
    [1] 4
    [1] 5


### Break Statement
break is used inside any loop like `repeat`, `for` or `while` to stop the iterations and flow the control outside of the loop.


```R
x <- 1:5

for (val in x) {
    if (val == 3){
        break
    }
    print(val)
}
```

    [1] 1
    [1] 2
    


```R
x <- 1:10
for (num in x){
    if (num==6) break
    mynum <- paste(num, "and so on. ", sep = " ")
    print(mynum)
}
```

    [1] "1 and so on. "
    [1] "2 and so on. "
    [1] "3 and so on. "
    [1] "4 and so on. "
    [1] "5 and so on. "


### Next Statment
* Useful to controls the flow of R loops  
* generaal usage inside the For Loop and While Loop  

**Example:**


```R
x <- 1:5

for (val in x) {
    if (val == 3){
        next
    }
    print(val)
}
```

    [1] 1
    [1] 2
    [1] 4
    [1] 5
    


```R
m=20
odd=numeric()

for (k in 1:m) {
   if (!k %% 2)
      next
      odd <- c(odd,k)
}
odd
```


<ol class=list-inline>
	<li>1</li>
	<li>3</li>
	<li>5</li>
	<li>7</li>
	<li>9</li>
	<li>11</li>
	<li>13</li>
	<li>15</li>
	<li>17</li>
	<li>19</li>
</ol>




```R
for (i in 1:10) {
  if (!i %% 2){
    next
  }
    print(i)
}
```

    [1] 1
    [1] 3
    [1] 5
    [1] 7
    [1] 9
    


```R
x <- 1:10
for (num in x){
    if (num %% 3 == 1) next
    mynum <- paste(num, "and so on. ", sep = " ")
    print(mynum)
}
```

    [1] "2 and so on. "
    [1] "3 and so on. "
    [1] "5 and so on. "
    [1] "6 and so on. "
    [1] "8 and so on. "
    [1] "9 and so on. "


### Switch Statment
**switch statement allows a variable to be tested for equality against a list of values. Each value is called a case**  

Syntax:
```r
switch (Expression, "Option 1", "Option 2", "Option 3", ....., "Option N") 
```

**Examples:**

* If the value evaluated is a number, that item of the list is returned.


```R
switch(2,"red","green","blue")
# [1] "green"
switch(1,"red","green","blue")
# [1] "red"
################
x <- "red"
switch(x, red="cloth", size=5, name="table")
#################
# If the numeric value is out of range (greater than the number of items in the list or smaller than 1), then, 
# NULL is returned.
 x <- switch(4,"red","green","blue")
 x
 x <- switch(0,"red","green","blue")
 x
```


'green'



'red'



'cloth'



    NULL



    NULL



```R
number1 <- 30
number2 <- 20
operator <- readline(prompt="Please enter any ARITHMETIC OPERATOR You wish!: ")
 
switch(operator,
       "+" = print(paste("Addition of two numbers is: ", number1 + number2)),
       "-" = print(paste("Subtraction of two numbers is: ", number1 - number2)),
       "*" = print(paste("Multiplication of two numbers is: ", number1 * number2)),
       "^" = print(paste("Exponent of two numbers is: ", number1 ^ number2)),
       "/" = print(paste("Division of two numbers is: ", number1 / number2)),
       "%/%" = print(paste("Integer Division of two numbers is: ", number1 %/% number2)),
       "%%" = print(paste("Division of two numbers is: ", number1 %% number2))
)
```

    Please enter any ARITHMETIC OPERATOR You wish!: -
    [1] "Subtraction of two numbers is:  10"


<span style="color:red">**Conclusion**</span>

**Loops are not recommended until and unless its really needed, since R has vectorisation feature**


```R
# let us take a vector 
vect <- c(1,2,3,4,5,6,7,9)
# now we multiply each element of vect with 5
print(vect * 5)
# now we add each element of vect with 5
print(vect + 5)
# now we subtract each element of vect with 5
print(vect - 5)
```

    [1]  5 10 15 20 25 30 35 45
    [1]  6  7  8  9 10 11 12 14
    [1] -4 -3 -2 -1  0  1  2  4


# Vectorization and recycling concepts

**Vectorized Operations**

* when you apply a function to a vector, it applies the function to every element of the vector.
* All the mathematical operators, like +, -, *, and the logical operators, like & (AND), | (OR), and the comparison operators, like < and > are hungry to operate element-wise on every element of a vector.



For example, to add pairs of numbers contained in two vectors


```R
first <- c(86, 42, 123, -45)
second <- c(78, 210, 48, 52)
first * 5 # with scalar
second / 2.3
first + second # vector with another vector
first * second
first - second
first/second
```


<ol class=list-inline>
	<li>430</li>
	<li>210</li>
	<li>615</li>
	<li>-225</li>
</ol>




<ol class=list-inline>
	<li>33.9130434782609</li>
	<li>91.304347826087</li>
	<li>20.8695652173913</li>
	<li>22.6086956521739</li>
</ol>




<ol class=list-inline>
	<li>164</li>
	<li>252</li>
	<li>171</li>
	<li>7</li>
</ol>




<ol class=list-inline>
	<li>6708</li>
	<li>8820</li>
	<li>5904</li>
	<li>-2340</li>
</ol>




<ol class=list-inline>
	<li>8</li>
	<li>-168</li>
	<li>75</li>
	<li>-97</li>
</ol>




<ol class=list-inline>
	<li>1.1025641025641</li>
	<li>0.2</li>
	<li>2.5625</li>
	<li>-0.865384615384615</li>
</ol>




```R
a <- 1:10
b <- 1:10
```


```R
res <- numeric(length = length(a))
for (i in seq_along(a)) {
  res[i] <- a[i] + b[i]
}
res
```


<ol class=list-inline>
	<li>2</li>
	<li>4</li>
	<li>6</li>
	<li>8</li>
	<li>10</li>
	<li>12</li>
	<li>14</li>
	<li>16</li>
	<li>18</li>
	<li>20</li>
</ol>



Instead, `+` is a vectorized function which can operate on entire vectors at once


```R
res2 <- a + b
res2
all.equal(res, res2)
```


<ol class=list-inline>
	<li>2</li>
	<li>4</li>
	<li>6</li>
	<li>8</li>
	<li>10</li>
	<li>12</li>
	<li>14</li>
	<li>16</li>
	<li>18</li>
	<li>20</li>
</ol>




TRUE


**Vector Recycling**

* R likes to operate on vectors of the same length
*  if it encounters two vectors of different lengths in a binary operation, it recycles the smaller vector until it is the same length as the longest vector.
* It gives some warning, but still returns the output.
* If you perform an operation on two or more vectors of unequal length, R will recycle elements of the shorter vector(s) to match the longest vector.
* When R reaches the end of the shorter vector `b`, it starts again at the first element of `b` and continues until it reaches the last element of the longest vector `a`.


```R
a <- 1:10
b <- 1:5
a + b
```


<ol class=list-inline>
	<li>2</li>
	<li>4</li>
	<li>6</li>
	<li>8</li>
	<li>10</li>
	<li>7</li>
	<li>9</li>
	<li>11</li>
	<li>13</li>
	<li>15</li>
</ol>




```R
a <- 1:10
b <- 5
a * b # here b  is a vector of length 1 
```


<ol class=list-inline>
	<li>5</li>
	<li>10</li>
	<li>15</li>
	<li>20</li>
	<li>25</li>
	<li>30</li>
	<li>35</li>
	<li>40</li>
	<li>45</li>
	<li>50</li>
</ol>



* When the length of the longer object is a multiple of the shorter object length (as in our example above), the recycling occurs silently. When the longer object length is not a multiple of the shorter object length, a warning is given:


```R
a <- 1:10
b <- 1:7
a + b
```

    Warning message in a + b:
    "longer object length is not a multiple of shorter object length"


<ol class=list-inline>
	<li>2</li>
	<li>4</li>
	<li>6</li>
	<li>8</li>
	<li>10</li>
	<li>12</li>
	<li>14</li>
	<li>9</li>
	<li>11</li>
	<li>13</li>
</ol>




```R
df <- data.frame(x = 1:3, y = c("a", "b", "c"))
df
df1 <- cbind(df, 1) 
print(df1)
```


<table>
<thead><tr><th scope=col>x</th><th scope=col>y</th></tr></thead>
<tbody>
	<tr><td>1</td><td>a</td></tr>
	<tr><td>2</td><td>b</td></tr>
	<tr><td>3</td><td>c</td></tr>
</tbody>
</table>



      x y 1
    1 1 a 1
    2 2 b 1
    3 3 c 1
    


```R
head(mtcars)
```


<table>
<thead><tr><th></th><th scope=col>mpg</th><th scope=col>cyl</th><th scope=col>disp</th><th scope=col>hp</th><th scope=col>drat</th><th scope=col>wt</th><th scope=col>qsec</th><th scope=col>vs</th><th scope=col>am</th><th scope=col>gear</th><th scope=col>carb</th></tr></thead>
<tbody>
	<tr><th scope=row>Mazda RX4</th><td>21.0 </td><td>6    </td><td>160  </td><td>110  </td><td>3.90 </td><td>2.620</td><td>16.46</td><td>0    </td><td>1    </td><td>4    </td><td>4    </td></tr>
	<tr><th scope=row>Mazda RX4 Wag</th><td>21.0 </td><td>6    </td><td>160  </td><td>110  </td><td>3.90 </td><td>2.875</td><td>17.02</td><td>0    </td><td>1    </td><td>4    </td><td>4    </td></tr>
	<tr><th scope=row>Datsun 710</th><td>22.8 </td><td>4    </td><td>108  </td><td> 93  </td><td>3.85 </td><td>2.320</td><td>18.61</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Hornet 4 Drive</th><td>21.4 </td><td>6    </td><td>258  </td><td>110  </td><td>3.08 </td><td>3.215</td><td>19.44</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
	<tr><th scope=row>Hornet Sportabout</th><td>18.7 </td><td>8    </td><td>360  </td><td>175  </td><td>3.15 </td><td>3.440</td><td>17.02</td><td>0    </td><td>0    </td><td>3    </td><td>2    </td></tr>
	<tr><th scope=row>Valiant</th><td>18.1 </td><td>6    </td><td>225  </td><td>105  </td><td>2.76 </td><td>3.460</td><td>20.22</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
</tbody>
</table>




```R
head(iris)
```


<table>
<thead><tr><th scope=col>Sepal.Length</th><th scope=col>Sepal.Width</th><th scope=col>Petal.Length</th><th scope=col>Petal.Width</th><th scope=col>Species</th></tr></thead>
<tbody>
	<tr><td>5.1   </td><td>3.5   </td><td>1.4   </td><td>0.2   </td><td>setosa</td></tr>
	<tr><td>4.9   </td><td>3.0   </td><td>1.4   </td><td>0.2   </td><td>setosa</td></tr>
	<tr><td>4.7   </td><td>3.2   </td><td>1.3   </td><td>0.2   </td><td>setosa</td></tr>
	<tr><td>4.6   </td><td>3.1   </td><td>1.5   </td><td>0.2   </td><td>setosa</td></tr>
	<tr><td>5.0   </td><td>3.6   </td><td>1.4   </td><td>0.2   </td><td>setosa</td></tr>
	<tr><td>5.4   </td><td>3.9   </td><td>1.7   </td><td>0.4   </td><td>setosa</td></tr>
</tbody>
</table>


```R
# Define the cars vector with 5 values
cars <- c(1, 3, 6, 4, 9)

# Graph the cars vector with all defaults
plot(cars)
```

<span style="color:red; font-family:Comic Sans MS">Sources & References</span>    
<a href="https://www.tutorialgateway.org/r-programming/" target="_blank">https://www.tutorialgateway.org/r-programming//</a>  
<a href="https://swcarpentry.github.io/r-novice-inflammation/15-supp-loops-in-depth/" target="_blank">https://swcarpentry.github.io/r-novice-inflammation/15-supp-loops-in-depth/</a>  
