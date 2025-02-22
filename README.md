# OpenAI Instructor
Open AI is a great tool to fetch answers of puzzling questions. It can be used to answer questions for both personal and professional settings.
Be it questions related to diagnosis of symptoms of mental health, places to visit in Bangalore or as a corporate classifying customer complaints 
into different categories, using RAG for augmenting answers to quries on your in-house documents or identifying the ticketing category to which it belongs. 

The problem is when you ask Open AI, it provides you the response in a structured or most of the time unstructured manner. This is often unpredictable
and the response does not meet the desired standards. For eg, lets say you want to classify a document into various categories. And you give the prompt to 
OpenAI as "I want to classify the text into a ticket category. The list of ticket categories are Billing, Customer Experience, Goods and Services. 
The text is : "I have an issue with payment of my pending bills". "

No doubt, Open AI will identify this complaint as "Billing" issue. But when it gives the response, the response can be vary as you pass the request again and again.
For ex, the response can vary each time from "Billing","This is a billing issue","Billing issue". This variablity in response makes it difficult to index the complaint
for further use. Then what would be the best solution here? 
Perhaps, Open AI categorizes the complaint rightly as Billing, but the best thing would be to constraint the response to just "Billing".

The question is how do we do this?
We use a library called Instructor which is a package under Pydantic. Instructor as the name suggests instructs OpenAI to give response in a certain way. 
It patches with OpenAI and when the request is sent to OpenAI, the instructor asks OpenAI to reply in a specific format. Then how this specific format is decided?
We create a class response_model which includes all the categories needed to be predicted by the model. 
