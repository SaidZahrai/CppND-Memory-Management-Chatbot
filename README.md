# CPPND: Memory Management Chatbot

This is the third project in the [Udacity C++ Nanodegree Program](https://www.udacity.com/course/c-plus-plus-nanodegree--nd213), forked from
[the project repository](https://github.com/udacity/CppND-Memory-Management-Chatbot), where you can find more details about the project and specific tasks.

The code creates a dialogue box, which allows the user to move through a tree information built from nodes and edges in `answergraph.txt`. The project was started with a functioning code, but an intentional bug that would cause issue when the application was stopped. The project was to modify the code to use smart pointers for a better memory management. The work was divided into 5 tasks as described in [the project repository](https://github.com/udacity/CppND-Memory-Management-Chatbot). This repository presents the solution to the tasks. All changes and modifications in the code are made in the areas marked by

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

## Running the code

The code has been tested on Windows 10/WSL2 Ubuntu 20.04, with the below dependencies installed:

* cmake >= 3.11
* make >= 4.1 (Linux, Mac), 3.81 (Windows)
* gcc/g++ >= 5.4
* wxWidgets >= 3.0

but it should be runnable on other OSs. For information about how to install the dependencies on different OSs, please see
[the project repository](https://github.com/udacity/CppND-Memory-Management-Chatbot).

1. Clone this repo.
2. Make a build directory in the top level directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./membot`.

If everything goes well and you have the DISPLAY set correctly, you should see a window like below openning:

<p style="text-align:center;"><img src="images/chatbot_demo.png" style="max-width:20%;"></p>

Point with the cursor in the white textbox, and enter your question/keyword. 


