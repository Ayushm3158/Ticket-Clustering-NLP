# Ticket-Clustering-NLP 🤖
AI model using NLP and K-Means clustering to automatically categorize customer support tickets for rapid routing and enhanced product insights.

🎯 Project Goal
This project demonstrates an AI model designed to automatically categorize unstructured customer support ticket text. This capability is the foundational step for automated ticket triage, which is crucial for rapid issue resolution and providing actionable data insights to product teams.

The Task: Group the following sample tickets:

"I forgot my password, how to reset it?"

"I can't log in, as password is incorrect."

"How to see leave balance?"

Resulting Groups:

Account Access (Authentication)

Information Request (HR/Leave)

🛠️ Technical Approach
The solution employs a standard machine learning pipeline for text classification:

1. Natural Language Processing (NLP)
Method: TF-IDF (Term Frequency-Inverse Document Frequency) is used to convert the raw, human-written text into numerical vectors. This process weights unique, important words ("password," "leave") while filtering out common, less important "stop words" (like "the" or "is").

2. Unsupervised Learning (Clustering)
Model: K-Means Clustering is used. Since the initial sample tickets are unlabeled, clustering is the appropriate unsupervised technique to discover the natural groupings based on the content of the tickets.

Parameter: The model is initialized with K=2 clusters to match the two distinct issue types identified (account access vs. specific information queries).

💡 Alignment with Job Requirements
This model directly addresses multiple requirements outlined in the job description:

1. Work on AI Models that Provide Solutions (Job Point #2)
The instant categorization enables automated workflows:

'Account Access' Tickets: The system immediately triggers a bot or workflow to send the official password reset link, minimizing human agent intervention and providing a near-instant solution.

'Information Request' Tickets: The ticket is automatically routed to the HR or Policy team and a contextual template reply with a link to the relevant knowledge base article is provided to the customer.

2. Track Feature Progress (Job Point #1)
By automatically tagging every ticket, Product Managers gain real-time analytics. Spikes in tickets belonging to the 'Account Access' cluster, for example, would immediately flag a systemic issue with the login feature, allowing the PM to prioritize resources and track the status of that specific feature's stability.

⚙️ How to Run the Code
The complete, runnable code is available in the ticket_grouper.ipynb file.

Execution
The notebook is structured in sequential cells to demonstrate the full pipeline:

1. Code Cells 1-3 handle setup, data loading, and model training.

2. Code Cells 4 shows the final grouped results of the sample data.

3. Code Cells 5-6 demonstrates a live function predicting the category for new, unseen tickets (e.g., "My user ID is locked, I can't sign in.").
