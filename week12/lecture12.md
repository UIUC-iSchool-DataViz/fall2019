---
title: Lecture 12
layout: lecture
---

<!-- .slide: class="titleslide" -->

# Data Visualization

<div style="height: 6.0em;"></div>

## Matthew Turk
## Fall 2019
## Lecture 12

---

# Assignment Highlights

 * [How Migration is Changing Our World](https://www.bloomberg.com/graphics/2019-how-migration-is-changing-our-world/)
 * [15 Visualizations](https://blog.udacity.com/2015/01/15-data-visualizations-will-blow-mind.html), especially:
   * Shooting stars, satellites, workday, music timeline
 * [Citibike Data](https://twitter.com/CraigTaylorGIS/status/1191282070380789760)
 * [Opiod Overdoes](https://medium.com/@chaitupramod/redesigning-a-bad-graph-spaghetti-to-micromaps-374d68b5df6c)
 * [Letter Frequency](https://public.tableau.com/en-us/gallery/frequency-letters)

---

## Today

 1. Scientific Visualization
 2. Big-ish Data
 3. Portfolio Building

---

## Scientific Visualization

What characterizes "scientific" visualization?

 * Spatial organization - distance metrics
 * Dimensionality reduction or mapping
 * Multiple overlapping quantities with implicit or explicit extent

---

## Scientific Visualization - Data Representations

<div class="multiCol">
<div class="col">
<div class="fig-container" data-style="height: 600px;" data-file="figures/blank_axes.html" data-markdown=true>
</div>
</div>
<div class="col" data-markdown=true>

Commonly, data will be represented in "scientific visualization" through one of a few mechanisms:

 * Discrete points
 * Volume-filling information
 * Meshed values

</div>
</div>

---

## Discrete Points: Data

<div class="multiCol">
<div class="col">
<div class="fig-container" data-style="height: 600px;" data-file="figures/scatter.html" data-markdown=true>
</div>
</div>
<div class="col" data-markdown=true>

 * Associated field values
 * May have extent
 * Values can be either
   * Locally defined
   * Integrated over neighbors
</div>
</div> 

---

## Discrete Points: Techniques


<div class="multiCol">
<div class="col">
<div class="fig-container" data-style="height: 600px;" data-file="figures/discrete_tech.html" data-markdown=true>
</div>
</div>
<div class="col" data-markdown=true>

 * Associated field values
 * May have extent
 * Values can be either
   * Locally defined
   * Integrated over neighbors
</div>
</div> 


---

## Discrete Points: Density Estimates



---

## Discrete Points: Regular

---

## Discrete Points: Quadtree

---

## Discrete Points: kD-tree

---

## Volume-filling: Data

For this, we will be using Python to collaboratively explore what volume-filling data is.

Install yt and ipyvolume.

```
conda install -c conda-forge yt ipyvolume
```

---

## Volume-filling: Techniques

---

## Mesh: Data

---

## Mesh: Techniques

---

## Python Tools

We'll try out a handful of Python tools.

 * `matplotlib`
 * `yt`
 * `ipyvolume`

You can install each of these individually.

---

## Big-ish Data

How do we deal with data that is too large to fit into memory?

 * Can we cycle our operations?
 * Can we use tools to cycle operations?

---

## Operations

Some operations we can manually cycle through, storing only reductions in
memory rather than the full dataset.

Clear candidates:

 * Mean
 * Extrema
 * Histograms and "binning"

Is this the same as incremental updates to a dataset?

(What about the median?)

---

## Portfolio Building

GitHub pages is a simple, straightforward way to publish websites.

 * Static-site generation using Jekyll
 * Manual HTML building
 * Integration with other systems (Idyll)

---

## Publishing Notebooks

Jupyter Notebooks can be published online.  The simplest way:

 * Commit them to a github repository
 * View them using nbviewer.jupyter.org

Widget state can be saved in many cases.

http://ipywidgets.readthedocs.io/en/latest/embedding.html

---

## Your First Github Page

 * We will use Jekyll to build a github page
 * Create the repository `[username].github.io`
 * Clone this repository.
 * Let's talk about the branches `gh-pages` and `master`

