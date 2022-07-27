# hello-quarto-demo

Repository for the demos in the "Hello, Quarto!" talk

## Software

-   RStudio:

    -   Version: Current release -- RStudio 2022.07.0+548 "Spotted Wakerobin" Release (34ea3031089fa4e38738a9256d6fa6d70629c822, 2022-07-06) for macOS Mozilla/5.0 (Macintosh; Intel Mac OS X 12_4\_0) AppleWebKit/537.36 (KHTML, like Gecko) QtWebEngine/5.12.10 Chrome/69.0.3497.128 Safari/537.36
    -   Theme: rsthemes::a11y-light

-   R 4.2.1

-   MousePose - Mouse Clicks on

-   Desktop - Background single color Quarto blue (#75aadb)

-   Quarto - 1.0.36

## Steps

### Demo 1 - Share / flexibility in formats:

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

-   Add alt text to figure in second code chunk -\> save to render

    ``` r
    #| fig-alt: |
    #|   Scatterplot of bill length vs. flipper length for three 
    #|   species of penguins. The relationship is positive and 
    #|   moderately strong. The three species are identified on 
    #|   the plot with points with different colors and shapes, 
    #|   revealing three clusters.
    ```

-   Change to `format: revealjs` -\> save to render

-   Remove execute / echo to show they're off by default -\> save to render

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

-   Add freeze to _quarto.yml

    execute:
      freeze: true

-   From terminal: `quarto publish quarto-pub`

### Demo 2 - Collaborate:
Starting setup: `hello-quarto-demo@main` cloned, Terminal open already cd'd into the repo. Zoom screenshare show url. Mousepose.

-   Orient to JupyterLab
-   Open Mine's example site, quarto preview
-   Open website in separate window (narrow windows) 
-   PAUSE recording - copy pre-made .ipynb (New Terminal > `cp hello_in_python.ipynb hello-quarto-demo`, delete code comments. Also open _quarto.yml)
-   Talk through and execute notebook chunks
-   Add `.ipynb` to `_quarto.yml`
-   View website - new page is added to website
-  Add fig captions

```
#| fig-cap: "Flipper and bill length for penguins"
```
- Add margin

```
#| column: margin   
```

-   `quarto convert` to .qmd
-   ~Turn this into slides~

### Demo 3 - Teach / teaching things:

-   Features that are useful for teaching:
    -   Add chalkboard
    
        ``` yaml
        format: 
          revealjs:
            chalkboard: true
        ```    
    -   Show hamburger menu outline and print to PDF
    -   multiplex: Slides / scroll for audience
    -   Add code line highlighting to plotting chunk
   
       ``` r
         #| code-line-numbers: "|1-2|3|4|5-13|14"
       ```
    -   Auto linking code to docs
    
        ``` yaml
        format: 
          html:
            code-link: true
        ```
    -   Add tabsets

-   Features that are useful for learning:
    -   if teaching with rstudio, it comes with everything, and people can just get started
    -   visual editor -- Julie will say more
    -   yaml errors
    
-   Features that are useful for research: quarto journal

### Demo 4 - Reimagine / visual editor:

Prep: pull hello-quarto-demo@collab, open index.qmd and delete visual in yml. Mousepose.

Goal: to show you the visual editor, and also some additional features of Quarto that are integrated in the Visual Editor

-   open project in RStudio
-   Open Mine's index.qmd 
- switch to visual editor
- Now let's edit: 
    - Type "Quarto unifies and extends the RMarkdown ecosystem." 
- pasting text from a google doc! Formatting stays: 

```

[**Quarto**](https://quarto.org) is a new, open-source, scientific and technical publishing system that makes the process of creating and collaborating dramatically better. It\'s a **really powerful** tool for research teams, since we can use the same workflow for reproducible data analyses and for and for new ways of contributing to science. See the [Quarto Gallery](https://quarto.org/docs/gallery/) for examples and learn more through [Quarto at rstudio::conf(2022)](https://quarto.org/docs/blog/posts/2022-06-21-rstudio-conf-2022-quarto/).


Next we'll explore Quarto with the tidyverse and data from the[ palmerpenguins](https://allisonhorst.github.io/palmerpenguins) R package.
```
-   Add image: 
    -   using the visual editor, Insert menu: `images/horst_quarto_meteor.png`
    -   add caption: The Quarto meteor crosses the night sky. We liked the idea of Quarto in the night sky and worked with Allison Horst to bring these ideas to life. Allison made several other images with Quarto in the night sky, including illustrations depicting teach, collaborate, share, and reimagine. 

    -   add alt text: An illustrated meteor with the quarto logo crosses the night sky
    -   close dialogue -\> save to render \> 
    -   double click on image and change width to 400, tab to change height
    -   switch over to source editor to show how this info is recorded
-   Add citations: 
    - 1. Command - / to add a doi: 10.1371/journal.pone.0090081
    - 2. \@ to search my Zotero library
-   Also: Call-outs
    - Final tip: To learn more
     - Check out our [slides](https://mine.quarto.pub/hello-quarto)

- ONE LAST THING about Quarto that aren't Visual Editor Specific but I'd like to show you:
- Add extension: 
```
filters:
   - lightbox
lightbox: auto   
```

