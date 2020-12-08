# DC 25th Nov Post-Mortem Minutes

## Zoom

### Pros

- Structured Orientation

    A structured orientation in how Carpentries utilises zoom appeared to reap some benefit in way of engagement.
    A formal _Zoom Orientation for Carpentries_ may be beneficial for future workshops.

### Cons

  - Zoom Censoring Zoom

    while screen sharing zoom is now censoring out its overlays / panes which blocks material on screen, be wary

## Excel

### Pros

- Relaxed Style
- Showing Libre Office in addition to Excel

    There is definitely a benefit in demonstrating across multiple spreadsheet applications.

### Cons

- More exercises

    Lesson could do with more hands-on exercises, but this is reliant on the

    - A clean-up of the lessons
        - removing typos
        - removing references to other lessons
    - Dirtying up the data set in a way that allows for better instruction

- Allowing different versions of spreadsheet apps, let alone different apps allows for far too much variation.

- Technical Issue

    There were some unavoidable and some avoidable technical issues. In sum, try out the system you are using ***before*** the workshop. Do not tempt fate by changing machines just beforehand.

***

## OpenRefine


### Pros

- Delivered perfectly and effortlessly

### Cons

- Add advanced GREL

    Lessons could do with a couple of [GREL examples](https://guides.library.illinois.edu/openrefine/grel)

- Typos in material

    A general clean-up of the lesson material, removing typos etc...


- Installation hitches

    There were a few hitches during installation

    **Common Problems**:

        - File extraction / unzipping (windows specific)
        - macOS security settings (GateKeeper)

    Perhaps asking learner to annotate which OS they use in their Zoom name or on the participants list of the etherpad would at least allow helpers to narrow down common issues. A troubleshooting guide / FAQ for learners would not hurt. A list of common problems would also be useful for helpers.

***

## Python

### Pros

- NLP example

    Some kind of text analysis / Natural Languag Processing example in the official lesson would be beneficial. The NLP example appeared to go down well.

### Cons

- lessons disorganised / wrong order

    Lesson material jumps focussed too much without any narrative through-line or justification

- add something from text analysis carp (in incubator)

- commenting code as you go

    For the ease of comprehension and reading, annotating code (especially more complex functions) would be beneficial.

***

## SQL

### Pros


### Cons

- Scheduling and Lack of Attendance

    SQL suffered from a lack of attendance. It would be useful to change-up the schedule for the next carpentry to see if this improves. Ideally SQL should be in the morning. For a 3 day lesson plan like this, it would possibly make more sense to have a running order of

    - Spreadsheets Day 1 AM
    - Open Refine Day 1 PM
    - SQL Day 2 AM
    - Python Day 2PM, Day 3 ALL


- More Context

    Lesson plan could benefit from giving SQL more context, providing use-cases and examples of when it is beneficial

    To help give the lesson more context ther should be

    - A stronger narrative through-line
    - A data set with from a relevant project or use-case in mind, potentially [Gapminder](http://www.gapminder.org)

- Data set disorganised

    Data set is disorganised in a way that is not on purpose. Particularly with the `.db` file there are view that should be purged to avoid confusion and potential errors. (Flag an Issue)
