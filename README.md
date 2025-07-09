# study_links
Some training for python packages <br />
numpy pandas matplotlib plotly

# numPy (Numerical Python)
This library is the foundation for numerical computing in Python.<br />
It provides powerful N-dimensional array objects and a collection of routines for fast operations on these arrays, including mathematical, logical, shape manipulation, sorting, selecting, I/O, discrete Fourier transforms and basic linear algebra.<br />
NumPy's efficiency and capabilities make it a cornerstone for many other data science libraries.<br />

# pandas (Python Data Analysis Library)
Built on top of NumPy, Pandas offers high-performance, easy-to-use data structures and data analysis tools.<br />
Its primary data structures are the Series (one-dimensional labeled array) and DataFrame (two-dimensional labeled data structure with columns of potentially different types).<br /> 
Pandas excels at data cleaning, transformation, and manipulation, making it indispensable for preparing data for analysis and visualization.<br />

# matplotlib
This is a comprehensive library for creating static, animated and interactive visualizations in Python.<br /> 
It provides a wide range of plotting functions, allowing users to create various types of charts and graphs, including line plots, scatter plots, bar charts, histograms and more.<br /> 
Matplotlib offers extensive customization options for controlling plot appearance and layout.<br />

# plotly
An open-source graphing library for creating interactive, web-based visualizations. 
Plotly enables the creation of a wide variety of interactive charts and graphs, including statistical, financial and scientific plots, as well as 3D graphs and maps. 
It is particularly useful for creating dynamic visualizations that can be embedded in web applications or displayed in Jupyter notebooks. 
Plotly Express, a high-level API within the Plotly ecosystem, simplifies the process of creating common plot types.

# networkx streamlit pyvis
NetworkX and Streamlit can be integrated to build interactive web applications for network analysis and visualization. <br />
NetworkX is a Python package specifically designed for the creation, manipulation, and study of complex networks, while Streamlit is an open-source framework that allows users to turn Python scripts into sharable web applications with minimal effort.<br />
pyvis is often used in conjunction with NetworkX and Streamlit to create interactive network visualizations.<br />
<br />Create a NetworkX graph:
- Define your network structure using NetworkX, including nodes and edges, and potentially adding attributes to them.
<br />Visualize the graph using Pyvis (or Matplotlib):
- Pyvis - Convert the NetworkX graph to a Pyvis network object, which can then be rendered as an interactive HTML file.
- Matplotlib - Use NetworkX's built-in drawing capabilities with Matplotlib to create static visualizations.
<br />Embed in Streamlit:
- Pyvis: Use st.components.v1.html to embed the generated Pyvis HTML content directly into your Streamlit application, making the network interactive within the web app.
- Matplotlib: Use st.pyplot() to display the Matplotlib-generated plot in your Streamlit application.
Add Streamlit widgets:
Incorporate Streamlit widgets like sliders, buttons, or file uploaders to allow users to interact with the network data, modify visualization parameters, or load new datasets.

# Python Example Workflow:

import streamlit as st
import networkx as nx
from pyvis.network import Network

# Create a simple NetworkX graph
G = nx.Graph()
G.add_edges_from([(1, 2), (2, 3), (3, 4), (4, 1)])

# Create a Pyvis network object
net = Network(notebook=True, height="750px", width="100%", bgcolor="#222222", font_color="white")
net.from_nx(G)

# Save the network to an HTML file
net.save_graph("pyvis_graph.html")

# Display the Pyvis graph in Streamlit
with open("pyvis_graph.html", "r") as f:
    html_content = f.read()
    st.components.v1.html(html_content, height=800)

st.write("This is an interactive network graph created with NetworkX, Pyvis, and Streamlit.")


# torch tqdm scikit-learn tslearn
These packages can be used together in various scenarios. For instance, tqdm can be used to monitor the training progress of deep learning models built with torch, while scikit-learn might be used for traditional machine learning tasks or as a component in a hybrid system alongside torch. tslearn then extends the machine learning capabilities to handle the unique characteristics of time series data, often integrating seamlessly with scikit-learn's ecosystem.

# torch (or PyTorch)
This is an open-source machine learning framework primarily used for deep learning and neural networks.<br />
It provides powerful tensor computation capabilities with GPU acceleration and a flexible automatic differentiation system (autograd) for building and training complex neural network architectures.<br />

# tqdm
This library provides fast, extensible progress bars for loops and iterables.<br />
It is used to visualize the progress of time-consuming operations in a clear and user-friendly manner within the terminal or notebooks.<br />

# scikit-learn
A comprehensive machine learning library offering a wide range of classical machine learning algorithms for tasks such as classification, regression, clustering, dimensionality reduction and model selection. It is known for its consistent API and ease of use for traditional machine learning tasks.<br />

# tslearn
This package specializes in machine learning tools for time series data. It builds upon scikit-learn, numpy and scipy, providing dedicated models and utilities for time series specific tasks like clustering, classification and regression as well as pre-processing and feature extraction for time series.<br />

