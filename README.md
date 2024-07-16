<body>
<img src = "https://github-vistors-counter.onrender.com/github?username=https://github.com/HeiderJeffer/MSc.-ETH-Zurich-Universit-della-Svizzera-Italiana-Semantic-Web" alt = "Visitors-Counter"/>
</body>


**ETH Zürich - Università della Svizzera Italiana**

**Faculty of Computer Science - Master in Artificial Intelligence**

**Thesis: Unraveling the Semantic Web: A Comprehensive Exploration**

**Developer: Heider Jeffer**

**Instructor: Prof. Mehdi Jazayeri**

**Assistant: Sasa Nesic**

**Speaker: Prof. Grigoris Anoniou**

Sure! Let's break down the key sections of the Semantic Web evolution and explain them with corresponding Python code examples. We'll use the RDFLib library in Python for handling RDF data and illustrate other concepts with additional code snippets.

### Introduction: Navigating the Evolution of the Semantic Web

The Semantic Web aims to embed semantics into the web, making it understandable by both humans and machines.

### The Semantic Web Framework: Principles, Collaboration, and Technologies

#### Design Principles and Collaborative Work

The Semantic Web is structured around design principles like interoperability and extensibility, built by collaborative efforts among various organizations and working groups.

### Technological Foundations: RDF, Data Interchange, and Notations

#### Example: Creating RDF Data with RDFLib

```python
from rdflib import Graph, Literal, RDF, URIRef
from rdflib.namespace import FOAF

# Create a new graph
g = Graph()

# Create an identifier for a person
person_uri = URIRef("http://example.org/people/JohnDoe")

# Add triples using store's add method
g.add((person_uri, RDF.type, FOAF.Person))
g.add((person_uri, FOAF.name, Literal("John Doe")))
g.add((person_uri, FOAF.mbox, URIRef("mailto:johndoe@example.org")))

# Print out the graph in RDF/XML format
print(g.serialize(format='xml').decode('utf-8'))
```

### Semantic Publishing: A Revolutionary Leap in Scientific Dissemination

Semantic publishing allows real-time dissemination of scientific data on the internet.

### Bridging the Human-Computer Divide: Semantic Web's Vision

The Semantic Web aims to make web information comprehensible to machines, automating tasks like finding and combining information.

### Integration Across Applications: Semantic Web's Role in Enterprise Information Systems

The Semantic Web integrates diverse content and applications, facilitating interconnected enterprise systems.

### Clarifying Terminological Confusion: Semantics, Metadata, Ontologies, and More

Understanding the terms used in the Semantic Web is crucial. Here's a basic example of how ontologies are defined:

#### Example: Defining an Ontology in OWL

```python
from rdflib import Graph, Namespace
from rdflib.namespace import RDF, OWL

# Create a graph and bind namespaces
g = Graph()
EX = Namespace("http://example.org/")

g.bind("ex", EX)

# Define a class in OWL
g.add((EX.Person, RDF.type, OWL.Class))
g.add((EX.Employee, RDF.type, OWL.Class))
g.add((EX.Employee, OWL.subClassOf, EX.Person))

# Define a property
g.add((EX.hasName, RDF.type, OWL.DatatypeProperty))
g.add((EX.hasName, RDF.domain, EX.Person))
g.add((EX.hasName, RDF.range, EX.Literal))

# Print the ontology in Turtle format
print(g.serialize(format='turtle').decode('utf-8'))
```

### HTML Limitations: Unveiling the Divide Between Documents and Data

HTML is limited in representing both human-readable documents and machine-processable data, emphasizing the need for solutions like RDF.

### Semantic Web's Language of Data: RDF, OWL, XML, and the Giant Global Graph

#### Example: Creating Linked Data with RDF

```python
# Continuing from previous RDFLib example
g.add((person_uri, FOAF.knows, URIRef("http://example.org/people/JaneDoe")))

# Print the graph with the new data link
print(g.serialize(format='turtle').decode('utf-8'))
```

### Navigating the Challenges: Vastness, Vagueness, Uncertainty, Inconsistency, and Deceit

#### Vastness: Managing Large Data

Handling vast amounts of data requires efficient storage and retrieval mechanisms.

#### Vagueness: Fuzzy Logic Example

```python
# Example of simple fuzzy logic using skfuzzy library
import numpy as np
import skfuzzy as fuzz
import matplotlib.pyplot as plt

# Define fuzzy sets and rules for the concept of "tall"
height = np.arange(0, 201, 1)
short = fuzz.trimf(height, [0, 0, 150])
tall = fuzz.trimf(height, [150, 200, 200])

# Visualize the fuzzy sets
plt.figure()
plt.plot(height, short, 'r', linewidth=1.5, label='Short')
plt.plot(height, tall, 'b', linewidth=1.5, label='Tall')
plt.title('Fuzzy membership functions for height')
plt.xlabel('Height (cm)')
plt.ylabel('Membership degree')
plt.legend()
plt.show()
```

#### Uncertainty: Probabilistic Reasoning Example

```python
# Example of Bayesian inference using PyMC3
import pymc3 as pm
import numpy as np

# Define the probabilistic model
with pm.Model() as model:
    # Prior for unknown parameter
    theta = pm.Beta('theta', alpha=1, beta=1)
    
    # Likelihood
    data = np.array([1, 0, 1, 1, 0, 1, 0, 1])
    obs = pm.Bernoulli('obs', p=theta, observed=data)
    
    # Posterior inference
    trace = pm.sample(1000, return_inferencedata=False)

# Summarize the posterior
pm.summary(trace)
```

#### Inconsistency: Paraconsistent Reasoning Example

Handling inconsistencies requires advanced reasoning techniques beyond simple logic.

#### Deceit: Ensuring Information Integrity with Cryptography

```python
from cryptography.fernet import Fernet

# Generate a key for encryption
key = Fernet.generate_key()
cipher_suite = Fernet(key)

# Encrypt a message
message = b"A secret message"
cipher_text = cipher_suite.encrypt(message)

# Decrypt the message
plain_text = cipher_suite.decrypt(cipher_text)
print(plain_text.decode('utf-8'))
```

### Conclusion: Charting the Future of the Semantic Web

The Semantic Web is reshaping how we interact with web information, paving the way for a dynamic, interconnected knowledge ecosystem.

This code illustrates the concepts discussed in the text, providing practical examples to help understand the evolution and components of the Semantic Web.
