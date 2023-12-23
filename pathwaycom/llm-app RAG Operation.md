https://github.com/pathwaycom/llm-app.git

### High Level Steps
1. user adds documents (eg a repo, code documentation, etc) to a prompt, which are sent to the Embedding Service that creates a vector out of each document plus the prompt 
2. the vectors are compared by the service and the original prompt is enhanced by the context of the documents
3. the enhanced prompt is sent to the GPT service for generated text that continues or responds to that prompt

### Lower Level Details
- takes embedding (documents) and creates a nearest neighbor index over it
	- one image or text document is converted into a vector (array of numbers) based on its characteristics and that vector is compared to other vectors in the model 
		- image characteristics include: shape, color, texture, and patterns
		- document characteristics include:  semantic meaning, contextual nuance, keywords + topics, & writing style + tone
	- contrast with an index in a SQL query, which is used to speed up retrieval of data that is already known to match
