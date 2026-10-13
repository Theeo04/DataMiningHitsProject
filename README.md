# Structural Analysis of Web Networks Using HITS

## 1. Project Overview

Analyze the structure of web networks using the **HITS (Hyperlink-Induced Topic Search)** algorithm.

- Identify **Hubs** (pages linking to useful resources) and **Authorities** (pages referenced by good hubs).
- Compare structural patterns across two real-world web networks.
- Investigate how removing hyperlinks affects Hub–Authority relationships.
- **Focus:** Network structure and robustness, not web page ranking.

## 2. Datasets

| Dataset |   Nodes |   Edges | Source                                                |
| ------- | ------: | ------: | ----------------------------------------------------- |
| Web-EDU | \~3,000 | \~6,500 | https://networkrepository.com/web_edu.php             |
| Web-EPA | \~4,300 | \~9,000 | https://networkrepository.com/web_EPA.php             |

**Structure:** Graph with nodes (web pages) and edges (hyperlinks).

Dataset Structure: Each row contains two node IDs (`source → target`), representing a hyperlink from the source web page to the target web page, assuming the dataset preserves edge direction.

## 3. Implementation

1. **Data Processing:** Load datasets and build directed graphs.
2. **HITS Algorithm:** Implement Hub/Authority calculations in Python.
3. **Structural Analysis:** Classify nodes as Hub, Authority, Hybrid or Peripheral using score thresholds.
4. **Visualization:** Graph structure, Hub–Authority scatter plots and role distributions.

## 4. Special Experiment – Network Robustness

**Question:** How do Hub–Authority relationships change when hyperlinks disappear?

- **Scenario A:** Original network (baseline).
- **Scenario B:** Remove 10% of hyperlinks randomly.
- **Scenario C:** Remove 10% of hyperlinks, prioritizing links from important hubs.
- Recalculate HITS and compare role changes and role stability (Jaccard similarity) across both datasets.

## 5. Technologies

**Python, Jupyter Notebook, NetworkX, NumPy, Pandas, Matplotlib.**

## 6. Learning Resources

1. [Graph Fundamentals – NetworkX](https://networkx.org/documentation/stable/tutorial.html)
2. [Web Mining & Link Analysis – Stanford](https://nlp.stanford.edu/IR-book/pdf/21link.pdf)
3. [HITS Algorithm – Stanford](https://nlp.stanford.edu/IR-book/html/htmledition/hubs-and-authorities-1.html)
4. [Original HITS Paper – Jon Kleinberg](https://www.cs.cornell.edu/home/kleinber/auth.pdf)
5. [HITS Implementation – NetworkX](https://networkx.org/documentation/stable/reference/algorithms/generated/networkx.algorithms.link_analysis.hits_alg.hits.html)
