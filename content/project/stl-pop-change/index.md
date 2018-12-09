+++
# Project title.
title = "St. Louis Neighborhood Change"

# Date this page was created.
date = 2018-12-09T00:00:00

# Project summary to display on homepage.
summary = "Population changes, 2010 to 2017."

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["StLouis", "GIS", "Demography"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Links (optional).
url_pdf = ""
url_slides = ""
url_video = ""
url_code = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
url_custom = [{icon_pack = "fas", icon="download", name="Download", url = "nhoodChange.png"}, {icon_pack = "fab", icon="github", name="Data & Code", url = "https://github.com/chris-prener/STL_DEMOGRAPHY_NhoodChange"}, {icon_pack = "fab", icon="twitter", name="Tweet", url = "https://twitter.com/chrisprener/status/1071078021690474496"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = "North St. Louis, Midtown, and Downtown neighborhoods"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"
+++

With the release of the 2013-2017 5-year estimates from the U.S. Census Bureau's [American Community Survey](https://www.census.gov/programs-surveys/acs/), I wanted to get a sense of how St. Louis's neighborhoods are changing in terms of population. These percentages compare the latest population estimates to the 2010 Decennial Census. 

The largest estimated population growth is found in Downtown, Downtown West, the Central West End, The Grove, Lafayette Square, and Tower Grove East. Much of the rest of Midtown and South City saw either modest population increases or were stable. North City, with the exception of Old North and the West End, saw varying degrees to population loss. 

[![](/project/stl-pop-change/nhoodChange.png)](nhoodChange.png)

### Technical Notes
This map was created by interpolating census tract data into neighborhood boundaries for both the 2010 Decennial Census and the 2013-2017 ACS. Population change was then calculated and mapped using a modification of [Jenks natural breaks](https://en.wikipedia.org/wiki/Jenks_natural_breaks_optimization). 

ACS data should be interpreted as *estimates* and not exact population values, and are therefore subject to a degree of error. Interpolation introduces a degree of error as well, particularly in neighborhoods boarding significant un-populated areas like Forest Park or the Botanical Gardens.

All data analysis and mapping was done using `R`, using the [`tidycensus`](https://walkerke.github.io/tidycensus/) package for data access, the [`areal`](https://github.com/slu-openGIS/areal) package for interpolations, and [`ggplot2`](http://ggplot2.tidyverse.org) for mapping.

