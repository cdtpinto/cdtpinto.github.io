# Readability Checker

Readability Checker is a plugin for the NetBeans IDE that estimates Java source code readability using three different software readability formulas and metrics.

![Main Window](https://raw.githubusercontent.com/cdtpinto/cdtpinto.github.io/development/files/images/readability_checker_ui.PNG "Readability Checker Main Window")

## Features

The main window shows the readability of the currently opened project. The readability of each file can be viewed by selecting the "Detailed Results" option.

Readability analysis for a specific formula or metric can be disabled by toggling the "Disable" checkbox.

After checking the readability, the results can be exported to a text file by pressing the "Export Results" button.

## Installation

These are the install instructions for Apache NetBeans 10.0. Steps may slightly vary for other versions of the IDE.

1. Download `nbm` file [here](https://www.dropbox.com/s/6s8b8sv8n5680jg/ReadabilityChecker-1.0.4.nbm?dl=0)
2. In NetBeans, go to **Tools** > **Plugins** > **Downloaded** > **Add Plugins**
3. Select the downloaded `ReadabilityChecker-1.0.4.nbm` file
4. Click **Install** and follow the instructions

The following icon should now appear in the upper left corner of NetBeans: ![](https://raw.githubusercontent.com/cdtpinto/cdtpinto.github.io/master/files/images/readabilitycheckericon24.png "Readability Checker Icon")

## Implemented Formulas and Metrics

Currently, Readability Checker implements three software readability 
as:

* Comments Ratio
* Software Readability Ease Score (SRES)
* Buse & Weimer (B&W)

### Comments Ratio

Proposed in 2002 by the researchers Krishan K. Aggarwal, Yogesh Singh and Jitender Kumar Chhabra in the article [An Integrated Measure of Software Maintainability](https://ieeexplore.ieee.org/document/981648/).

The proposed formula is:

![](https://raw.githubusercontent.com/cdtpinto/cdtpinto.github.io/master/files/images/comments_ratio_formula.gif "Comments Ratio Formula")

where:

LOC is the number of lines of code

LOM is the number of lines with comments

##### Implementation notes

* **Fully supports Java SE 11.**

* Aggarwal et al. say that a comments ratio between 1 and 5 mean a good readability value, between 5 and 8 mean an average readability value and bigger that 8 mean a poor readability value. However, later studies suggest that the number of comments should be consistent with the code and controlled. So, the readability values for this formula should be critically considered as good or bad.

* Analyzes the readability of the project, it's classes and methods.

### SRES

Theorized by Jürgen Börstler, Michael E. Caspersen and Marie Nordström, the general principles of this readability formula were first introduced in 2007, in the article [Beauty and the Beast Toward a Measurement Framework for Example Program Quality](https://pdfs.semanticscholar.org/8c41/1a1fb987966f2020765069dc21881826e635.pdf), then it's logic was implemented in a readability tool titled [Properties of "Good" Java Examples](http://www8.cs.umu.se/education/examina/Rapporter/NadeemAbbas_v2.pdf) by Nadeem Abbas, and later on, in 2015, the SRES readability formula was finally suggested in the article [Beauty and the Beast: on the readability of object-oriented example programs](https://link.springer.com/article/10.1007/s11219-015-9267-5).

The proposed formula is:

![](https://raw.githubusercontent.com/cdtpinto/cdtpinto.github.io/master/files/images/sres_equation.gif "SRES Formula")

where:

ASL is the average sentence length

AWL is the average word length

##### Implementation notes

* **Fully supports Java SE 5.**

* Threshold readability value is 6. Values closer to 0 mean more readable code.

* Analyzes the readability of the project and it's classes.

### B&W

This software readability metric was proposed in 2010 by the researchers Raymond Buse and Westley Weimer in the paper [Learning a Metric for Code Readability](https://ieeexplore.ieee.org/document/5332232).

This metric isn't translated in a specific formula. Instead, some features of the code (e.g. number of identifiers, number of spaces, etc...) are considered to calculate the code readability, using an approach described in the mentioned paper.

This metric was implemented by the authors and is available [here](http://www.arrestedcomputing.com/readability). This is the implementation used on Readability Checker.

#### Implementation notes

* **Fully supports Java SE 11.**

* Readability values range from 0 to 1. Values closer to 1 mean a more readable code.

* Analyzes the readability of the project and it's classes.
