# Evaluation Frameworks

## LangSmith

This toolkit is not just a simple debugger. It is designed as a comprehensive environment that lets developers examine an application’s responses, the intermediate steps it takes, and the entire workflow from start to finish.

In practice, this means we can move beyond surface-level error checking. Instead, we can reconstruct the entire reasoning chain of the system, verifying not only whether the final output is correct, but also whether each decision alýng the way is logically consistent.

The added advantage is that the tool is tightly integrated with both UI (user interface) and SDK (software Development Kit) layers. This dual perspective provides insight into how abstract code execution translates into concrete, user-facing actions and underlying API calls.

So, whenever we are debugging a multi-step or complex process (for instance, AI workflow, a chain of API requests, or an interactive system) we can rely on this toolkit to uncover hidden issues, trace dependencies, and ensure the workflow behaves as intended.

Let's think of it as a full-spectrum diagnostic lens: it not only shows us the end result, but also the hidden mechanisms that produced it.



```
# Basic Example
# Connects to LangSmith via Client().
# Defines a very simple chain: prompt -> model.
# Wraps execution in trace_run so every step is recorded in LangSmith’s UI.
# When we run it, we’ll see:
# The input (Hello, how are you?)
# The generated output (French translation)
# Each intermediate step traced in your LangSmith dashboard.

from langsmith import Client
from langchain_openai import ChatOpenAI
from langchain.prompts import ChatPromptTemplate

# Initialize LangSmith client (LANGSMITH_API_KEY is set in env file)
client = Client()

# 
# Define a simple LangChain model
model = ChatOpenAI(model="gpt-3.5-turbo")

# Creating simple prompt
prompt  = ChatPromptTemplate.from_messages([
	(
		"system": "You are a helpful assistant."
	),
	(
		"human": "Translate this into Turkish: {text}"
	),
  ])

# Bind the model to the prompt
chain = prompt | model

# Run the chain with LangSmith tracing
with client.trace_run("Translation Example"):
	response = chain.invoke({"text": "Hello, how are you?"})

print("AI responsen: ", response.content)





"""
Common alternatives we could use

Anthropic (Claude models)

from langchain_anthropic import ChatAnthropic
model = ChatAnthropic(model="claude-3-opus-20240229")


Cohere

from langchain_cohere import ChatCohere
model = ChatCohere(model="command-r-plus")


Mistral / Mixtral

from langchain_mistralai import ChatMistralAI
model = ChatMistralAI(model="mistral-large-latest")


Hugging Face Hub models

from langchain_huggingface import HuggingFaceEndpoint
model = HuggingFaceEndpoint(repo_id="tiiuae/falcon-7b-instruct")


Azure OpenAI (Microsoft’s hosted version of OpenAI)

from langchain_openai import AzureChatOpenAI
model = AzureChatOpenAI(
    deployment_name="gpt-35-turbo",
    model="gpt-35-turbo"
)
"""

```

### RESOURCES
https://www.datacamp.com/tutorial/introduction-to-langsmith

https://github.com/langchain-ai/langsmith-cookbook


## Google ADK (Agent Development Kit)
GoogleADK Eval is framework that provides built-in evaluation features specifically tailored for agents within Google's AI ecosystem. Unlike generic testing tools, it leverages structured test files and predefined schemas, which make it easier to create repeatable, standardized benchmarks for agent performance.

The primary purpose is to test enterprise-grade agents that are developed insdie Google's broader AI tool ecosystem. Because enterprise agents often handle complex, multi-turn interactions and integrate with diverse data sources, evaluation cannot simply be about checking whether the final answer is "r,ght or wrong". Instead, ADK Eval focuses on assessing the quality, reliability, and compliance of agent behavior across different sceneraios.

In practice, organizations can use ADK Eval to:
	- Define structed evaluation cases through schema-based test files.
	- Automatically run these tests against their enterprise agents.
	- Obtain consistent insights whether the agent meets required business, security, and user experince standards.

So, we can think of Google ADK eval as a specialized testing harness that ensures enterprise AI agents behave predictably, meet organizational standards, and integrate seamlessly with the rest of Google's AI ecosystem.




### RESOURCES
https://codelabs.developers.google.com/onramp/instructions?hl=tr#0

https://google.github.io/adk-docs/get-started/

https://developers.googleblog.com/en/agent-development-kit-easy-to-build-multi-agent-applications/

https://github.com/google/adk-python

https://google.github.io/adk-docs/

https://cloud.google.com/vertex-ai/generative-ai/docs/agent-development-kit/quickstart





# RESOURCES

https://www.linkedin.com/posts/rakeshgohel01_evaluation-is-what-separates-great-ai-agents-activity-7362464250545504256-IEKO?utm_source=share&utm_medium=member_desktop&rcm=ACoAADCwKaABkjIKZVprcgUmTUq_EfIe6r7qpFE
