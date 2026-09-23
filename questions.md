

It sounds like this is for distributed databases specifically and not any distributed system?

There also seems to be shared disk and shared nothing distributed databases, which one is our focus?

Wouldn’t it be a better idea to start by making a database we can test this on?

-	Would be easier to see what we are supposed to do and also understand the data the LLM is  	storing. If we just simulate the logs and don’t have an actual database to test things on we don’t 	know if the idea works.

How do we make the database distributed?

What are all the types of logs we want to read? Just the database transaction logs?

Does anything like this already exists that we could use as a reference?

What can this do that non-generative recovery tools can’t and why should I use this instead of traditional recovery tool?

-	SQL servers do already seem to have non-generative recovery features and the transaction logs 	seem to be specifically made for them. In the right setting LLMs can find connections other 	tools can’t but are way more prone to error and therefore less robust and take more 	computing power than more traditional algorithms.

	- Even if LLM could be useful in some situations it would likely only be when there is huge 	amounts of data. In that case

		- How do we get to host large distributed databases?? That would probably cost a huge chunk of money we do not have
		- Even if we could do that just generating huge amounts of test data sounds like a huge waste 	of resources 

We can’t give LLM access to any sensitive data, how do we ensure this does not happen?

-	At least we can make it not read straight from the database and only the logs but in that case 	especially I wonder if there truly is any case where it can be better than just using the more 	traditional recovery 	tools.

Why are we storing the logs on .json files? Wouldn’t it be better to have the LLM read the actual logs? It sounds like we are just generating huge amounts of extra data when the logs can already take up a lot of space and .json takes even more space than a real database. If the plan is to simplify the actual logs how do we do that? Prehaps the idea is for the agent to give a simplification of that databases logs so it can discuss it with other agents who communicate with different databases? In that case it sounds like a better idea to write the agent a guide how to write a summary of the logs was it .json or .md document and check if the summary makes any sense. Prehaps we could even make the agent team up with traditional database recovery tools.

How are we planning to create database crashes so we can see if our agents can fix the issue?
-	We should also probably test this against traditional crash management tools to see if this does 	actually perform better.



I also hope that this idea is not too complicated for 5 point course even if we were able to solve all the issues. 
