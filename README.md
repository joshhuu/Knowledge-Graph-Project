---

# Knowledge Graph Project: The Movies Dataset

## Overview
This project involves building a **Knowledge Graph (KG)** from **The Movies Dataset** available on Kaggle. The goal is to extract, organize, and represent the relationships between movies, genres, directors, actors, production companies, and other related metadata in a graph format, enabling more effective querying and data retrieval.

The project will also demonstrate how to build and visualize a knowledge graph, integrate the relationships among entities, and query it using graph-based techniques.

## Dataset Information
The dataset includes information about movies such as:
- Movie title
- Genres
- Cast (actors and actresses)
- Crew (directors, writers, etc.)
- Production companies
- Budget, revenue, and other financial data
- Release date and runtime
- Language, keywords, etc.

You can download the dataset from Kaggle: [The Movies Dataset](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset)

## Objectives
- **Data Extraction**: Load and preprocess data from the movies dataset.
- **Knowledge Graph Construction**: Create nodes for different entities such as movies, genres, actors, directors, and companies, and define relationships between them.
- **Graph Querying**: Use graph traversal techniques to extract insights like common actors across movies, genre popularity, director collaborations, etc.
- **Visualization**: Visualize the knowledge graph to explore relationships and connections.
- **Integration with Machine Learning**: Optionally, integrate the knowledge graph with machine learning models to predict movie success, genres, or user preferences.

## Technologies Used
- **Python**: Primary programming language
- **NetworkX**: For creating and managing the knowledge graph
- **Neo4j**: For graph database management (optional, if you want to store and query the graph)
- **pandas**: For data manipulation and preprocessing
- **Matplotlib/Plotly**: For graph visualization
- **Jupyter Notebook**: For documentation and exploration

## Steps Involved
### 1. Data Preprocessing
- Load the dataset into a pandas DataFrame.
- Clean and preprocess the data (handling missing values, duplicates, and standardizing formats).
  
### 2. Graph Construction
- Create nodes for each entity (e.g., movies, genres, actors).
- Define relationships (edges) between nodes, such as "acted_in," "directed_by," "belongs_to_genre," etc.

### 3. Querying the Knowledge Graph
- Implement graph query functions to retrieve insights from the graph.
- Examples: Find movies of a particular genre, identify top directors, or recommend movies based on similar actors.

### 4. Graph Visualization
- Visualize the knowledge graph using NetworkX or Plotly to explore movie relationships visually.

### 5. Optional Machine Learning Integration
- Integrate the knowledge graph with machine learning models to predict movie success, ratings, or user preferences based on graph features.

### Packages to be installed 
pandas==2.0.3
numpy==1.24.3
networkx==3.0
matplotlib==3.7.2
plotly==5.16.0
neo4j==5.11.0
jupyterlab==4.0.5
scipy==1.11.2



## Example Queries
- **Find all movies by a particular director**:
  ```python
  query = "MATCH (d:Director)-[:DIRECTED]->(m:Movie) WHERE d.name = 'Steven Spielberg' RETURN m.title"
  ```

- **List all actors who acted in movies of a specific genre**:
  ```python
  query = "MATCH (g:Genre)-[:HAS_GENRE]->(m:Movie)<-[:ACTED_IN]-(a:Actor) WHERE g.name = 'Action' RETURN a.name, m.title"
  ```

## Contributing
Feel free to fork the repository, create pull requests, and submit issues if you encounter bugs or have suggestions for improvements.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
