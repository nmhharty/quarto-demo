## About The Project

Reporting is a necessity in public health, but traditional workflows often rely on copying tables out of R scripts into word processing 
software or slide decks. This manual copy-paste process introduces errors, makes updating analyses tedious, and leads to formatting 
inconsistencies across teams.

This repository serves as a demonstration and educational resource for the **CDPHE Healthcare Associated Infections (HAI) Program** and State 
of Colorado **Programming Users Group at the State (PUGS)**. It showcases how **Quarto**—an open-source scientific and technical publishing system—enables 
data teams to combine text, code, dynamic tables, and images into fully reproducible reports and presentations.

Key benefits demonstrated in this project include:  
* **Automated Data Pipelines:** Refreshing analyses, tables, and narrative calculations instantly when underlying data updates.
* **Standardized Branding:** Enforcing official State of Colorado / CDPHE visual guidelines (`_brand.yaml`) across output formats.
* **Multi-Format Publishing:** Generating interactive HTML reports, Word documents (`.docx`), PDF files, and Revealjs slide decks from the same raw code.
* **Significant Efficiency:** Reducing annual report writing and assembly time by up to 75%.

### Built With

* [R](https://www.r-project.org/)
* [Quarto](https://quarto.org/)
* [Revealjs](https://quarto.org/docs/presentations/revealjs/)
* [knitr](https://yihui.org/knitr/)

## Project Contents

This repository contains two Quarto slide decks that can be used as templates, alongside an automated annual report template used for live 
demonstrations.

### 1. The Single Quarto Document (`quarto-demo-hai.qmd`)
* **Overview:** A single, standalone Quarto document containing all presentation metadata and Quarto slides. Slides were used for a brief presentation
to the CDPHE HAI Program.  
* **Structure:** Follows a standard vertical authoring layout. It uses the default Revealjs `black` theme.  
* **Use Case:** Best suited for shorter presentations, single-author decks, or quick exploratory talks where maintaining one long file is manageable.  

### 2. The Modular Approach (`index-pugs.qmd`)
* **Overview:** A modular framework where `index-pugs.qmd` serves as a lightweight master file that stitches together separate sub-files (`01-intro.qmd` 
through `06-but-how.qmd`) using Quarto's `{{< include >}}` shortcodes. Slides were used for an hour-long presentation and demonstration to the Programming Users 
Group at the State (PUGS) in August 2026.  
* **Branding Integration:** Utilizes a custom theme bound to `_brand.yaml`. This YAML configuration enforces official CDPHE branding, automatically setting color palettes 
(Primary Dark Blue `#001970`) and unifying typography (`Trebuchet MS`).
* **Use Case:** Ideal for large presentations, team-based collaboration, and reusable workshop modules. Modularizing slides prevents merge conflicts and simplifies maintenance.

### 3. The Live Demo Script (`_demo-report.qmd`)
* **Overview:** A parameterized report template simulating the state HAI Annual Report workflow.
* **Features:**
  * Demonstrates inline R computations embedded within narrative paragraphs.
  * Dynamically populates custom summary tables using `flextable`.
  * Showcases YAML parameterization (`params`), automated figure/table cross-referencing, and multi-format output targets (`html`, `docx`, `pdf`, `typst`).

## Getting Started

To render these slides and test scripts locally, ensure your environment meets the prerequisites below.

### Prerequisites

You must have **R** (v4.0 or higher), **RStudio**, and the **Quarto CLI** installed.

Install the required R package dependencies using the console:

* **Slide Deck Dependencies:**
  ```R
  install.packages(c("knitr", "fontawesome"))
  ```

* **Live Demo (`_demo-report.qmd`) Dependencies:**
  ```R
  install.packages(c("flextable", "googlesheets4", "dplyr", "lubridate", "purrr", "glue", "yaml"))
  ```

### Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/nmhharty/quarto-demo.git
   ```
2. Open `quarto-demo.Rproj` in RStudio.
3. Install missing R package dependencies listed above.

## Usage

You can render files directly in RStudio using the **Render** button, or via the terminal using the Quarto CLI.

#### Render the Monolithic Presentation
```sh
quarto render quarto-demo-hai.qmd
```

#### Render the Modular Presentation (with CDPHE Brand Theme)
```sh
quarto render index-pugs.qmd
```

#### Render the Parameterized Live Demo Report
```sh
quarto render _demo-report.qmd
```

## Contributing  

Contributions make the open-source community an amazing place to learn, inspire, and create.  

1. Fork the Project  
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)  
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)  
4. Push to the Branch (`git push origin feature/AmazingFeature`)  
5. Open a Pull Request  

## Contact  

Nicole Harty, MPH - NHSN Data Unit Manager, CDPHE Healthcare Associated Infections Program  

Project Link: [https://github.com/nmhharty/quarto-demo](https://github.com/nmhharty/quarto-demo)  

## Acknowledgements

* [Jadey Ryan's Talks on Reproducible Reporting with Quarto](https://jadeyryan.com/talks)  
* [Nicola Rennie's Introduction to Quarto Training](https://nrennie.rbind.io/training-intro-to-quarto/slides.html)  
* [Othneil Drew's Best-README-Template](https://github.com/othneildrew/Best-README-Template)  
