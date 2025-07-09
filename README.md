# study_links
Some training for python packages
#numpy pandas matplotlib plotly

#networkx streamlit pyvis
NetworkX and Streamlit can be integrated to build interactive web applications for network analysis and visualization. NetworkX is a Python package specifically designed for the creation, manipulation, and study of complex networks, while Streamlit is an open-source framework that allows users to turn Python scripts into sharable web applications with minimal effort.
pyvis is often used in conjunction with NetworkX and Streamlit to create interactive network visualizations.
Create a NetworkX graph:
Define your network structure using NetworkX, including nodes and edges, and potentially adding attributes to them.
Visualize the graph using Pyvis (or Matplotlib):
Pyvis: Convert the NetworkX graph to a Pyvis network object, which can then be rendered as an interactive HTML file.
Matplotlib: Use NetworkX's built-in drawing capabilities with Matplotlib to create static visualizations.
Embed in Streamlit:
Pyvis: Use st.components.v1.html to embed the generated Pyvis HTML content directly into your Streamlit application, making the network interactive within the web app.
Matplotlib: Use st.pyplot() to display the Matplotlib-generated plot in your Streamlit application.
Add Streamlit widgets:
Incorporate Streamlit widgets like sliders, buttons, or file uploaders to allow users to interact with the network data, modify visualization parameters, or load new datasets.

#Python Example Workflow:


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


torch tqdm scikit-learn tslearn
These packages can be used together in various scenarios. For instance, tqdm can be used to monitor the training progress of deep learning models built with torch, while scikit-learn might be used for traditional machine learning tasks or as a component in a hybrid system alongside torch. tslearn then extends the machine learning capabilities to handle the unique characteristics of time series data, often integrating seamlessly with scikit-learn's ecosystem.

torch (or PyTorch)
This is an open-source machine learning framework primarily used for deep learning and neural networks. It provides powerful tensor computation capabilities with GPU acceleration and a flexible automatic differentiation system (autograd) for building and training complex neural network architectures.

tqdm
This library provides fast, extensible progress bars for loops and iterables.
It is used to visualize the progress of time-consuming operations in a clear and user-friendly manner within the terminal or notebooks.

scikit-learn
A comprehensive machine learning library offering a wide range of classical machine learning algorithms for tasks such as classification, regression, clustering, dimensionality reduction and model selection. It is known for its consistent API and ease of use for traditional machine learning tasks.

tslearn
This package specializes in machine learning tools for time series data. It builds upon scikit-learn, numpy and scipy, providing dedicated models and utilities for time series specific tasks like clustering, classification and regression as well as pre-processing and feature extraction for time series.

