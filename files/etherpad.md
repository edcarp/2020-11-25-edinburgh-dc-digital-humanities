Welcome to The Carpentries Etherpad!



This pad is synchronized as you type, so that everyone viewing this page
sees the same text. This allows you to collaborate seamlessly on
documents.



Use of this service is restricted to members of The Carpentries
community; this is not for general purpose use (for that, try
<https://etherpad.wikimedia.org)>.



Users are expected to follow our code of conduct:
<https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html>



All content is publicly available under the Creative Commons Attribution
License: <https://creativecommons.org/licenses/by/4.0/>



 
-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--\
\

# Workshop Webpage



<https://edcarp.github.io/2020-11-25-edinburgh-dc-digital-humanities/>




# Code of Conduct



<https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html>




# Post-workshop survey



[[https://forms.office.com/Pages/ResponsePage.aspx?id=sAafLmkWiUWHiRCgaTTcYbJksOTKjv5Nsdenk5ny0NNUQVZTUk1MS0c3T0JUWENPMlBPMTJLQjJSTC4u]{.underline}](https://forms.office.com/Pages/ResponsePage.aspx?id=sAafLmkWiUWHiRCgaTTcYbJksOTKjv5Nsdenk5ny0NNUQVZTUk1MS0c3T0JUWENPMlBPMTJLQjJSTC4u)












### Helpful Zoom Shortcuts





| Function                        | mac   | windows     |
| ------------------------------- | ----- | ----------- |
| Mute/unmute audio               | ⌘+⇧+A | Alt+A       |
| Start/stop video                | ⌘+⇧+V | Alt+V       |
| Start/stop screen share         | ⌘+⇧+S | Alt+Shift+S |
| Display/hide participants panel | ⌘+U   | Alt+U       |
| Show/hide in-meeting chat panel | ⌘+⇧+H | Alt+H       |
| Raise hand/lower hand           | ⌥+Y   | Alt+Y       |
| Enter or exit full screen       | ⌘+⇧+F | Alt+F       |








## Day 1






### Data



<https://github.com/edcarp/2020-11-25-edinburgh-dc-digital-humanities/releases/download/0.1.0/data.zip>




### Spreadsheets






## Comments on the Data



Mentions  of London 

in column K (Places) need reconciled to 1  entity (London, Londini, I
'm
in London) 

Untidy data, eg Lots of
"London?
"

Blank fields under Author

The fields are not labelled

Bit of messy data. Count of places probs should have been a column with
entries. Semicolon at Column D.

Column D seems to have two things slpit by semi-colon

Places, random spacing and London appears as
'Londini
' in one entry -
rogue and might create havoc

Weird characters in title field

Mentions of Antwerp in Places (column K) are messy - 5 different
variations at least.

My column F has been split further due to commas (libreoffice)




## Dates q



I can\'t seem to change the \'what I typed\' - they revert back, is this
just me?\
It hates commas and \'th\'\
I typed 22 11 1992 (with spaces) and it came up as \#VALUE!\
When I try to type in \'Mar-21\' then it turns into \'21/3/2020\', not
\'3/2021\'. My excel auto-corrected me into DMY whenever I typed a
XX-XX\
Doesn\'t recognise US format e.g. 11/30/2020 or 20201130\
It doesn\'t recognise it at all as a date if I type \'Jan-25\'
(libreoffice)\
\'Nov 30\' is interpreted as 1930\
\'Nov 30\' in my excel was corrected as \'30-Nov\' then into 30/11/2020\
\
\

## Feedback

\

### Pro

\
Easy to understand and implement material. I am not sure if I will need
to use Openrefine though as the data I work on are more tidy!\
Great tool, never used it before and the workshop was thorough enough
but also easy enough to follow to start using it myself. I previously
used R to clean data in Excel sheets and I find OpenRefine much more
user friendly and accessible for the main first steps. Also super
helpful that you can easily recreate your commands later.\
Thanks for great introduction, I will definitely be using OpenRefine\
\

### Con

\
Not really a \"Con\" just an idea, could you make commands and/or steps
to make certain changes available in a summary document? I kept writing
everything down in a separate Word document and in doing so sometimes
missed a part of the following instructions.\
\

### OpenRefine

\
\

#### Excercise 1

\
\
\

#### GREL

\

1. clean the column values\
   Edit cell \
   value.replace( \"what you want to change\", \"what you want\")\
2. do splitting of values\
   Facet/costum text facet \
   value.split (\"list delimiter\")\
   \

```json
{
  "op": "core/mass-edit",
  "engineConfig": {
    "facets": [],
    "mode": "row-based"
  },
  "columnName": "Place",
  "expression": "value",
  "edits": [{
    "from": [
      "London",
      "London?"
    ],
    "fromBlank": false,
    "fromError": false,
    "to": "London"
  }],
  "description": "Mass edit cells in column Place"
}, {
  "op": "core/mass-edit",
  "engineConfig": {
    "facets": [],
    "mode": "row-based"
  },
  "columnName": "Place",
  "expression": "value",
  "edits": [{
    "from": [
      "London",
      "Londini"
    ],
    "fromBlank": false,
    "fromError": false,
    "to": "London"
  }],
  "description": "Mass edit cells in column Place"
}, {
  "op": "core/mass-edit",
  "engineConfig": {
    "facets": [],
    "mode": "row-based"
  },
  "columnName": "Place",
  "expression": "value",
  "edits": [{
    "from": [
      "Antverpi",
      "Antwerp"
    ],
    "fromBlank": false,
    "fromError": false,
    "to": "Antverpi"
  }],
  "description": "Mass edit cells in column Place"
}, {
  "op": "core/column-split",
  "engineConfig": {
    "facets": [],
    "mode": "row-based"
  },
  "columnName": "STC",
  "guessCellType": true,
  "removeOriginalColumn": false,
  "mode": "separator",
  "separator": ";",
  "regex": false,
  "maxColumns": 0,
  "description": "Split column STC by separator"
}, {
  "op": "core/text-transform",
  "engineConfig": {
    "facets": [],
    "mode": "row-based"
  },
  "columnName": "STC 2",
  "expression": "value.trim()",
  "onError": "keep-original",
  "repeat": false,
  "repeatCount": 10,
  "description": "Text transform on cells in column STC 2 using expression value.trim()"
}, {
  "op": "core/column-split",
  "engineConfig": {
    "facets": [],
    "mode": "row-based"
  },
  "columnName": "STC 2",
  "guessCellType": false,
  "removeOriginalColumn": false,
  "mode": "lengths",
  "fieldLengths": [
    4,
    4,
    4
  ],
  "description": "Split column STC 2 by field lengths"
}, {
  "op": "core/text-transform",
  "engineConfig": {
    "facets": [],
    "mode": "row-based"
  },
  "columnName": "STC 2 2",
  "expression": "value.trim()",
  "onError": "keep-original",
  "repeat": false,
  "repeatCount": 10,
  "description": "Text transform on cells in column STC 2 2 using expression value.trim()"
}, {
  "op": "core/text-transform",
  "engineConfig": {
    "facets": [],
    "mode": "row-based"
  },
  "columnName": "Terms",
  "expression": "grel:value.replace(\"--\",\";\")",
  "onError": "keep-original",
  "repeat": false,
  "repeatCount": 10,
  "description": "Text transform on cells in column Terms using expression grel:value.replace(\"--\",\";\")"
}, {
  "op": "core/text-transform",
  "engineConfig": {
    "facets": [],
    "mode": "row-based"
  },
  "columnName": "Terms",
  "expression": "grel:value.replace(\" ; \", \";\").replace(\"(\", \"\").replace(\")\", \"\").replace(\"[\", \"\").replace(\"] \"\").replace(\".\", \"\")",
"onError": "keep-original",
"repeat": false,
"repeatCount": 10,
"description": "Text transform on cells in column Terms using expression grel:value.replace(\" ; \", \";\").replace(\"(\"\").replace(\")\", \"\").replace(\"[\", \"\").replace(\"]\", \"\").replace(\".\", \"\")"
}, {
  "op": "core/text-transform",
  "engineConfig": {
    "facets": [],
    "mode": "row-based"
  },
  "columnName": "Date",
  "expression": "value.toNumber()",
  "onError": "keep-original",
  "repeat": false,
  "repeatCount": 10,
  "description": "Text transform on cells in column Date using expression value.toNumber()"
}, {
  "op": "core/text-transform",
  "engineConfig": {
    "facets": [{
      "type": "range",
      "name": "Date",
      "expression": "value",
      "columnName": "Date",
      "from": 1539,
      "to": 1610,
      "selectNumeric": true,
      "selectNonNumeric": true,
      "selectBlank": true,
      "selectError": true
    }],
    "mode": "row-based"
  },
  "columnName": "STC 2 3",
  "expression": "value.toNumber()",
  "onError": "keep-original",
  "repeat": false,
  "repeatCount": 10,
  "description": "Text transform on cells in column STC 2 3 using expression value.toNumber()"
}, {
  "op": "core/text-transform",
  "engineConfig": {
    "facets": [{
      "type": "range",
      "name": "Date",
      "expression": "value",
      "columnName": "Date",
      "from": 1539,
      "to": 1610,
      "selectNumeric": true,
      "selectNonNumeric": true,
      "selectBlank": true,
      "selectError": true
    }],
    "mode": "row-based"
  },
  "columnName": "Page Count",
  "expression": "value.toNumber()",
  "onError": "keep-original",
  "repeat": false,
  "repeatCount": 10,
  "description": "Text transform on cells in column Page Count using expression value.toNumber()"
}, {
  "op": "core/text-transform",
  "engineConfig": {
    "facets": [{
      "type": "range",
      "name": "Date",
      "expression": "value",
      "columnName": "Date",
      "from": 1539,
      "to": 1610,
      "selectNumeric": true,
      "selectNonNumeric": true,
      "selectBlank": true,
      "selectError": true
    }],
    "mode": "row-based"
  },
  "columnName": "EEBO",
  "expression": "value.toNumber()",
  "onError": "keep-original",
  "repeat": false,
  "repeatCount": 10,
  "description": "Text transform on cells in column EEBO using expression value.toNumber()"
}]
```
   \
   \
   \

## Feedback

\

### Pro

\
Very clear case for using Open Refine for data cleaning, simplifying
operations.\
Concur! I\'m going to forget it though (GREL expressions in particular)\
\

### Con

\
\
Can you consider creating an illustrated pdf guide on the steps gone
through today and/or short 2-3 min screencapture video tutorials? Think
these would be really useful as a refresher or for documentation
purposes to help newbies. I concur!\
\
1 OpenRefine tutorial is here:
<https://www.youtube.com/watch?v=wfS1qTKFQoI>\
\

## Day 2

\

### Python

\
\

### Noteable

\
<https://noteable.edina.ac.uk/login/>\
\

### Jupyter Notebook Shortcuts

\
\
| Function                   | mac | windows     |
| -------------------------- | --- | ----------- |
| Run Cells                  | ⌘+⏎ | CTRL+ENTER  |
| Run Cells and Select Below | ⇧+⏎ | SHIFT+ENTER |
| Run Cells and Insert Below | ⌥+⏎ | ALT+ENTER   |
| Toggle Line Numbers        | ⇧+L | SHIFT+L     |
| New Cell Above             | a   | a           |
| New Cell Below             | b   | b           |
| Delete Cell                | d d | d d         |
\

### Lesson 1

\
\

### Lists

\
`beatles = ['john', 'paul', 'george', 'ringo']`\
\

#### List slicing

\
`list[ start_index : end_index : jump ]`\
\
Each value is optional; if excluded, Python uses a default value.\
\
\|         Default       \|                                             
Implication                                              \|\
\| \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--  \|
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- 
\|\
\|         0    (first)    \|                           start_index is
included in output                             \|\
\|         -1    (last)    \|                         end_index is not
included in output                          \|\
\|          1   (each)    \| jump is interpreted \'every \_\_\_\'
(second, third, fourth, et cetera) \|\
\
q)\
\
beatles\[1\]\
\

1.  \'john\'
2.  \'paul\'\*\*\*\*\*\*\*\*
3.  \'george
4.  \'ringo\'
5.  Error\*\*

\
Q2) beatles\[4\]\
\

1.  \'john\'
2.  \'Paul\'
3.  \'george
4.  \'ringo\'
5.  Error\*\*\*\*\*\*\*\*\*\*

\
Q3) beatles\[1:3\]\
\

1.  \'john\', \'paul\'
2.  \'paul\',\'george\'\*\*\*\*\*\*\*\*
3.  \'paul\',\'george,\',\'ringo\'
4.  \'john\',\'paul\',\'george,\',\'ringo\'
5.  Error

\
\
Q4) beatles\[-1\]\
\

1.  \'john\'\*\*\*
2.  \'paul\'\*
3.  \'george\'\*
4.  \'ringo\'\*\*\*\*\*
5.  Error\*\*\*

\
Q5) beatles\[-5\]\
\

1.  \'john\'\*
2.  \'paul\' \*
3.  \'george\'
4.  \'ringo\'\*\*\*
5.  Error\*\*\*\*\*\*\*

\
\
\

### Dictionaries

\
`beatles = {'john': 'guitar', 'paul': 'bass', 'george': 'guitar', 'ringo': 'drums'}`\
\
\

### for loops

\
General syntax:\
`for item in collection:`\

- `do things`

### Looping over the Beatles dictionary

\
```py
beatles = {'john': 'guitar', 'paul': 'bass', 'george': 'guitar', 'ringo': 'drums'}
for beatle, instrument in beatles.items():
    print(beatle, 'plays', instrument)`
```
\
\
```py
Places = tcp_df['Place']
Num_of_Places = pd.unique(Places)
len(Num_of_Places)
```
\
\
\

### Quantifying Data:

\

#### Notes on data description:

\
\
\
Q) Create a list of unique locations found in the index data. Call it
places. How many unique location are there in the data? \
\
\

1.  998
2.  11
3.  14
4.  90\*\*\*\*\*\*\*\*

\
Bonus: More readable suggestions\
could you make an variable for \'Place\'?\
pages seem to be split by . such as 146.98 ??? can you have 0.8 of a
page?\
all of the unnamed: 11 column are NaN expect one being 0.0?\
what does +07 mean?!\
The output for EEBO is not helpful.\
so the max page is 2072? not 998?\
\
Q) how many \'Unknown\' Authors are there\
\

1.  126
2.  30\*\*\*\*
3.  14
4.  0

\
\

#### Sermons

```py
is_a_sermon = tcp_df['Terms'].str.contains('sermon', na = False)
tcp_df[is_a_sermon]
pamphlets = tcp_df['Page Count'] < 10
missing_terms = tcp_df["Terms"].isna()
tcp_df[missing_terms]
author_is_unknown = tcp_df['Author'].isna()
tcp_df[author_is_unknown].count()
```

## Workflow and Automation

\
\
Alex is analysing Virginia Woolf\'s To the Lighthouse. They wish to
extract all mentions of the lighthouse and surrounding context using
python\
\
How many problems?\
sorry what do you mean by a problem? \
do you mean all mentions in the entire spreadsheet?\
Does one \'mention\' here means a sentence?\
\

1. \*\*\
   5)\*\*\*\*\*\*\
   15)\*\*\
   25)\
   \

### Sentiment Analysis Example

`import urllib.request, urllib.error, urllib.parse, pprint`
`url = "http://gutenberg.net.au/ebooks01/0100101.txt" # a website`
`response = urllib.request.urlopen(url) # this fetches information from a webpage`
`text = response.read().decode('ASCII') # this processes the response a bit, so it is`
`# text, rather than binary format`
`text[0:100] # to see a small portion`
`text.split()[0:10] # splits the text on whitespace characters`
`words = text.split() # create a list of all words`
`# prints each word if the word is Lighthouse`
`for word in words:`
`if word == 'Lighthouse':`
  `print(word)`
`# prints the word and its index for each occurrence of Lighthouse`
`for index, word in enumerate(words):`
- `if word == 'Lighthouse':`
  - `print(index, word)`
`# A different way to use this information`
`for index, word in enumerate(words):`
- `if word == 'Lighthouse':`
  - `print(words[index])`
`# Grabbing some context around each occurrence of Lighthouse`
`for index, word in enumerate(words):`
`if word == 'Lighthouse':`
    `print(words[index - 1:index + 2])`=
`# Collecting the bits of text`
`lighthouse = []`
`for index, word in enumerate(words):`
`if word == 'Lighthouse':`
    `lighthouse.append(words[index - 4:index + 5])`

### Normalising text

\
`"Hello".lower()`\
`"Hello".upper()`\
\
`# Collecting the bits of text (gets both capitalised and non-capitalised occurrences)`\
`lighthouse = []`\
\
`for index, word in enumerate(words):`\

- `if word.lower() == 'lighthouse':`
  - `lighthouse.append(words[index - 4:index + 5])`

\
`for phrase in lighthouse:`\

- `print(phrase)`

\
\

### Grand Solution w/ Pretty Printing

\
```py
import urllib.request, urllib.error, urllib.parse, pprint

url = "http://gutenberg.net.au/ebooks01/0100101.txt"
response = urllib.request.urlopen(url)
text = response.read()
words = [word.decode('ASCII') for word in text.split()]


lighthouse = []

for index, word in enumerate(words):
    if 'lighthouse' in word.lower():
        if 'Virginia' not in words[index - 3:index + 4]:
            lighthouse.append(" ".join(words[index - 3:index + 4]))

max_characters  = max([s.find('Lighthouse') for s in lighthouse])

for phrase in lighthouse:
    pad = max_characters - phrase.find('Lighthouse')
    print(" " * pad, phrase)

```
\

## Feedback

\

\

### Pro

\
Really good examples, nicely explained  - just needs comments explaining
each step/what leach line is doing to digest the syntax a bit more.
Think illustrated pdf/slides/videos may help during and definitely post
session so attendees can follow/catchup at own pace  \
Great first day (of Python) with an initial explanation of
functions/commands and then going on to a more complex problem to solve.
I had an introduction to Python before and worked with R a bit. It was
easy to follow and I leart a lot.\
I wish my undergrad Computing course was as good as this. Great material
and great teaching.\
\

### Con

\
Not really a con. At the beginning, there are no codes to refer to
(directly copy and paste), but in the later part, one helper solved this
problem! \
Just a suggestion when asking how many problems, ask how many steps
instead?\
\

## Day 3

\

### Python

\
\
`def function():`\

- `yada yada yada`

`def function():`\

- `taradidledidleda`

\

### Noteable

\
<https://noteable.edina.ac.uk/login/>\
\

### Jupyter Notebook Shortcuts

\
\
| Function                   | mac | windows     |
| -------------------------- | --- | ----------- |
| Run Cells                  | ⌘+⏎ | CTRL+ENTER  |
| Run Cells and Select Below | ⇧+⏎ | SHIFT+ENTER |
| Run Cells and Insert Below | ⌥+⏎ | ALT+ENTER   |
| Toggle Line Numbers        | ⇧+L | SHIFT+L     |
| New Cell Above             | a   | a           |
| New Cell Below             | b   | b           |
| Delete Cell                | d d | d d         |
\
\

### Bokeh



<https://docs.bokeh.org/en/latest/docs/reference/plotting.html?highlight=y_axis_label#bokeh.plotting.figure>
```py
from bokeh.plotting import figure, output_file, show, save
from bokeh.io import output_notebook
import pandas as pd
output_notebook()
# create a space to hold our plots
line_plot = figure(plot_width 600, plot_height = 400)
# create some data for the points
x = [0, 1, 2, 3]
y1 = [101, 60, 80, 10]
y2 = [50, 43, 72, 1]
# add lines to our line_plot figure object
line_plot.line(x, y1)
line_plot.line(x, y2)
# add circular emphasis points on the points from y1`
line_plot.circle(x, y1) # tells the notebook to display the line_plot figure `show(line_plot)
```

### Generating some data automatically

\
``\
\# range will produce a list of numbers, but it doesn\'t just create it\
\# instead, it returns the next number in the range when you need it,
saving memory for large ranges\
`range(10)`\
\
`# Remember this does not include the end number:`\
`for number in range(10):`\

- `print(number)`

``\
`for number in range(42, 51):`\

- `print(number)`

\
`# create a new figure for our new plot`\
`big_plot = figure(plot_width = 400, plot_height = 400)`\
`` \ `# create some data `\ `x = range(0, 100) `\ `y = x `\ ``\
`# creating more data, the -1 tells it the steps should be decreasing`\
`# the default is for it to increase`\
`y2 = range(100, 0, -1)`\
`` \ `# add the lines to the new figure `\ `big_plot.line(x, y) `\ `big_plot.circle(x, y2) `\ ``\
`# show the new figure`\
`show(big_plot)`\
`\`\
`\`\
`import pandas as pd`\
`from bokeh.plotting import save`\
`# this line will not work if you are not in the same place as the`\
`# "eebo.csv" file from yesterday`\
`data_frame = pd.read-csv("eebo.csv")`\
\
`# create some variables with interesting data`\
`y = data_frame['Page Count']`\
`# x = range(0, len(y))`\
`x = data_frame['Date']`\
\
`# create a figure object to hold our new plot`\
`page_plot = figure(plot_height = 400, plot_width = 400)`\
\
`# add a line with circular dots to our new figure`\
`page_plot.circle(x, y)`\
`` \ `# show the new figure `\ `show(page_plot) `\ ``\
`` \ `output_file("date-page-scatter.html") `\ `save(page_plot)`\ ``\
``\

### Going back to the first example

\
`# We can change some formatting things to make code easier to read`\
\
`from bokeh.plotting import figure, output_file, show save`\
`from bokeh.io import output_notebook`\
`import pandas as pd`\
`output_notebook()`\
``\
`# adds functionality so you can 'inspect' individual points in the finished plot`\
`TOOLTIPS = [`\

- - `("index", "$index"),`
  - `("(x, y)", "($x, $y)"`

`]`\
\
`# create a space to hold our plots`\
`# this function call is now split over several lines, making it easier to read`\
`line_plot = figure(plot_width 600,`\

- - - - - - - `plot_height = 400,`
            - `title = "Two Lines",`
            - `x_axis_label = "No. Cats in Scotland",`
            - `y_axis_label = "Avg Price of Cheese (£)"`
            - tooltips = TOOLTIPS)

`` \ `# create some data for the points `\ `x = [0, 1, 2, 3] `\ `y1 = [101, 60, 80, 10] `\ `y2 = [50, 43, 72, 1] `\ ``\
`# add lines to our line_plot figure object`\
`line_plot.line(x, y1, line_color = "orange", legend_label = "Croatia")`\
`line_plot.line(x, y2, legend_label = "Germany")`\
`` \ `# add circular emphasis points on the points from y1 `\ `line_plot.circle(x, y1, line_color = "red") `\ \ `# tells the notebook to display the line_plot figure `\ `show(line_plot) `\ ``\
``\

### Plotting a sine wave

\
from math import sin \
\
`# create a figure to hold our sine plot`\
`plot_sine = figure(plot_width = 400, plot_height = 400)`\
`# doesn't work, yet`\
`sin(1)`\
``\
\# create some data and an empty list to store sine values \
`x = range(100)`\
`sine_wave = []`\
\
`# add sine values to our empty list, one-at-a-time`\
`for number in x:`\

- `sine_wave.append(sin(number / 25))`

`# plot the sine wave with circles, and display it`\
`plot_sine.circle(x, sine_wave)`\
`show(plot_sine)`\
\
`***********************************************************`\
`# new version, written as a function`\
  \
`from math import sin`\
`` \ `# define a function to plot sine waves `\ `def plot_sine_wave(freq, sample_rate):`\ ``\

- `plot_sine = figure(plot_width = 400, plot_height = 400)`
- `x = range(sample_rate)`
- `sine_wave = []`
- `two_pi = 2 * 3.141592653`
- ``
- `for number in x:`
  - `sine_wave.append(sin(two_pi * freq * number / sample_rate))`
  - ``
- `plot-sine.circle(x, sine_wave)`
- `show(plot_sine)`

``\
\
\# plot some sine waves using our function \
`plot_sine_wave(3, 100)`\
\
\

### Additional - Markdown

\
\
<https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet>\
`\`\
`\ \`\
\
\

## Feedback

\

### Pro

\
really well explained why we would want to use certain libraries and
demonstrating the power of the tools e.g. Bokeh. Clear that Matthew is
curious about all aspects of Python and that really translated!\
Extremely helpful day 3, both creating figures with Python and looking
at spreadsheets with SQL. Both was new to me and I now feel confident
using both (on a basic level) and exploring more. It was great to get
links to cheat sheets for looking up things in the future and training
more.\
\

### Con

\
bit quick occassionally but further explanations made this manageable\
\

### SQLite

\
Data:
<https://github.com/edcarp/2020-11-25-edinburgh-dc-digital-humanities/releases/download/0.1.0/data.zip>\
DB Browser: <https://sqlitebrowser.org/dl/>\
\
Execute SQL query: \

- Windows/ Linux: Ctrl + Enter
- Mac: Cmd + Enter

or press F5 on any of these OSs\
\
SELECT Title FROM eebo;\
\
SELECT \* FROM eebo LIMIT 4;\
\
SELECT DISTINCT Date FROM eebo;\
\
SELECT DISTINCT Date, Title FROM eebo;\
\
SELECT PageCount, PageCount/10 FROM eebo;\
\
SELECT Date, PageCount, ROUND(PageCount/100., 1) FROM eebo;    (notice
the dot after \'10\', expect SQLite to return with a floating point
result)\
\
\-- This is a comment line in SQL                       (use two dashes,
sort of equivalent to the hash we\'ve used in Python)\
\
Might be a bit more visually appealing writing the SQL query in the
following format:\
\
SELECT Date,  Status\
FROM eebo\
WHERE Date \> 1600;   \-- Before that you may reset \'Date\' type to
INTEGER             WHERE clause or keyword is the basic SQL syntax to
filter on rows\
\
\
SELECT Status\
FROM eebo\
WHERE Status =\'Free\';\
\
\
SELECT Date\
FROM eebo\
WHERE (Date \> = 1640) AND (Status = \'Free\');                \-- You
may consider using brackets for better readibility\
\
\
SELECT PageCount, Date, TCP, Title\
FROM eebo\
WHERE PageCount \> 75\
ORDER BY PageCount;                     \-- default ordering is
ascending, if otherwise, use the \'DESC\' keyword\
\
\
\
SELECT PageCount, Date, TCP, Title\
FROM eebo\
WHERE PageCount \> 75\
ORDER BY PageCount DESC , Date DESC;                     \-- default
ordering is ascending, if otherwise, use the \'DESC\' keyword\
\
\
SELECT Date, Author\
FROM eebo\
ORDER BY Date ASC , Author ASC;                     \-- default ordering
is ascending, if otherwise, use the\
\
\
SELECT Date\
FROM eebo\
WHERE Date \> 1550\
ORDER BY Date;\
\
\
\
**Aggregating functions**\
\
\
SELECT COUNT(\*), COUNT(Author)\
FROM authors;\
\
\
SELECT SUM(PageCount), \
              ROUND(AVG(PageCount), 2),\
              MIN(PageCount),\
              MAX(PageCount)\
FROM eebo;\
\
\
\
SELECT Date,\
              COUNT(\*)\
FROM eebo\
GROUP BY Date;\
\
\
SELECT Date, PageCount\
FROM eebo\
WHERE Date \>= 1600     \--an ad hoc WHERE clause added to illustrate
the difference; WHERE is to filter ungrouped records in the data table\
GROUP BY Date\
HAVING SUM(PageCount) \> 10;                          \-- \'HAVING\'
clause used to filter groups\
\
\
\

## Feedback

\

### Pro

\
\

### Con

\
