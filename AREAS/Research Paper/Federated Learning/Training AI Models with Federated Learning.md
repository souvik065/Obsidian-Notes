

All AI Application like Chatbots, Recommendation Systems and Spam Filters, they are all very data hungry and they have been fed tons of examples, which they use to learn their specific task to build and AI model.

Federated Learning turns this process on its head. Instead of bringing the data to the model, we take the model to the data.

Think every device, like a smartphone or a laptop or a server, it has its own local version of a model.
And this model learns from the data right there on the device itself.

Now, after the model has learned from the local data, it sends only the model updates back to the central server, not the actual raw data.

And then that server aggregates all of these updates from all the devices to create what is called the global model.



# Why bother with this Lebel of Decentralization ?

This concept was first introduced by Google in 2016 when global attention was focused on the use and misuse of personal data Concerns about data privacy and security.

Centralized AI training methods giving birth to federated learning.

#### **Example :-**
Let's imagine a scenario involving a group of companies that want to collaborate on building a model to predict market trends.
But each company has sensitive sales data they they want to keep private so each company has access to an initial baseline predictive global model.

- And  this global model  resides on centralized server.
- This  iterative process continues with each company refining the model based on that private data and sharing only the model updates.
- Over time the model becomes increasingly accurate at predicting market trends, even though no company had to share this sensitive data.


## **Conclusion:**

Each company benefits from the collective intelligence of the group while maintaining their data privacy. That is the essence of the federated learning, **allowing for collaborative learning** from shared model updates while keeping the actual data distributed and private.


## **Three Flavors of Federated Learning**

1. Horizontal Federated Learning
	- Horizontal Federated Learning describes the forecasting model
2. Vertical Federated Learning
	- Instead of using similar datasets, we're dealing with complementary data, using movies and book reviews, for predicting someone's music preferences.
3. Federated Transfer Learning
	- Here we start with a model that's already been trained to do one task and then adapt it do something slightly different. 

**Note :-**
Consider the health care industry where federated learning allows medical institution to collaboratively train their models on their sensitive data without sharing the medical records.

# Cons 
1. Risk of Inference Attack
	- Where adversaries may try to extract information about the data from the shared model updates when we put them up there


