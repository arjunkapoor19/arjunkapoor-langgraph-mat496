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

![alt text](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8d6d9e968ebf1f09fa32a015038674d58ccb4fa4/images/local-lang-trace.png "LangGraph Stack - trim")

[Link](https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8d6d9e968ebf1f09fa32a015038674d58ccb4fa4/MODULE%202/chatbot-external-memory.ipynb)

**MODULE 3** 

Lesson 1:

I learned what streaming is, how LangChain provides first-class streaming support, how to use .stream and .astream, the difference between streaming modes like updates and values, and how to use .astream_events for token-level event streaming.

Code edit:

Changed name from Lance to Arjun, changed team from 49ers to FC Barcelona.

Lesson 2:

I learned how breakpoints enable human-in-the-loop workflows by pausing execution for approval, debugging, or editing; how streaming with None and a thread ID resumes execution from the current state; and how to incorporate user choices so the graph continues based on input

Code edit: 

Added another modulus tool, used it on 10 and 4, curiously in the output the memory still had the addition of 2 and 3 as well as the new modulus operation and printed both cumulatively in the output.

![alt text]("/Users/arjunkapoor/Documents/Code/LLM/arjunkapoor-langgraph-mat496/images/Module 3, Lesson 3.png " "LangGraph Stack - trim")

Lesson 3:

I learned how to actually intepret human feedback and use it to edit graph state at the breakpoint and also use graph.get_state(thread) and graph.update_state(thread,updates) after interrupting the graph.

Code edit:

Again added the modulus tool and used it on 10 and 6 and also, entered human input. Also made a small math quiz bot which randomises questions and tells the user if the answers are correct or not.

Lesson 4:

I learned how to override node interrupts based on conditions.

Code edit:

Changed code and learned through that.

Lesson 5:

I learned that I can view all past graph execution states using get_state_history(), each identified by a unique checkpoint_id. I can restore and replay execution from any point by extracting its config and passing it back into graph.stream. I also learned about forking, which allows branching from a previous state to explore new paths without affecting the original execution, by creating and using a new fork_config.

Code edit:

Changed code throughout and added an example of forking at the end.

**MODULE 4**

Lesson 1:

I learned that errors may occur when a state key receives multiple values simultaneously from parallel nodes. To address this, LangGraph applies reducers, which merge parallel updates before moving to the next non-parallel state in the execution graph. By defining a custom reducer, we can control how these values are combined—for example, ensuring they are sorted or processed in a specific order—preventing state conflicts and maintaining predictable behavior when updating shared keys in parallel workflows.

Code edit:

Made a tavily example with 3 parallelization nodes.

![alt text]("https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob 8684c054368420130c9a871e8fb551f6629729c3/images/Module%204%2C%20Lesson%201.png" "Module 4 Lesson 1")


Lesson 2:

I learned that subgraphs are reusable portions of a larger graph that maintain their own internal state, allowing modular and isolated execution; they can be integrated into parent graphs to build more complex workflows, and reducers are used to prevent state collisions when multiple subgraphs update shared keys simultaneously.

Code edit:

Added my own example at the end

Lesson 3:

I learned about subgraphs, their states and what are their uses,how to add subgraphs to parent graphs and using reducers to prevent collisions between subgraphs.

![alt text]("https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8684c054368420130c9a871e8fb551f6629729c3/images/Module%203%2C%20Lesson%203.png" "Module 4 Lesson 3")

Code edit:

Added my own example at the end.

Lesson 4:

I learned to integrate all LangGraph concepts covered so far into a single workflow, using multiple tools together and generating a summarized Markdown report from multiple inputs.

Code Edit:

Added a code to print the number of analysts in the final report.

![alt text]("https://github.com/arjunkapoor19/arjunkapoor-langgraph-mat496/blob/8684c054368420130c9a871e8fb551f6629729c3/images/Module%204%2C%20Lesson%204.png" "Module 4 Lesson 4")