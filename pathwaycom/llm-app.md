https://github.com/pathwaycom/llm-app.git

- takes embedding (documents) and creates a nearest neighbor index over it
	- one image or text document is converted into a vector (array of numbers) based on its characteristics and that vector is compared to other vectors in the model 
		- image characteristics include: shape, color, texture, and patterns
		- document characteristics include:  semantic meaning, contextual nuance, keywords + topics, & writing style + tone
	- contrast with an index in a SQL query, which is used to speed up retrieval of data that is already known to match

