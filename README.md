# hello-quarto-demo

Repository for the demos in the "Hello, Quarto!" talk

## Software

-   RStudio:

    -   Version: Current release -- RStudio 2022.07.0+548 "Spotted Wakerobin" Release (34ea3031089fa4e38738a9256d6fa6d70629c822, 2022-07-06) for macOS Mozilla/5.0 (Macintosh; Intel Mac OS X 12_4\_0) AppleWebKit/537.36 (KHTML, like Gecko) QtWebEngine/5.12.10 Chrome/69.0.3497.128 Safari/537.36
    -   Theme: rsthemes::a11y-light

-   R 4.2.1

-   MousePose - Mouse Clicks on

-   Desktop - Background single color Quarto blue (#75aadb)

-   Quarto - 1.0.24

## Steps

### Demo 1 - Share / flexibility in formats:

#### Part 1

-   Open hello.Rmd with source editor -\> knit

-   Change to visual editor -\> knit

-   Close file -\> change file type to .qmd -\> open (make sure visual editor) and render

-   Change `output: html_document` to `format: html` -\> render

-   Click on Render on save

-   Change to `format: pdf` -\> save to render -\> then change back to `format: html`

-   Add chunk option `echo: false` to the first chunk using tab completion -\> save to render

-   Delete `echo: false` from first chunk -\> turn off echo from document YAML -- type `execute:`, return, `e`, tab completion to choose `echo` and `false`.

    ``` yaml
    execute:
        echo: false
    ```

#### Part 2

-   Add alt text to figure in second code chunk -\> save to render

    ``` r
    #| fig-alt: |
    #|   Scatterplot of bill length vs. flipper length for three 
    #|   species of penguins. The relationship is positive and 
    #|   moderately strong. The three species are identified on 
    #|   the plot with points with different colors and shapes, 
    #|   revealing three clusters.
    ```


#### Part 3 - ??? **Julie note: time-wise I wonder if this could move to Demo 3 Teach"

-   Add tables: -

    -   Before "The plot below"
    -   Insert H2: "Datasets"
    -   Insert text: "This package has two datasets:"
    -   Insert tabsets:
        -   tab 1: penguins_raw
            -   Includes nesting observations, penguin size data, and isotope measurements from blood samples for adult Adélie, Chinstrap, and Gentoo penguins.
        -   tab 2: penguins
            -   Subset of `penguins_raw`, includes measurements for penguin species, island in Palmer Archipelago, size (flipper length, body mass, bill dimensions), and sex.

-   Add H2 before plot "A first look at penguins"

#### Part 4

-   Change to `format: revealjs` -\> save to render

-   Remove execute / echo to show they're off by default -\> save to render

-   Add code line highlighting to plotting chunk

    ``` r
      #| code-line-numbers: "|1-2|3|4|5-13|14"
    ```

-   Show hamburger menu outline and print to PDF

-   Add chalkboard

    ``` yaml
    format: 
      revealjs:
        chalkboard: true
    ```

#### Part 5

-   Change to `format: html`

-   Add `index.qmd` with File \> New Quarto Document

    ``` markdown
    ---
    title: "Welcome"
    format: html
    editor: visual
    ---

    Welcome to the demo site for the "Hello, Quarto!" talk at rstudio::conf(2022)!
    ```

-   Add `_quarto.yml`

    ``` yaml
    project:
      type: website

    website:
      title: "Quarto"
      navbar:
        left:
          - index.qmd
          - hello.qmd
    ```

-   Relaunch projects with File \> Recent projects \> choose most recent

-   Show new Build tab

-   Preview site, show `_site` folder

-   Make one change in hello.qmd, watch it update the site

### Demo 2 - Collaborate:

-   Orient to JupyterLab
-   Open Mine's example site, quarto preview
-   Open website in separate window (narrow windows) 
-   New `.ipynb` Copy pre-made one: New Terminal > `cp hello_in_python.ipynb hello-quarto-demo` (can pause recording)
-   Talk through and execute notebook chunks
-   Add `.ipynb` to `_quarto.yml`
-   View website - new page is added to website
-   Add quarto commenting - no auto-update! Because  Freeze by default with Jupyter Notebooks -- this actually did auto-update hmmmm
-  Add fig captions

```
#| fig-cap: "Body Mass by Island for each Species."
```
- Add margin

```
#| column: margin   
```

-   Turn this into slides (??)
-   `quarto convert` to .qmd
-   `quarto publish` (??)

### Demo 3 - Teach / teaching things:

-   Auto linking code to docs

    ``` yaml
    format: 
      html:
        code-link: true
    ```

-   

### Demo 4 - Reimagine / visual editor:

-   open project in RStudio
-   quarto preview, no prob with the .ipynb file
-   Edit Mine's index.qmd 
    - make sure the "render on save" button is on
    - it's really nice for writing a lot of prose
    - it's also really great for pasting text from let's say a google doc! Formatting stays.
-   Add image: 
    -   using the visual editor, `images/lter_penguins.png`
    -   add alt text: Three species of penguins: Chinstrap, Gentoo, and Adelie.
    -   close dialogue -\> save to render
    -   double click on image and change width to 400, tab to change height
    -   go to Attributes and under CSS classes add `float: right;` -\> save to render
    -   switch over to source editor to show how this info is recorded
-   Tables
- Two columns - make the image and table in 2 columns
-   Call-outs
-   Citations: 10.1371/journal.pone.0090081
- let's create a section in the quarto_yml
