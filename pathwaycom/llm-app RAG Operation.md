https://github.com/pathwaycom/llm-app.git

### High Level Steps
1. user adds documents (eg a repo, code documentation, etc) to a prompt, which are sent to the Embedding Service that creates a vector out of each document plus the prompt 
2. the vectors are compared by the service and the original prompt is enhanced by the context of the documents
3. the enhanced prompt is sent to the GPT service for generated text that continues or responds to that prompt
4. if documentation does not speak to what is in the prompt, the prompt will not be enhanced or it will be in accurate
5. adding additional files to the documentation folder (locally or on s3), will automatically trigger the indexing service to keep your app in sync 
	- this will happen if a process puts a new file into a folder or appends new data to a Delta Lake table in your data lake as well
	- will happen if message comes over Kafka topic as well
		

### Lower Level Details
- takes embedding (documents) and creates a nearest neighbor index over it
	- one image or text document is converted into a vector (array of numbers) based on its characteristics and that vector is compared to other vectors in the model 
		- image characteristics include: shape, color, texture, and patterns
		- document characteristics include:  semantic meaning, contextual nuance, keywords + topics, & writing style + tone
	- contrast with an index in a SQL query, which is used to speed up retrieval of data that is already known to match
- query is embedded, nearest neighbors are retrieved, and an enhanced prompt is generated from the vector comparison by the embedding service and sent to the GPT service to answer the user
- In all cases of adding context, Pathway program reacts and reindexes the documents, effectively adding it to the local database; this replaces vector db
- pathway.stdlib.ml.nlp module functions are run to interact with LLMs
- we call it incremental computation when the RAG vector db table info is saved locally between runs of the ai bot (docs don't have to be resent to the embedding model again)
	- no extra api calls were made when the system was rebooted; the system reuses all previous results from previous run
- it is a microservice

> Note: read pathway docs on Louvain community detection graphs


