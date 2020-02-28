1. Introduction
===============

C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\01.Introduction.mp4

2. Program Schematics
======================
Below are the program schematics from the two screencasts above. You may want to download and save these for future reference as you are working on the code.

C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\02.ProgramSchematic-1.mp4
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\02.ProgramSchematic-2.mp4

3. Membot Knowledge Base
=======================

C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\03.KnoledgeBase.mp4


4. Project Tasks Overview
==========================

C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\04.Tasks.mp4


There will be a more detailed discussion of each of these tasks coming up, but first, we will discuss each of the files in the Membot source code.

5. Code Walkthrough
====================

Each of the following screencasts is a detailed overview of the code for one or more files in the project repository. If you haven't seen the repo already, you can find the repo here. You may want to download the code to your local machine or open the repo in another browser window to follow along with the screencasts below.

chatgui.h
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\06 Walkthrough - Chatgui.H.mp4

chatgui.cpp
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\07 Walkthrough - Chatgui.Cpp.mp4

chatlogic.cpp
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\08 Walkthrough - Chatlogic.H.mp4

graphnode.h
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\10 Walkthrough - Graphnode.H.mp4

graphnode.cpp
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\11 Walkthrough - Graphnode.Cpp.mp4

graphedge
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\12 Walkthrough - Graphedge.mp4

chatbot.h
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\13 Walkthrough - Chatbot.H.mp4

chatbot.cpp
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\14 Walkthrough - Chatbot.Cpp.mp4

6. Tasks Details
================

Debug Warm-Up Task
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\15 Debug Warm Up Task.mp4

Task 1 : Exclusive Ownership 1
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\16 Task 1.mp4

In file chatgui.h / chatgui.cpp, make _chatLogic an exclusive resource to class ChatbotPanelDialog using an appropriate smart pointer. Where required, make changes to the code such that data structures and function parameters reflect the new structure.

Task 2 : The Rule Of Five
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\17 Task 2.mp4

In file chatbot.h / chatbot.cpp, make changes to the class ChatBot such that it complies with the Rule of Five. Make sure to properly allocate / deallocate memory resources on the heap and also copy member data where it makes sense to you. In each of the methods (e.g. the copy constructor), print a string of the type „ChatBot Copy Constructor“ to the console so that you can see which method is called in later examples.

Task 3 : Exclusive Ownership 2
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\18 Task 3.mp4

In file chatlogic.h / chatlogic.cpp, adapt the vector _nodes in a way that the instances of GraphNodes to which the vector elements refer are exclusively owned by the class ChatLogic. Use an appropriate type of smart pointer to achieve this. Where required, make changes to the code such that data structures and function parameters reflect the changes. When passing the GraphNode instances to functions, make sure to not transfer ownership and try to contain the changes to class ChatLogic where possible.

Task 4 : Moving Smart Pointers
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\19 Task 4.mp4

In files chatlogic.h / chatlogic.cpp and graphnodes.h / graphnodes.cpp change the ownership of all instances of GraphEdge in a way such that each instance of GraphNode exclusively owns the outgoing GraphEdges and holds non-owning references to incoming GraphEdges. Use appropriate smart pointers and where required, make changes to the code such that data structures and function parameters reflect the changes. When transferring ownership from class ChatLogic, where all instances of GraphEdge are created, into instances of GraphNode, make sure to use move semantics.

Task 5 : Moving the ChatBot
C:\Users\ahmed\OneDrive\Desktop\MemMang\Project\20 Task 5.mp4

In file chatlogic.cpp, create a local ChatBot instance on the stack at the bottom of function LoadAnswerGraphFromFile. Then, use move semantics to pass the ChatBot instance into the root node. Make sure that ChatLogic has no ownership relation to the ChatBot instance and thus is no longer responsible for memory allocation and deallocation. Note that the member _chatBot remains so it can be used as a communication handle between GUI and ChatBot instance. Make all required changes in files chatlogic.h / chatlogic.cpp and graphnode.h / graphnode.cpp. When the program is executed, messages on which part of the Rule of Five components of ChatBot is called should be printed to the console. When sending a query to the ChatBot, the output should look like the following:

ChatBot Constructor
ChatBot Move Constructor
ChatBot Move Assignment Operator
ChatBot Destructor
ChatBot Destructor 

