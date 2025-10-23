I have switched to using gpt-4o-mini instead of gpt-4o due to credit constraints.

**MODULE 1**

Lesson 1:

The first lesson explained how LangGraph enables developers to combine reliable control flows with LLM-based decision-making to build adaptive AI agents. 
It covers the foundations, memory, human oversight, and customization of these agents. It basically explained how LangGraph lessens the degradation of reliability on increasing agent's level of control. It then further explained the future modules.

Lesson 2: 

We learned how to make simple graphs, it was taught how to add nodes, edges and conditional edges and how to build the entire graphs.

 Code edit: I added another node, node4 and then connected that to the conditional edge, I used the path_map in this which allows us to properly connect more than 2 nodes.
[Link](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/c5ebfcff424f5a1f0e920152893cec62a0e8aee2/simple-graph.ipynb)

 Lesson 3:

 LangGraph Studio was introduced in this video, although I am using Visual Studio Code.

Lesson 4:

We learn about how to use AI agents and use messages to send or invoke queries. We also learn about the concept of tools and how we can use them within our code in combination with AI models. We also learned about how to use messages as a state and learned about reducers to deal with issues regarding overriding state value which can help us handle how state updates are performed.

Code edit: I changed the initial messages in the chat_model section and made my own custom calls about Batman. I created another tool called modulus and called it throughout the rest of the code.

[Link](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/c5ebfcff424f5a1f0e920152893cec62a0e8aee2/chain.ipynb)

Lesson 5:

In this lecture, we were taught how to use tools in our graph nodes itself using built in function ToolNode. We were also taught tools_condition built in function acting as a conditional edge for tools.

Code Edit: I added more tools (add and sub), and tested calling them with slightly more complex language.
[Link](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/c5ebfcff424f5a1f0e920152893cec62a0e8aee2/router.ipynb)

Lesson 6: 

In this lecture we were taught the ReAct architecture, which allows the LLM to loop between reasoning and tool use, allowing us to use multiple tools and perform multi-step arithmetic.

Code Edit: Added 2 new tools, subtract and to_percentage and also tried 2 new prompts which involves multi level complex arithmetic demonstrating the ReAct architecture.
[Link](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/c5ebfcff424f5a1f0e920152893cec62a0e8aee2/agent.ipynb)

Lesson 7:

We used the MemorySaver function for persisitence. Basically we save whatever is in the previous output in memory and use it for further instances using the thread_id which stores graph states.

Code Edit: I added multiple interactions using the same thread_id, and then questioned the agent on the first calculation showing that the model is context-aware and remembers what it did earlier.
[Link](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/c5ebfcff424f5a1f0e920152893cec62a0e8aee2/agent-memory.ipynb)

**MODULE 2** 

Lesson 1:

Learned how to define and manage states, also learned how to define a state schema in LangGraph using TypedDict.
Also learned how to manage state schema using python's dataclasses. Learned the Pydantic library to validate types and checked if we are using correct values using Pydantic at runtime.

Code Edit:
Added another state, neutral, also changed the probability from 1/2 to 1/3 in all the respective implementations.

[Link](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8d6d9e968ebf1f09fa32a015038674d58ccb4fa4/MODULE%202/state-schema.ipynb)

Lesson 2:

Learned how updating the same value at multiple places runs us into problems and how reducers help us in resolving overwriting of state. Learned how operator.add helps us in forming concatenated lists. Learned how to use custom reducers to handle unaddresses issues.Learned about add_messages reducer and also message removal by id.

Code edit: Instead of giving state['foo'] + 1, changed it to state['foo'] * 3, now returning 3 instead. In messages, changed name from Lance to Arjun and instead of asking for information of marine biology, now asking for information on Batman.

[Link](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8d6d9e968ebf1f09fa32a015038674d58ccb4fa4/MODULE%202/state-reducers.ipynb)

Lesson 3:

Learned about private states and their role in the intermediate working of the graph. Learned how input and output is manipulated by filtering keys.

Code edit: 

Changed state['baz'] + 1 to state['baz'] * 3 and got the output {'foo': 9} instead of {'foo': 3}. Changed name to Arjun from Lance and also added 'see you!', in the message hence getting output {'answer': 'bye Arjun, see you!'}.

[Link](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8d6d9e968ebf1f09fa32a015038674d58ccb4fa4/MODULE%202/multiple-schemas.ipynb)

Lesson 4:

Learned how to handle long chatbot conversations in LangGraph by using message filtering and trimming techniques. Filtering helped remove older messages, while trimming allowed to control the total number of tokens. Also explored LangSmith tracing to observe how the model was being called and executed.

![alt text](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8d6d9e968ebf1f09fa32a015038674d58ccb4fa4/images/trim-lang-trace.png "LangGraph Stack - trim")


Code edit:

Changed from ocean mammals to birds, told the model I know about cuckoos then asked the model about flamingos further using filtering.


[Link](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8d6d9e968ebf1f09fa32a015038674d58ccb4fa4/MODULE%202/trim-filter-messages.ipynb)


Lesson 5:

Learned how to generate summaries of the ongoing conversation without changing the current context. Also avoided using filters and trimming. Learned memorysaver and thread ids.

Code edit:

Changed name from Lance to Arjun, instead of liking the 49ers, I told the AI I like FC Barcelona, one of my favourite football teams, and prompted a question about the team's star young player Lamine Yamal.

![alt text](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8d6d9e968ebf1f09fa32a015038674d58ccb4fa4/images/memory-lang-trace.png "LangGraph Stack - trim")


[Link](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8d6d9e968ebf1f09fa32a015038674d58ccb4fa4/MODULE%202/chatbot-summarization.ipynb)


Lesson 6:

Learned how to build chatbots with summarization capabilities, key highlight being we used an external memory using a sqlite database and checkpointer. Chatbot stored conversations in local database allowing us to pick off even after restarting notebook.

Code edit:

Changed name from Lance to Arjun, changed message to from 49ers to I like FC Barcelona. Asked how many UCLs we have in langgraph studio.

[Link](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8d6d9e968ebf1f09fa32a015038674d58ccb4fa4/MODULE%202/chatbot-external-memory.ipynb)

![alt text](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8d6d9e968ebf1f09fa32a015038674d58ccb4fa4/images/local-lang-trace.png "LangGraph Stack - trim")


