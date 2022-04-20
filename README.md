# CPPND: Memory Management Chatbot

This is the third project in the [Udacity C++ Nanodegree Program](https://www.udacity.com/course/c-plus-plus-nanodegree--nd213), forked from
[the project repository](https://github.com/udacity/CppND-Memory-Management-Chatbot), where you can find more details about the project and specific tasks.

The code creates a dialogue box, which allows the user to move through a tree information built from nodes and edges in `answergraph.txt`. All changes in the code are in the areas marked by

```
    //// STUDENT CODE
    ////

    // Code added or modified...

    ////
    //// EOF STUDENT CODE
}
```

except the below method in lines 39 to 42 in `graphnode.cpp`

```
void GraphNode::AddEdgeToChildNode(std::unique_ptr<GraphEdge> edge)
{
    _childEdges.push_back(std::move(edge));
}
```

which originally was

```
void GraphNode::AddEdgeToChildNode(GraphEdge *edge)
{
    _childEdges.push_back(edge);
}
```

This change was necessary to satisfy task 4 and allow a node exclusively own its child edges.

The ChatBot code creates a dialogue where users can ask questions about some aspects of memory management in C++. After the knowledge base of the chatbot has been loaded from a text file, a knowledge graph representation is created in computer memory, where chatbot answers represent the graph nodes and user queries represent the graph edges. After a user query has been sent to the chatbot, the Levenshtein distance is used to identify the most probable answer. The code is fully functional as-is and uses raw pointers to represent the knowledge graph and interconnections between objects throughout the project.

In this project you will analyze and modify the program. Although the program can be executed and works as intended, no advanced concepts as discussed in this course have been used; there are currently no smart pointers, no move semantics and not much thought has been given to ownership or memory allocation.

Your goal is to use the course knowledge to optimize the ChatBot program from a memory management perspective. There are a total of five specific tasks to be completed, which are detailed below.

## Running the code

1. Clone this repo.
2. Make a build directory in the top level directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./membot`.

If everything goes well and you have the DISPLAY set correctly, you should see a window like below openning:

<p style="text-align:center;"><img src="images/chatbot_demo.png" style="max-width:20%;"></p>

Point with the cursor in the white textbox, and enter your question/keyword. 

The code has been tested on Windows 10/WSL2 with the below dependencies installed:

* cmake >= 3.11
* make >= 4.1 (Linux, Mac), 3.81 (Windows)
* gcc/g++ >= 5.4
* wxWidgets >= 3.0

but it should be runnable on other OSs. For information about how to install the dependencies on different OSs, please see
[the project repository](https://github.com/udacity/CppND-Memory-Management-Chatbot).
