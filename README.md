Lesson 1:

The first lesson explained how LangGraph enables developers to combine reliable control flows with LLM-based decision-making to build adaptive AI agents. 
It covers the foundations, memory, human oversight, and customization of these agents. It basically explained how LangGraph lessens the degradation of reliability on increasing agent's level of control. It then further explained the future modules.

Lesson 2: 

We learned how to make simple graphs, it was taught how to add nodes, edges and conditional edges and how to build the entire graphs.

 Code edit: I added another node, node4 and then connected that to the conditional edge, I used the path_map in this which allows us to properly connect more than 2 nodes.
 Link : [text](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/c5ebfcff424f5a1f0e920152893cec62a0e8aee2/simple-graph.ipynb)

 Lesson 3:

 LangGraph Studio was introduced in this video, although I am using Visual Studio Code.

Lesson 4:

We learn about how to use AI agents and use messages to send or invoke queries. We also learn about the concept of tools and how we can use them within our code in combination with AI models. We also learned about how to use messages as a state and learned about reducers to deal with issues regarding overriding state value which can help us handle how state updates are performed.

Code edit: I changed the initial messages in the chat_model section and made my own custom calls about Batman. I created another tool called modulus and called it throughout the rest of the code.

Link: [text](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/c5ebfcff424f5a1f0e920152893cec62a0e8aee2/chain.ipynb)

Lesson 5:

In this lecture, we were taught how to use tools in our graph nodes itself using built in function ToolNode. We were also taught tools_condition built in function acting as a conditional edge for tools.

Code Edit: I added more tools (add and sub), and tested calling them with slightly more complex language.
Link: [text](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/c5ebfcff424f5a1f0e920152893cec62a0e8aee2/router.ipynb)

Lesson 6: 

In this lecture we were taught the ReAct architecture, which allows the LLM to loop between reasoning and tool use, allowing us to use multiple tools and perform multi-step arithmetic.

Code Edit: Added 2 new tools, subtract and to_percentage and also tried 2 new prompts which involves multi level complex arithmetic demonstrating the ReAct architecture.
Link: [text](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/c5ebfcff424f5a1f0e920152893cec62a0e8aee2/agent.ipynb)

Lesson 7:

We used the MemorySaver function for persisitence. Basically we save whatever is in the previous output in memory and use it for further instances using the thread_id which stores graph states.

Code Edit: I added multiple interactions using the same thread_id, and then questioned the agent on the first calculation showing that the model is context-aware and remembers what it did earlier.
Link: [text](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/c5ebfcff424f5a1f0e920152893cec62a0e8aee2/agent-memory.ipynb)