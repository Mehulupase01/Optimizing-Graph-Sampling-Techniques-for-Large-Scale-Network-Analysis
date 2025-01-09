# Optimizing Graph Sampling Techniques for Large-Scale Network Analysis

In large-scale graph analysis, efficient sampling is crucial for reducing the computational complexity of graph algorithms while still preserving key network properties. This project focuses on optimizing graph sampling techniques and evaluating their effectiveness on various real-world datasets. Our goal is to create smaller, representative subgraphs that can be analyzed in place of the original massive graphs.

## Overview

Social network analysis has become a central area of study due to the rapid growth of large-scale networks in various domains, such as social media platforms, biological networks, and communication systems. However, the sheer size of these networks often makes them computationally expensive and difficult to analyze. Graph sampling techniques provide an effective solution by generating smaller subgraphs that preserve essential properties of the original graph.

### Objectives of the Project:

- **Graph Sampling Algorithms**: Implement and compare different graph sampling techniques such as **Random Node Selection**, **PageRank-based Sampling**, and **Random Walk Sampling**.
- **Preservation of Graph Properties**: Ensure that the sampled graph maintains key properties like degree distribution, clustering coefficients, and path lengths.
- **Evaluation Metrics**: Utilize metrics like the **Kolmogorov-Smirnov D-statistic** to quantitatively assess how well the sampled graphs preserve the original graph's structure.
- **Empirical Analysis**: Conduct a thorough experimental evaluation of sampling techniques on several real-world datasets, including social networks, road networks, and online reviews, to determine the most effective techniques.

The project’s main contributions are to refine existing sampling methods, test their performance on diverse datasets, and identify potential biases or limitations in the current frameworks. Our research aims to improve the scalability and adaptability of graph sampling techniques for large-scale network analysis.

## Project Structure

The project consists of the following key components:

1. **Sampling Algorithms**:
   - **Random Node Selection (RN)**: Randomly selects nodes to form the sample, with an aim to preserve degree distribution.
   - **Random PageRank Node Selection (RPN)**: Uses PageRank scores to probabilistically select nodes.
   - **Random Degree Node Selection (RDN)**: Nodes are selected with a probability proportional to their degree.
   - **Random Walk (RW)** and **Random Jump (RJ)**: Explore the graph using random walks, where nodes are selected based on walk trajectories.
   - **Forest Fire (FF)**: Simulates a "burning" process to spread through the graph, selecting nodes and edges accordingly.

2. **Graph Properties Preservation**:
   - The project evaluates the preservation of key graph properties like **in-degree distribution**, **out-degree distribution**, **strongly connected components (SCC)**, **weakly connected components (WCC)**, and **clustering coefficients**.

3. **Kolmogorov-Smirnov D-statistic**:
   - This statistical test is used to compare the degree distribution and other properties of the sampled graph to the original graph, helping assess the quality of the sampling methods.

4. **Datasets**:
   - **Social Network**: A large-scale directed graph representing social media interactions.
   - **Amazon Product Co-Purchasing Network**: A graph representing relationships between products purchased together.
   - **Internet Network (Gnutella)**: Peer-to-peer network topology.
   - **California Road Network**: Road network data representing intersections and road connections.
   - **Online Reviews Network**: Network of user reviews for products on Amazon.

5. **Code Implementation**:
   - **`Algorithms.ipynb`**: Contains the code for implementing the sampling algorithms, including node selection methods, random walk algorithms, and Forest Fire sampling.
   - **`D Stat.ipynb`**: This notebook computes the Kolmogorov-Smirnov D-statistic to evaluate the similarity between sampled and original graphs. It also performs the necessary statistical analysis for the sampled graphs.
   - **`Sampling_from_graphs.pdf`**: The accompanying paper detailing the theory and methodology behind the sampling techniques and their empirical evaluation.

## Methodology

### Sampling Techniques

Graph sampling techniques are categorized based on the way nodes and edges are selected for the sampled graph. Some methods focus on random selection of nodes, while others explore the graph structure to select connected components. Each algorithm is designed to preserve a different set of graph properties, such as node centrality, clustering coefficients, or degree distribution.

- **Node Sampling**: Involves selecting a subset of nodes from the graph, either randomly or based on their degree or importance (PageRank).
- **Edge Sampling**: Focuses on selecting edges based on node connectivity, ensuring that the sampled graph preserves network flow and connectivity properties.
- **Hybrid Sampling**: Combines node and edge sampling to balance the representation of graph structure and connectivity.

### Evaluation Criteria

The primary evaluation technique used in this project is the **Kolmogorov-Smirnov D-statistic**, which quantifies the difference between the distributions of graph properties in the original and sampled graphs. This measure helps assess the effectiveness of each sampling algorithm in preserving the original graph's key metrics.

### Experimental Setup

We perform experiments on multiple datasets from various domains, including social networks, road networks, and product co-purchasing networks. The experiments are designed to:

1. Test the effectiveness of each sampling algorithm.
2. Compare the properties of the sampled graphs with the original graphs using statistical tests.
3. Evaluate the performance of sampling algorithms at different sample sizes, ranging from 15% to 50% of the original graph.

## Results & Discussion

The results indicate that **Random Walk (RW)** and **Random Jump (RJ)** perform best when the sample size is small (around 15%), while methods like **Forest Fire (FF)** and **Random Node Selection (RN)** provide more stable results at larger sample sizes. The **Kolmogorov-Smirnov D-statistic** was instrumental in quantifying the preservation of graph properties, revealing that certain sampling algorithms excel in maintaining degree distribution and connectivity, while others perform better in preserving clustering coefficients and community structure.

## Conclusion

This project provides a comprehensive evaluation of various graph sampling techniques, offering valuable insights into their strengths and limitations. Our findings show that **Random Walk** and **Forest Fire** are the most effective techniques for preserving graph properties at different sample sizes. However, the performance of each algorithm depends on the specific graph properties that need to be preserved, highlighting the importance of choosing the appropriate sampling technique based on the application's needs.

## Future Work

- **Weighted Graph Sampling**: Extend the current sampling techniques to work with graphs that have weighted edges, allowing for more accurate representation of real-world systems.
- **Sampling for Specific Properties**: Develop sampling algorithms optimized for specific properties such as centrality or community structure, and evaluate their performance in various graph types.

For further implementation details, refer to the code in `Algorithms.ipynb` and `D Stat.ipynb`.

## Acknowledgments

We thank our academic advisor, Dr. Frank Takes, for his guidance and support. We also appreciate the researchers and datasets available from **SNAP** and other sources.

## References

- [Leskovec, J., & Faloutsos, C. (2006). Sampling from Large Graphs](https://doi.org/10.1145/1150402.1150479)
- [Rajaraman, A., & Ullman, J. D. (2011). Mining of Massive Datasets](https://doi.org/10.1109/MASCOT.2003.1240643)
