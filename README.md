# 13-Pathway-Ideas

## Domain Selection :-
I selected my domain as Cricket, the chat model wtih the helps of agents will be able to get information about matches, get latest news, do some analytics (like comparing between the players), will be able to book and cancel tickets.

The reason behind this domain selection is that cricket is a field in which we can have vast variety of streaming data to be integrated with Pathway pipeline, and can build up various agents for tackling different tasks. 

## Swarm using Gemini Model :-
I made a demo version of my multi-agent system. Of course it doesn't work, I tried to implement it using Swarm and integrating it with google-gemini model but I believe that gemini was getting difficulty in handling complex agents. I tried implementing simple agents and they were working ok. Overall, it has some missing features: 
- I didn't made context variables features, as GenerativeModel() takes function directly as input, so its difficult to create a function whose parameters can be changed to remove context variables. But later on I came to know that I could have utilised LLMChat module which can take json form of function and its parameters can be changed to remove context_variables and then pass it to model, so that model don't have to worry about context variables
- I didn't implemented stream chat feature because of lack of time
- Model get stuck in a loop if I try to put a loop in model doing function call and then again feeding the result of call to model (as what it has been done in original Swarm repo.) until model converges to some final result. Gemini model was either taking too long to converge or it's never converging at all, it was calling the same function again and again. So, I removed the loop and restricted the model to call functions only once, So they cannot go throught their function return and do something with it.
