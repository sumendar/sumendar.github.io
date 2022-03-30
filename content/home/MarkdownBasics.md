## Present working directory path


```python
pwd
```




    'C:\\Users\\Administrator\\Documents\\GitHub\\DSAIML\\00-Python\\00-notebooks'



## Markdown syntax

**markdown syntax:** https://www.markdownguide.org/basic-syntax/ 

## Accessing/loading a files 

**If File is available in the same current working directory folder**


```python
import pandas as pd

df1 = pd.read_csv(
    'hcpuniverse.csv', sep=";"
)  #goback to the previous parent directory files other than present working directory
```


```python
df1.shape
```




    (3681, 6)



**If the File is available in the folder curresponding the same working directory location**


```python
import pandas as pd

df2 = pd.read_csv(
    '01A-data/hcpuniverse.csv', sep=";"
)  #goback to the previous parent directory files other than present working directory
```


```python
df2.shape
```




    (3681, 6)



**OR**


```python
import pandas as pd

df3 = pd.read_csv(
    './01A-data/hcpuniverse.csv', sep=";"
)  #goback to the previous parent directory files other than present working directory
```


```python
df3.shape
```




    (3681, 6)



### Accessing/loading a file which present in other than current/present working directory exact parent of current


```python
import pandas as pd

df4 = pd.read_csv(
    '../01-data/hcpuniverse.csv', sep=";"
)  #goback to the previous parent directory files other than present working directory
```


```python
df4.shape
```




    (3681, 6)




```python
df4.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>c_First_Name</th>
      <th>h_First_Name</th>
      <th>c_Last_Name</th>
      <th>h_Last_Name</th>
      <th>c_Title</th>
      <th>h_Title</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Brian</td>
      <td>BRIAN</td>
      <td>Kelly</td>
      <td>KELLY</td>
      <td>Medicine</td>
      <td>PHYSICAL MEDICINE AND REHABILITATION</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Rahul</td>
      <td>RAHUL</td>
      <td>Sharma</td>
      <td>SHARMA</td>
      <td>Laboratory Director</td>
      <td>PHYSICAL MEDICINE AND REHABILITATION</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Kashif</td>
      <td>KASHIF</td>
      <td>Khan</td>
      <td>KHAN</td>
      <td>Anesthesia</td>
      <td>GERIATRIC MEDICINE</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Mark</td>
      <td>MARK</td>
      <td>Smith</td>
      <td>SMITH</td>
      <td>Anesthesia</td>
      <td>INTERNAL MEDICINE</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Paul</td>
      <td>PAUL</td>
      <td>Harris</td>
      <td>HARRIS</td>
      <td>Apprenticeship in Joinery</td>
      <td>FAMILY PRACTICE</td>
    </tr>
  </tbody>
</table>
</div>



### Accessing/loading a file which present in other than current/present working directory grand parent of current path  


```python
import pandas as pd
df5 = pd.read_csv('../../00-Python/hcpuniverse.csv',sep=";") #goback to the previous/parent directory files
```


```python
df5.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>c_First_Name</th>
      <th>h_First_Name</th>
      <th>c_Last_Name</th>
      <th>h_Last_Name</th>
      <th>c_Title</th>
      <th>h_Title</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Brian</td>
      <td>BRIAN</td>
      <td>Kelly</td>
      <td>KELLY</td>
      <td>Medicine</td>
      <td>PHYSICAL MEDICINE AND REHABILITATION</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Rahul</td>
      <td>RAHUL</td>
      <td>Sharma</td>
      <td>SHARMA</td>
      <td>Laboratory Director</td>
      <td>PHYSICAL MEDICINE AND REHABILITATION</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Kashif</td>
      <td>KASHIF</td>
      <td>Khan</td>
      <td>KHAN</td>
      <td>Anesthesia</td>
      <td>GERIATRIC MEDICINE</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Mark</td>
      <td>MARK</td>
      <td>Smith</td>
      <td>SMITH</td>
      <td>Anesthesia</td>
      <td>INTERNAL MEDICINE</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Paul</td>
      <td>PAUL</td>
      <td>Harris</td>
      <td>HARRIS</td>
      <td>Apprenticeship in Joinery</td>
      <td>FAMILY PRACTICE</td>
    </tr>
  </tbody>
</table>
</div>




```python
import pandas as pd
df6 = pd.read_csv('../../../DSAIML/hcpuniverse.csv',sep=";") #goback to the previous/parent directory files
```


```python
df6.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>c_First_Name</th>
      <th>h_First_Name</th>
      <th>c_Last_Name</th>
      <th>h_Last_Name</th>
      <th>c_Title</th>
      <th>h_Title</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Brian</td>
      <td>BRIAN</td>
      <td>Kelly</td>
      <td>KELLY</td>
      <td>Medicine</td>
      <td>PHYSICAL MEDICINE AND REHABILITATION</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Rahul</td>
      <td>RAHUL</td>
      <td>Sharma</td>
      <td>SHARMA</td>
      <td>Laboratory Director</td>
      <td>PHYSICAL MEDICINE AND REHABILITATION</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Kashif</td>
      <td>KASHIF</td>
      <td>Khan</td>
      <td>KHAN</td>
      <td>Anesthesia</td>
      <td>GERIATRIC MEDICINE</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Mark</td>
      <td>MARK</td>
      <td>Smith</td>
      <td>SMITH</td>
      <td>Anesthesia</td>
      <td>INTERNAL MEDICINE</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Paul</td>
      <td>PAUL</td>
      <td>Harris</td>
      <td>HARRIS</td>
      <td>Apprenticeship in Joinery</td>
      <td>FAMILY PRACTICE</td>
    </tr>
  </tbody>
</table>
</div>



### Accessing/loading a file which present in other than current/present working directory other than grand parent of current path, super path let's say computer account name path


```python
import pandas as pd

df7 = pd.read_csv(
    '~/hcpuniverse.csv', sep=";"
)  #goback to the computer's account named directory(if the file located there) "C:\Users\Administrator" is nothing but ~
```


```python
df7.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>c_First_Name</th>
      <th>h_First_Name</th>
      <th>c_Last_Name</th>
      <th>h_Last_Name</th>
      <th>c_Title</th>
      <th>h_Title</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Brian</td>
      <td>BRIAN</td>
      <td>Kelly</td>
      <td>KELLY</td>
      <td>Medicine</td>
      <td>PHYSICAL MEDICINE AND REHABILITATION</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Rahul</td>
      <td>RAHUL</td>
      <td>Sharma</td>
      <td>SHARMA</td>
      <td>Laboratory Director</td>
      <td>PHYSICAL MEDICINE AND REHABILITATION</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Kashif</td>
      <td>KASHIF</td>
      <td>Khan</td>
      <td>KHAN</td>
      <td>Anesthesia</td>
      <td>GERIATRIC MEDICINE</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Mark</td>
      <td>MARK</td>
      <td>Smith</td>
      <td>SMITH</td>
      <td>Anesthesia</td>
      <td>INTERNAL MEDICINE</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Paul</td>
      <td>PAUL</td>
      <td>Harris</td>
      <td>HARRIS</td>
      <td>Apprenticeship in Joinery</td>
      <td>FAMILY PRACTICE</td>
    </tr>
  </tbody>
</table>
</div>



## Tables Generation

Tables Generator: https://www.tablesgenerator.com/markdown_tables

## LaTeX/Mathematics codes for statistical symbols

**LaTeX/Mathematics:**   
https://en.wikibooks.org/wiki/LaTeX/Mathematics  
https://towardsdatascience.com/write-markdown-latex-in-the-jupyter-notebook-10985edb91fd  
https://personal.math.ubc.ca/~pwalls/math-python/jupyter/latex/  
https://www.overleaf.com/learn  

$\Phi$

$e^{i \pi} + 1 = 0$

$\forall x$

$$
\frac{arg 1}{arg 2} \\
x^2\\
e^{i\pi}\\
A_i\\
B_{ij}\\
\sqrt[n]{arg}	
$$

Given : $\pi = 3.14$ , $\alpha = \frac{3\pi}{4}\, rad$
$$
\omega = 2\pi f \\
f = \frac{c}{\lambda}\\
\lambda_0=\theta^2+\delta\\
\Delta\lambda = \frac{1}{\lambda^2}
$$

$
\delta
$
$
\Delta
$

$k_{n+1} = n^2 + k_n^2 - k_{n-1}$

$\frac{n!}{k!(n-k)!} = \binom{n}{k}$

$\begin{equation}
\frac{
    \begin{array}[b]{r}
      \left( x_1 x_2 \right)\\
      \times \left( x'_1 x'_2 \right)
    \end{array}
  }{
    \left( y_1y_2y_3y_4 \right)
  }
\end{equation}$

$
\int\limits_a^b
$

$
50 \textrm{ apples} \times 100
 \textbf{ apples} = \textit{lots of apples}^2
$

$
\begin{equation}
  x = a_0 + \cfrac{1}{a_1 
          + \cfrac{1}{a_2 
          + \cfrac{1}{a_3 + \cfrac{1}{a_4} } } }
\end{equation}
$

$
    \binom{n}{k} = \frac{n!}{k!(n-k)!}
$

$$
\mathbf{J}
=
\frac{d \mathbf{f}}{d \mathbf{x}}
=
\left[ \frac{\partial \mathbf{f}}{\partial x_1}
\cdots \frac{\partial \mathbf{f}}{\partial x_n} \right]
=
\begin{bmatrix}
\frac{\partial f_1}{\partial x_1} & \cdots &
\frac{\partial f_1}{\partial x_n} \\
\vdots & \ddots & \vdots \\
\frac{\partial f_m}{\partial x_1} & \cdots &
\frac{\partial f_m}{\partial x_n}
\end{bmatrix}
$$


## Images Embedding From Internet Source

<table>
    <tr>
        <td>
            <img src="https://saturn-public-assets.s3.us-east-2.amazonaws.com/example-resources/dask.png" width="300">
        </td>
        <td>
            <img src="https://saturn-public-assets.s3.us-east-2.amazonaws.com/example-resources/rapids.png" width="300">
        </td>
        <td>
            <img src="https://saturn-public-assets.s3.us-east-2.amazonaws.com/example-resources/snowflake.png" width="300">
        </td>
    </tr>
</table>

![Imgur](https://i.imgur.com/1FohGsV.jpg)


## Download Notebook as PDF

### First Approach  
Source: https://mpievolbio-scicomp.pages.gwdg.de/blog/post/2020-12-09_pandoc_vs_nbconvert/   
`pandoc --to pdf --from ipynb -o Notebook.pdf Notebook.ipynb`  
                                               OR                                                     
Download as **PDF via LaTex(.pdf)**    
                                               OR                                                     
Goto **Chrome three dots** choose **print** option and **Save as PDF**                        


### Second Approach    
**Use Another Approach like below:**  
https://jupytext.readthedocs.io/en/latest/using-cli.html

### Third Approach
**Using nbconvert with all necessary installation mentioned below:**   
https://nbconvert.readthedocs.io/en/latest/install.html

## Output Generated From Notebook and embed output to MD

```python
# Sample Code
import matplotlib.pyplot as plt
import numpy as np

xpoints = np.array([1, 8])
ypoints = np.array([3, 10])

plt.plot(xpoints, ypoints)
plt.show()

```


    
![png](output_52_0.png)
    
## Embedding Videos


<iframe src="https://www.youtube.com/embed/NnTvZWp5Q7o"></iframe>

## Embedding  Tweets

<iframe
	border=0
	frameborder=0
	height=250
	width=550  
	src="https://twitframe.com/show?url=https%3A%2F%2Ftwitter.com%2Fjack%2Fstatus%2F20">
</iframe>
## Embedding Images From Local Folder

- ![Some](imgsAudVid/Engelbart.jpg)
- Above Code OR Use This Below Code
- ![[imgsAudVid/Engelbart.jpg]]

## Embedding Audio Files to the MD File
![[imgsAudVid/Excerpt from Mother of All Demos (1968).ogg]]