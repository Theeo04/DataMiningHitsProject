# Structural Analysis of Web Networks Using HITS

## 1. Project Overview

Analyze the structure of web networks using the **HITS (Hyperlink-Induced Topic Search)** algorithm.

- Identify **Hubs** (pages linking to valuable resources) and **Authorities** (pages referenced by good hubs).
- Compare structural patterns across two real-world directed web networks.
- Investigate how removing hyperlinks affects Hub–Authority relationships.
- **Focus:** Network structure and robustness, not web page ranking.

## 2. Datasets

| Dataset | Nodes | Edges | Source |
|---|---:|---:|---|
| Pajek/EPA | 4,772 | 8,965 | [SuiteSparse EPA](https://sparse.tamu.edu/Pajek/EPA) |
| Pajek/California | 9,664 | 16,150 | [SuiteSparse California](https://sparse.tamu.edu/Pajek/California) |

**Dataset Descriptions:**

- **Pajek/EPA:** A hyperlink network of web pages linking to the US Environmental Protection Agency website (`www.epa.gov`), constructed by expanding an initial set of 200 search results.
- **Pajek/California:** A hyperlink network generated from the search query "California", expanded from 200 initial search results to related web pages.

**Structure:** Directed graphs where nodes represent web pages and edges represent hyperlinks.

**Dataset Format:** Matrix Market (`.mtx`), convertible to an edge list containing source and target node IDs.

## 3. Implementation

1. **Data Processing:** Load datasets, construct directed graphs and analyze degree distributions.
2. **HITS Algorithm:** Implement Hub/Authority calculations in Python and validate with NetworkX.
3. **Structural Analysis:** Classify nodes as Hub, Authority, Hybrid or Peripheral using top-10% score thresholds.
4. **Baseline Comparison:** Compare Hub scores with out-degree and Authority scores with in-degree.
5. **Visualization:** Network subgraphs, Hub–Authority scatter plots and role distributions.

## 4. Special Experiment – Network Robustness

**Research Question:** How stable are Hub–Authority relationships under random and targeted hyperlink removal?

- **Scenario A:** Original network (baseline).
- **Scenario B:** Randomly remove 10% of edges (10 independent trials).
- **Scenario C:** Remove 10% of edges, prioritizing outgoing links from nodes with the highest initial Hub scores.
- **Evaluation:** Recalculate HITS and measure role changes (%) and top-10% Hub/Authority set overlap (Jaccard similarity).
- **Comparison:** Analyze which network and removal strategy produces greater structural changes.

## 5. Technologies

**Python, Jupyter Notebook, NetworkX, NumPy, Pandas, Matplotlib.**

## 6. Learning Resources

1. Graph Fundamentals – https://networkx.org/documentation/stable/tutorial.html
2. Web Mining & Link Analysis – https://nlp.stanford.edu/IR-book/pdf/21link.pdf
3. HITS Algorithm – https://nlp.stanford.edu/IR-book/html/htmledition/hubs-and-authorities-1.html
4. Original HITS Paper – https://www.cs.cornell.edu/home/kleinber/auth.pdf
5. HITS Implementation – https://networkx.org/documentation/stable/reference/algorithms/generated/networkx.algorithms.link_analysis.hits_alg.hits.html