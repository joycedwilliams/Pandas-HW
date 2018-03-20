#pandas-hw

```python
# Import the Pandas library
# import os
# import glob
import pandas as pd
import numpy as np
```


```python

```


```python
# Name of the CSV files
file = "../PyCitySchools/schools_complete.csv"

file2 = "../PyCitySchools/students_complete.csv"
```


```python

```


```python
#df = pd.read_csv('schools_complete.csv', usecols=['School ID','name', 'type', 'size', 'budget'], encoding = "ISO-8859-1")
#df.head()

df = pd.read_csv('schools_complete.csv', encoding = "ISO-8859-1")
df.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>name</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
# Define the new name of the columns
newcols = {'name': 'schools'}

# Use `rename()` to rename your columns
df.rename(columns=newcols, inplace=True)
df.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>schools</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
# Count the number of schools
school_id = df["School ID"].value_counts()
school_id

#Create a dataframe for the school id
pd.DataFrame(school_id)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>14</th>
      <td>1</td>
    </tr>
    <tr>
      <th>13</th>
      <td>1</td>
    </tr>
    <tr>
      <th>12</th>
      <td>1</td>
    </tr>
    <tr>
      <th>11</th>
      <td>1</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
    </tr>
    <tr>
      <th>0</th>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Count the types of schools
school_name = df["schools"].value_counts()
school_name

#Create a dataframe for the school names
pd.DataFrame(school_name)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>schools</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Pena High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Bailey High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
# Count the type of schools
school_type = df["type"].value_counts()
school_type

#Create a dataframe for the types of schools
pd.DataFrame(school_type)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Charter</th>
      <td>8</td>
    </tr>
    <tr>
      <th>District</th>
      <td>7</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
# Total school budget
#budget = df["budget"].value_counts()
#print(budget)
```


```python

```


```python
# Total school size
# size = df["size"].value_counts()
# size
```


```python

```


```python
df2 = pd.read_csv('students_complete.csv')
#df2 = pd.read_csv('students_complete.csv', usecols=['School ID','name', 'gender', 'grade', 'school', 'reading_score'], encoding = "ISO-8859-1")
```


```python

```


```python
# Define the new name of the columns
newcols = {"school": 'schools'}

# Use `rename()` to rename your columns
df2.rename(columns=newcols, inplace=True)
df2.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Student ID</th>
      <th>name</th>
      <th>gender</th>
      <th>grade</th>
      <th>schools</th>
      <th>reading_score</th>
      <th>math_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
# Count the grade levels
#Create a dataframe for the types of schools
```


```python
grade_level = df2["grade"].value_counts()

pd.DataFrame(grade_level)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>grade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>9th</th>
      <td>11408</td>
    </tr>
    <tr>
      <th>10th</th>
      <td>10168</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>9695</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>7899</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Count the geders
#Create a dataframe for the genders
```


```python
sex = df2["gender"].value_counts()

pd.DataFrame(sex)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>F</th>
      <td>19735</td>
    </tr>
    <tr>
      <th>M</th>
      <td>19435</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Merge two dataframes using an inner join
```


```python
merged_school_data = pd.merge(df, df2, on="schools")
merged_school_data.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>schools</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
      <th>Student ID</th>
      <th>name</th>
      <th>gender</th>
      <th>grade</th>
      <th>reading_score</th>
      <th>math_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>66</td>
      <td>79</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>94</td>
      <td>61</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>90</td>
      <td>60</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>67</td>
      <td>58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>97</td>
      <td>84</td>
    </tr>
  </tbody>
</table>
</div>




```python
# School Summary

districts = merged_school_data.groupby(["schools"])["type"].unique()
print(districts)

print("-----------------------------------------")

totalstudents = merged_school_data.groupby(["schools"]).count()["size"]
print(totalstudents)

print("-----------------------------------------")

average_budget_per_student = merged_school_data.groupby(["schools"]).count()["budget"]/totalstudents
print(average_budget_per_student)

print("-----------------------------------------")

school_budget =  merged_school_data.groupby(["schools"])["budget"].unique()
print(school_budget)

print("-----------------------------------------")

average_math_score = merged_school_data.groupby(["schools"]).mean()["math_score"]
print(round(average_math_score))

print("-----------------------------------------")

average_reading_score = merged_school_data.groupby(["schools"]).mean()["reading_score"]
print(round(average_reading_score))

print("-----------------------------------------")

percent_passing_math = merged_school_data.groupby(["schools"]).sum()["math_score"] >70 / totalstudents
print(percent_passing_math)

print("-----------------------------------------")

percent_passing_reading = merged_school_data.groupby(["schools"]).sum()["reading_score"] >70 / totalstudents
print(percent_passing_reading)

print("-----------------------------------------")

# percent_overall_pass = merged_school_data.groupby(["schools"]).sum()["average_math_score"] + ["average_reading_score"]/2
# percent_overall_pass

# pd.DataFrame(merged_school_data.groupby(["schools"]))


```

    schools
    Bailey High School       [District]
    Cabrera High School       [Charter]
    Figueroa High School     [District]
    Ford High School         [District]
    Griffin High School       [Charter]
    Hernandez High School    [District]
    Holden High School        [Charter]
    Huang High School        [District]
    Johnson High School      [District]
    Pena High School          [Charter]
    Rodriguez High School    [District]
    Shelton High School       [Charter]
    Thomas High School        [Charter]
    Wilson High School        [Charter]
    Wright High School        [Charter]
    Name: type, dtype: object
    -----------------------------------------
    schools
    Bailey High School       4976
    Cabrera High School      1858
    Figueroa High School     2949
    Ford High School         2739
    Griffin High School      1468
    Hernandez High School    4635
    Holden High School        427
    Huang High School        2917
    Johnson High School      4761
    Pena High School          962
    Rodriguez High School    3999
    Shelton High School      1761
    Thomas High School       1635
    Wilson High School       2283
    Wright High School       1800
    Name: size, dtype: int64
    -----------------------------------------
    schools
    Bailey High School       1.0
    Cabrera High School      1.0
    Figueroa High School     1.0
    Ford High School         1.0
    Griffin High School      1.0
    Hernandez High School    1.0
    Holden High School       1.0
    Huang High School        1.0
    Johnson High School      1.0
    Pena High School         1.0
    Rodriguez High School    1.0
    Shelton High School      1.0
    Thomas High School       1.0
    Wilson High School       1.0
    Wright High School       1.0
    dtype: float64
    -----------------------------------------
    schools
    Bailey High School       [3124928]
    Cabrera High School      [1081356]
    Figueroa High School     [1884411]
    Ford High School         [1763916]
    Griffin High School       [917500]
    Hernandez High School    [3022020]
    Holden High School        [248087]
    Huang High School        [1910635]
    Johnson High School      [3094650]
    Pena High School          [585858]
    Rodriguez High School    [2547363]
    Shelton High School      [1056600]
    Thomas High School       [1043130]
    Wilson High School       [1319574]
    Wright High School       [1049400]
    Name: budget, dtype: object
    -----------------------------------------
    schools
    Bailey High School       77.0
    Cabrera High School      83.0
    Figueroa High School     77.0
    Ford High School         77.0
    Griffin High School      83.0
    Hernandez High School    77.0
    Holden High School       84.0
    Huang High School        77.0
    Johnson High School      77.0
    Pena High School         84.0
    Rodriguez High School    77.0
    Shelton High School      83.0
    Thomas High School       83.0
    Wilson High School       83.0
    Wright High School       84.0
    Name: math_score, dtype: float64
    -----------------------------------------
    schools
    Bailey High School       81.0
    Cabrera High School      84.0
    Figueroa High School     81.0
    Ford High School         81.0
    Griffin High School      84.0
    Hernandez High School    81.0
    Holden High School       84.0
    Huang High School        81.0
    Johnson High School      81.0
    Pena High School         84.0
    Rodriguez High School    81.0
    Shelton High School      84.0
    Thomas High School       84.0
    Wilson High School       84.0
    Wright High School       84.0
    Name: reading_score, dtype: float64
    -----------------------------------------
    schools
    Bailey High School       True
    Cabrera High School      True
    Figueroa High School     True
    Ford High School         True
    Griffin High School      True
    Hernandez High School    True
    Holden High School       True
    Huang High School        True
    Johnson High School      True
    Pena High School         True
    Rodriguez High School    True
    Shelton High School      True
    Thomas High School       True
    Wilson High School       True
    Wright High School       True
    dtype: bool
    -----------------------------------------
    schools
    Bailey High School       True
    Cabrera High School      True
    Figueroa High School     True
    Ford High School         True
    Griffin High School      True
    Hernandez High School    True
    Holden High School       True
    Huang High School        True
    Johnson High School      True
    Pena High School         True
    Rodriguez High School    True
    Shelton High School      True
    Thomas High School       True
    Wilson High School       True
    Wright High School       True
    dtype: bool
    -----------------------------------------
    


```python
# School Summary 
```


```python
school_summary_df = merged_school_data.groupby(["schools"])
pd.DataFrame(school_summary_df.size().reset_index(name = "Total Students"))
                                                
#"Total Students", "Total Budget", "Per Student Budget", "Average Math Score",\
#"Average Reading Score", "% Passing Math", "% Passing Reading", "% Overall Passing Rate"])     
     
#school_summary_df = merged_school_data.groupby(["School Type", "Total Students", "Total Budget", "Per Student Budget", "Average Math Score",\
                                                #"Average Reading Score", "% Passing Math", "% Passing Reading", "% Overall Passing Rate"])     

#school_summary_df = merged_school_data.groupby(["School Type":districts, "Total Students":totalstudents, "Total Budget":school_budget, "Per Student Budget":budget, "Average Math Score":average_math_score,\
                                                #"Average Reading Score":average_reading_score, "% Passing Math":average_math_score, "% Passing Reading":average_reading_score, "% Overall Passing Rate":average_reading_score])     
    
#school_summary = [{"School Type":districts, "Total Students":totalstudents, "Total Budget":school_budget, "Per Student Budget":budget, "Average Math Score":average_math_score,\
#                   "Average Reading Score":average_reading_score, "% Passing Math":average_math_score, "% Passing Reading":average_reading_score, "% Overall Passing Rate":average_reading_score}]
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>schools</th>
      <th>Total Students</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bailey High School</td>
      <td>4976</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Cabrera High School</td>
      <td>1858</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Figueroa High School</td>
      <td>2949</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ford High School</td>
      <td>2739</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Griffin High School</td>
      <td>1468</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Hernandez High School</td>
      <td>4635</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Holden High School</td>
      <td>427</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Huang High School</td>
      <td>2917</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Johnson High School</td>
      <td>4761</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Pena High School</td>
      <td>962</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Rodriguez High School</td>
      <td>3999</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Shelton High School</td>
      <td>1761</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Thomas High School</td>
      <td>1635</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Wilson High School</td>
      <td>2283</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Wright High School</td>
      <td>1800</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
# Top performing Schools

# groupby_top_perform = pd.DataFrame(merged_school_data).groupby(['schools']),[{"School":school_name,"Total # total students":total_numb_students,"% Passing Reading":passing_reading, \
                   #"Average Math Score":avg_math_score,"% Passing Math":passing_math,"Overall % Passing":overall_passing}]

groupby_top_perform = pd.DataFrame(merged_school_data).groupby(['schools'])


groupby_top_perform.sum()
#pd.DataFrame(groupby_top_perform)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>size</th>
      <th>budget</th>
      <th>Student ID</th>
      <th>reading_score</th>
      <th>math_score</th>
    </tr>
    <tr>
      <th>schools</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <td>34832</td>
      <td>24760576</td>
      <td>15549641728</td>
      <td>101303896</td>
      <td>403225</td>
      <td>383393</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>11148</td>
      <td>3452164</td>
      <td>2009159448</td>
      <td>31477307</td>
      <td>156027</td>
      <td>154329</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>2949</td>
      <td>8696601</td>
      <td>5557128039</td>
      <td>12949059</td>
      <td>239335</td>
      <td>226223</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>35607</td>
      <td>7502121</td>
      <td>4831365924</td>
      <td>99055935</td>
      <td>221164</td>
      <td>211184</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>5872</td>
      <td>2155024</td>
      <td>1346890000</td>
      <td>19077394</td>
      <td>123043</td>
      <td>122360</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>13905</td>
      <td>21483225</td>
      <td>14007062700</td>
      <td>46090440</td>
      <td>375131</td>
      <td>358238</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <td>3416</td>
      <td>182329</td>
      <td>105933149</td>
      <td>9846620</td>
      <td>35789</td>
      <td>35784</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <td>0</td>
      <td>8508889</td>
      <td>5573322295</td>
      <td>4252986</td>
      <td>236810</td>
      <td>223528</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <td>57132</td>
      <td>22667121</td>
      <td>14733628650</td>
      <td>154327815</td>
      <td>385481</td>
      <td>366942</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <td>8658</td>
      <td>925444</td>
      <td>563595396</td>
      <td>22851829</td>
      <td>80851</td>
      <td>80654</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <td>43989</td>
      <td>15992001</td>
      <td>10186904637</td>
      <td>112111965</td>
      <td>322898</td>
      <td>307294</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>3522</td>
      <td>3101121</td>
      <td>1860672600</td>
      <td>11879706</td>
      <td>147441</td>
      <td>146796</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <td>22890</td>
      <td>2673225</td>
      <td>1705517550</td>
      <td>62705520</td>
      <td>137093</td>
      <td>136389</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <td>11415</td>
      <td>5212089</td>
      <td>3012587442</td>
      <td>33950493</td>
      <td>191748</td>
      <td>190115</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <td>18000</td>
      <td>3240000</td>
      <td>1888920000</td>
      <td>45243900</td>
      <td>151119</td>
      <td>150628</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Create a dataframe for school and grade
```


```python
#school_and_grade_DF = [{"School":school_name,"Grade":grade_level}]
#school_and_grade_DF = pd.DataFrame(merged_school_data).groupby(['schools'], "Districts":districts)


#dist_summary = [{"% Overall Passing Rate":round(overall_passing), "% Passing Reading":round(passing_reading), "% Passing Math":round(passing_math),"Avg Reading Score":avg_reading_score, "Avg Math Score":avg_math_score, "Budget":"$"+ str(budget),\
#                "Total Students":total_numb_students, "Total Schools":total_numb_schools}]


# pd.DataFrame(school_and_grade_DF)
```


```python

```


```python
total_numb_schools_df = df["schools"].count()
total_numb_schools = df["schools"].count()

total_numb_students_df = df2["name"].count()
total_numb_students = df2["name"].count()

avg_math_score = '{0:.2f}'.format(df2["math_score"].mean())
avg_reading_score = '{0:.2f}'.format(df2["reading_score"].mean())

passing_reading = (df2["reading_score"][df2.reading_score > 70].count()/total_numb_students) * 100
'{0:.2f}'.format(passing_reading)

passing_math = df2["math_score"][df2.math_score > 70].count()/total_numb_students * 100
'{0:.2f}'.format(passing_math)

overall_passing = (passing_reading + passing_math)/2
'{0:.2f}'.format(overall_passing)

budget = df["budget"].sum()

per_stud_budget = int(budget/total_numb_students)

```


```python
print("District Summary")
print("---------------------------")
print("District budget: " + "$" + str(budget))
print("Total schools: " + str(int(total_numb_schools)))
print("Total students: " + str(int(total_numb_students)))

print("Average math score: " + str(avg_math_score))
print("Percent passing math: " + str(round(passing_math,2)))

print("Average readging score: " + str(avg_reading_score))
print("Percent passing reading: " + str(round(passing_reading,2)))   

print("Overall Passing Rate: " + str(round(overall_passing,2)))
print("---------------------------")
```

    District Summary
    ---------------------------
    District budget: $24649428
    Total schools: 15
    Total students: 39170
    Average math score: 78.99
    Percent passing math: 72.39
    Average readging score: 81.88
    Percent passing reading: 82.97
    Overall Passing Rate: 77.68
    ---------------------------
    


```python
dist_summary = [{"% Overall Passing Rate":round(overall_passing), "% Passing Reading":round(passing_reading), "% Passing Math":round(passing_math),"Avg Reading Score":avg_reading_score, "Avg Math Score":avg_math_score, "Budget":"$"+ str(budget),\
                "Total Students":total_numb_students, "Total Schools":total_numb_schools}]
    
pd.DataFrame(dist_summary)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>% Overall Passing Rate</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>Budget</th>
      <th>Total Schools</th>
      <th>Total Students</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>78.0</td>
      <td>72.0</td>
      <td>83.0</td>
      <td>78.99</td>
      <td>81.88</td>
      <td>$24649428</td>
      <td>15</td>
      <td>39170</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Top Performing Schools (By Passing Rate)
# Create a table that highlights the top 5 performing schools based on Overall Passing Rate.
# Include all of the same metrics as above.

```


```python

```


```python
# Top Performing Schools (By Passing Rate)
# Create a table that highlights the top 5 performing schools based on Overall Passing Rate.
# Include all of the same metrics as above.

top_perform_DF = [{"School":school_name,"Total # students":total_numb_students,"% Passing Reading":passing_reading, \
                   "Average Math Score":avg_math_score,"% Passing Math":passing_math,"Overall % Passing":overall_passing}]

groupby_top_perform = pd.DataFrame(school_name).groupby(['schools']),[{"School":school_name,"Total # students":total_numb_students,"% Passing Reading":passing_reading, \
                   "Average Math Score":avg_math_score,"% Passing Math":passing_math,"Overall % Passing":round(overall_passing)}]

```


```python
# pd.DataFrame(groupby_top_perform)
```


```python
# Create a dataframe for % passing reading
passing_reading_DF = pd.DataFrame(top_perform_DF, columns = ["passing_reading"])

pd.DataFrame(passing_reading_DF)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>passing_reading</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Create a dataframe for % passing math
passing_math_DF = pd.DataFrame(top_perform_DF, columns = ["passing_math"])

pd.DataFrame(passing_math_DF)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>passing_math</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
# Math Scores by Grade
# Create a table that lists the average Math Score for students of each grade level (9th, 10th, 11th, 12th) at each school.

```


```python

```


```python
# Reading Scores by Grade

# Create a table that lists the average Reading Score for students of each grade level (9th, 10th, 11th, 12th) at each school

```


```python

```


```python
# Scores by School Spending

#Create a table that breaks down school performances based on average Spending Ranges (Per Student).
# Use 4 reasonable bins to group school spending. Include in the table each of the following:

# Average Math Score
# Average Reading Score
# % Passing Math
# % Passing Reading
# Overall Passing Rate (Average of the above two)

```


```python

```


```python
# Scores by School Size

# Repeat the above breakdown, but this time group schools based on a reasonable approximation of
# school size (Small, Medium, Large)
# small = 0 - 425, medium = 426 - 999, large = 1000 - 2999, xl = 3000 - 4800

#bins = [0, 425, 999, 1000, 2999, 3000]

# schools_size = ['Small', 'Medium', 'Large', 'Xlarge']
```


```python

```


```python
# Scores by School Type

# Repeat the above breakdown, but this time group schools based on school type (Charter vs. District).

```


```python

```


```python
# Create dataframe
raw_data = {'regiment': ['Nighthawks', 'Nighthawks', 'Nighthawks', 'Nighthawks', 'Dragoons', 'Dragoons', 'Dragoons', 'Dragoons', 'Scouts', 'Scouts', 'Scouts', 'Scouts'], 
        'company': ['1st', '1st', '2nd', '2nd', '1st', '1st', '2nd', '2nd','1st', '1st', '2nd', '2nd'], 
        'name': ['Miller', 'Jacobson', 'Ali', 'Milner', 'Cooze', 'Jacon', 'Ryaner', 'Sone', 'Sloan', 'Piger', 'Riani', 'Ali'], 
        'preTestScore': [4, 24, 31, 2, 3, 4, 24, 31, 2, 3, 2, 3],
       'postTestScore': [25, 94, 57, 62, 70, 25, 94, 57, 62, 70, 62, 70]}

df = pd.DataFrame(raw_data, columns = ['regiment', 'company', 'name', 'preTestScore', 'postTestScore'])

#df

# Create a groupby variable that groups preTestScores by regiment
groupby_regiment = df['preTestScore'].groupby(df['regiment'])
groupby_regiment

# Group the dataframe by regiment, and for each regiment,
for name, group in df.groupby('regiment'): 
    # print the name of the regiment
    print(name)
    # print the data of that regiment
    print(group)

#groupby_top_perform = df[top_perform_DF].groupby(school_name)
#groupby_top_perform
```

    Dragoons
       regiment company    name  preTestScore  postTestScore
    4  Dragoons     1st   Cooze             3             70
    5  Dragoons     1st   Jacon             4             25
    6  Dragoons     2nd  Ryaner            24             94
    7  Dragoons     2nd    Sone            31             57
    Nighthawks
         regiment company      name  preTestScore  postTestScore
    0  Nighthawks     1st    Miller             4             25
    1  Nighthawks     1st  Jacobson            24             94
    2  Nighthawks     2nd       Ali            31             57
    3  Nighthawks     2nd    Milner             2             62
    Scouts
       regiment company   name  preTestScore  postTestScore
    8    Scouts     1st  Sloan             2             62
    9    Scouts     1st  Piger             3             70
    10   Scouts     2nd  Riani             2             62
    11   Scouts     2nd    Ali             3             70
    


```python

```


```python

```


```python

```