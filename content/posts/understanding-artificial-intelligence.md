+++
author = "Thanni"
title = "Understanding Artificial Intelligence"
date = "2023-12-22"
description = "A beginner's guide to AI"
tags = [
    "AI-notes",
]
categories = [
    "How it works",
]
series = ["Explain like I'm 5"]
+++

From self-driving cars to medical diagnosis, AI's impact is permeating our lives, shaping the future of technology and society.

<!--more-->

# <mark>What is Artificial Intelligence?</mark>

## What AI can do

### Pattern recognition

- Prediction and inference
- Clustering/segmentation
- Anomaly detection
- Data generation

### Optimization

AI finds the best possible solution for a problem at a minimum cost, under constraints

- Logistics and delivery: smart routing
- Energy: Power grid operation and control
- Tourism: Flights and hotel pricing
- Marketing: maximum-revenue campaign

### Automation

AI is not automation as most people think, but it helps improve it

- Classifying documents, photos e.t.c
- Job application screening
- Parcel management robots

## Limitations of AI

- Social skills: AI lacks emotional intelligence, empathy, and new, unseen situations
- Bias
- Low data

## Subdomains of AI

- **Machine learning**: Learn from data; prediction, inference
  - **Deep learning**: A subset of machine learning that focuses on neural networks, solving the most challenging AI problems
- **Knowledge representation and reasoning**: Communicate with other AI systems
- **Robotics**: Act and manipulate the physical environment
- **Computer vision**: Visually perceiving objects in the environment
- **Natural language processing**: Analyse, understand, communicate human language

## Examples of AI Applications

- Personalized product management - Machine learning
- Warehouse management - Robotics, computer vision, reasoning
- Medical diagnosis - Computer vision, deep learning
- Smart voice assistant - NLP, deep learning

## Related Disciplines

- Data science
- Maths & statistics
- Psychology, physics, ethics, law

# <mark> Tasks AI can solve </mark>

## Algorithms and AI systems

An algorithm is a set of instructions to solve a problem or perform an action. The flow would be something like - `Inputs => Process => Outputs`.

Algorithms in computer science have a rigid, input-output behaviour. AI algorithms learn by themselves to produce better outputs.

An AI system encompasses the inputs, AI algorithm, hardware, database, outputs and more.

## Acquiring Data

More than just acquiring data, AI learn and reason from data to give output in form of decisions and insights.

AI collects data through sensors, emulating human senses. Then it transforms these perceptions into data.

- **NLP and audio**: capturing speech, sounds
- **Computer vision**: satellite images, fingerprint, etc
- **Robotics and sensors**: temperature, touch, motion, gravity, etc

Most AI applications today rely on datasets that are automatically collected.

## Learning from Data

With machine learning, AI learn from data to identify patterns, make predictions, clusters and classifications. Machine learning do these with different techniques:

- Supervised learning
- Unsupervised learning
- Reinforcement learning

### Supervised Learning

**Classification**: There's binary classification (male/female) and multi-class classification, which considers several mutually exclusive factors. During supervised learning, data annoation is employed to label data. Decision tree, support vector machine and random forest are examples of supervised learning models.

**Regression**: Deals with quantitative data, where models are built on mathematical computation. An example is looking at a house attributes to determine its price.

**Time series forecasting**: Training models to predict values based on its past behaviour.

### Unsupervised Learning

**Clustering**: Subgroups of data with similar charateristics

**Anomaly detection**: Detecting abnormal data observation e.g unauthorized card txns

**Association rule discovery**: Identify common occurences in txn data

### Reinforcement Learning

Learning by experience through trial and error.

## Deep Learning

Models built on neural networks. They solve extremely challenging tasks that may be hard to solve by classical ML models.

Here are five different real-world applications of deep learning:

1. Design an original t-shirt.
2. Find out the shopping style that best describes you.
3. Write a Cervantes novel-style fictitious piece of text.
4. Dynamically assign hotel room and flight prices in a booking portal.
5. Unlock your cellphone with your face.

## Interacting with the Physical Environment

These areas involve the AI interacting with the physical environment.

- Robotics
- Computer vision
- Natural language processing

### Robotics

Subareas include:

- Sensing and perception
- Mobility
- Manipulation
- Human-robot interaction

### Computer Vision

- Image processing
- Object detection
- Motion analysis
- Image and video generation

### Natural Language Processing

**Text-based**: Classification, sentiment analysis, question answering(chat bots), and summarization.

**Speech-based**: Text-to-speech and speech-to-text

# <mark>Harnessing AI in Organizations</mark>

## AI Value in Organizations

- Less operational costs
- Competitive advantage
- Revenue and efficiency
- Customer experience
- Better products

## Adopting AI for Organizations

- Build a roadmap
- Data strategy and governamce
- Infrastructure resources
- Collaboration
- Define & pursue metrics e.g customer centric
- AI & data literacy
- Responsible AI

## Example: Insurance company AI roadmap

- **Objective**: efficient claim processing
- **Resources**: data scientists, ML Experts.
- **Implementation**: ML model for fraud detection and claim satisfaction

## Data Strategy, Resources and People

**Data Strategy:** design and development of data-centric approached for information extraction and business decision making.

### Resources

**Cloud-based AI Infractrusture**: Highly scalable and cost effective. Cons - data location and access to internet

**On premises (self-hosted) AI infrastructure:** Enhanced data control, lower latency. Cons - upfront costs, limited scalability

**Machine Learning Operations (MLOps):** efficient and reliable management and operation of ML (AI) systems in the enterprise

### People: AI-related roles

- AI Architect
- Data Scientist
- Machine Learning and Data Engineer
- AI Ethicist
- AI Project Manager

An ideal AI team should include: Leadership & management, execution & MLOps and Support.

# <mark>Human Side of AI</mark>

## Democratizing AI

Design of AI tools anayone can easily implement to supplement tasks

**AI literacy** contributes to democratization by empowering indicicuals, promote ethics awareness, inclusive participation and critical thinking.

In organizations, data democratization make information accessible to employees of all roles.

**Open Data Policies**

Open data play a central role in AI democratization: the idea refers to enabling unrestricted access to non-sensitive data held by the government to the wider public, including citizens, research institutions, and organizations.

## Explainability and interpretability

Explainability refers to the ability of a model or system to provide clear and understandable reasons for its predictions or decisions. Interpretability, on the other hand, relates to the ease with which humans can comprehend and make sense of the inner workings or logic behind a model's outputs.

## White box and Black box AI systems

White box AI systems, also known as transparent or interpretable models, are those where the internal mechanisms and decision-making processes are easily understandable and explainable. In contrast, black box AI systems, often associated with complex models like deep neural networks, operate with intricate internal structures that make it challenging for users to comprehend the reasoning behind specific predictions or decisions.

## XAI

XAI, or Explainable Artificial Intelligence, refers to a set of techniques and approaches designed to make the decision-making processes of artificial intelligence systems more understandable and transparent to humans. XAI aims to address the inherent complexity and opacity of certain AI models, particularly those considered "black box," by providing insights into how these models arrive at their predictions or decisions. This increased transparency is crucial for building trust, verifying model behavior, and ensuring ethical and responsible use of AI in various applications.

### SHAP

SHAP, which stands for SHapley Additive exPlanations, is a popular framework in Explainable Artificial Intelligence (XAI). Developed based on cooperative game theory, SHAP values provide a way to fairly distribute the contribution of each feature in a predictive model to the prediction for a specific instance.

These values offer a means to interpret and understand the output of complex machine learning models, helping users gain insights into the factors influencing individual predictions. SHAP values are often employed to assess feature importance and contribute to the overall goal of making AI models more transparent and interpretable.

### Practical Implications of XAI

The practical implications of Explainable Artificial Intelligence (XAI) are significant across various domains, and they include:

1. **Trust and Adoption:**

   - **Increased Trust:** XAI can enhance users' trust in AI systems by providing transparent insights into the decision-making processes. Users are more likely to adopt and rely on AI technologies when they understand how and why certain decisions are made.

2. **Compliance and Regulation:**

   - **Ethical Compliance:** XAI can assist organizations in ensuring ethical compliance by allowing them to demonstrate accountability and fairness in AI decision-making. This is particularly important in industries with regulatory requirements, such as finance, healthcare, and autonomous vehicles.

3. **Risk Mitigation:**

   - **Identification of Biases and Errors:** XAI tools help identify biases and errors in AI models, enabling organizations to rectify issues before they lead to adverse consequences. This can reduce the risk of unintended and potentially harmful outcomes.

4. **Human-in-the-Loop Systems:**

   - **Human Oversight:** XAI facilitates the integration of human oversight in AI systems. When AI outputs are interpretable, human experts can better understand, validate, and intervene in critical decisions, especially in applications like medical diagnoses or financial decisions.

5. **Model Improvement:**

   - **Insights for Model Enhancement:** Explanations provided by XAI techniques offer valuable insights for improving model performance. Understanding the impact of different features helps data scientists and engineers refine models and optimize them for better outcomes.

6. **Customer and Stakeholder Communication:**

   - **Transparent Communication:** XAI enables organizations to communicate with customers, stakeholders, and the general public in a more transparent manner. Clear explanations of AI-driven decisions can help manage expectations and alleviate concerns about algorithmic decision-making.

7. **Educating Users:**

   - **User Understanding:** XAI tools can be used to educate end-users about the functioning of AI systems. This educational aspect is crucial for widespread acceptance and responsible use of AI technologies.

8. **Legal and Ethical Considerations:**

   - **Legal Compliance:** In legal contexts, the interpretability provided by XAI may be essential for complying with regulations that require explanations for automated decisions. This is relevant in areas such as finance, healthcare, and criminal justice.

9. **Debugging and Troubleshooting:**
   - **Model Debugging:** XAI facilitates the identification of issues and debugging in AI models. When models produce unexpected or undesirable results, explanations can guide developers in diagnosing and addressing problems effectively.

In summary, XAI has practical implications for building trustworthy, ethical, and effective AI systems, addressing concerns related to transparency, accountability, and the responsible deployment of AI technologies in real-world applications.

## Responsible AI

1. **Ethics and Fairness:**
   Responsible AI involves embedding ethical principles into the design and implementation of algorithms, ensuring fairness in decision outcomes for all individuals.

2. **Privacy:**
   Prioritizing privacy in AI development requires robust measures to protect user data, granting individuals control over their information and minimizing risks of unauthorized access or misuse.

3. **Transparency:**
   Transparency in AI necessitates clear communication of algorithms' intentions and functionality, providing users and stakeholders with understandable insights into the decision-making processes.

4. **Accountability and Governance:**
   Responsible AI demands the establishment of accountability frameworks and governance structures to oversee the development, deployment, and impact of AI systems, ensuring adherence to ethical standards and legal obligations.

5. **Sustainability:**
   Integrating sustainability into AI practices involves minimizing environmental impacts, optimizing energy efficiency, and considering the long-term ecological consequences of AI technologies to create a responsible and environmentally conscious approach.

## Bias in AI systems

Bias in AI systems can arise from various sources, including biased training data, flawed algorithms, or biased design choices. Here are examples of bias in AI systems:

1. **Gender Bias in Hiring Algorithms:**

   - Some AI-driven hiring systems have demonstrated gender bias, favoring male candidates over equally or more qualified female candidates, possibly due to historical biases present in training data or algorithmic decision-making.

2. **Racial Bias in Facial Recognition:**

   - Facial recognition systems have been found to exhibit racial bias, with higher error rates for certain ethnic groups, particularly people with darker skin tones. This bias is often attributed to imbalances in the training data used to develop these systems.

3. **Bias in Predictive Policing:**

   - Predictive policing algorithms may reflect and perpetuate existing biases in law enforcement data, leading to over-policing in certain communities and reinforcing societal inequalities.

4. **Financial Bias in Credit Scoring:**

   - Credit scoring algorithms may unintentionally incorporate biases, resulting in discriminatory lending practices. For instance, if historical data reflects biases in lending decisions, the algorithm may perpetuate these biases.

5. **Healthcare Disparities:**

   - AI applications in healthcare, such as diagnostic tools, may exhibit bias if the training data primarily represents certain demographics, potentially leading to diagnostic errors or disparities in the quality of care for different groups.

6. **Language Bias in Natural Language Processing (NLP):**

   - NLP models can exhibit bias based on the language used in training data. If the training data contains biased or discriminatory language, the model may replicate and perpetuate these biases in its outputs.

7. **Algorithmic Biases in Social Media:**

   - Recommendation algorithms on social media platforms may inadvertently promote biased or polarized content, contributing to filter bubbles and reinforcing users' existing beliefs, potentially leading to radicalization or misinformation.

8. **Accessibility Bias in Voice Assistants:**

   - Voice recognition systems may exhibit bias against certain accents or dialects, making them less effective for users with non-standard speech patterns or non-dominant languages.

9. **Age Bias in Predictive Analytics:**

   - Predictive analytics used for determining credit risk, insurance premiums, or job prospects may inadvertently incorporate age-related biases, disadvantaging or favoring individuals based on their age.

10. **Socioeconomic Bias in Recommendation Systems:**
    - Recommendation systems in e-commerce or content platforms may exhibit bias based on users' socioeconomic status, reinforcing existing disparities and limiting opportunities for certain individuals to discover diverse content or products.

Addressing these biases is crucial to developing more ethical and fair AI systems, and ongoing efforts are being made to improve the transparency and accountability of AI algorithms

## How AI may shape the present and future society

AI has the potential to shape present and future society in numerous ways, influencing various aspects of our lives. Here are some key ways in which AI may impact society:

1. **Automation of Jobs:**
   - AI technologies, including robotics and machine learning, may automate routine and repetitive tasks, leading to changes in the job market. While this could eliminate some jobs, it may also create new opportunities and roles in AI-related fields.
2. **Enhanced Productivity and Efficiency:**
   - AI can improve productivity across industries by streamlining processes, optimizing resource allocation, and enhancing decision-making. This can lead to economic growth and increased efficiency in sectors such as manufacturing, healthcare, and logistics.
3. **Personalized Services:**
   - AI enables the development of personalized services and products tailored to individual preferences and behaviors. This includes personalized recommendations in entertainment, targeted advertising, and customized healthcare treatments.
4. **Healthcare Advancements:**
   - AI has the potential to revolutionize healthcare through improved diagnostics, personalized medicine, and efficient management of health records. AI applications may contribute to early disease detection, treatment optimization, and overall better healthcare outcomes.
5. **Education Transformation:**
   - AI can transform education by providing personalized learning experiences, automating administrative tasks, and offering new tools for both students and educators. Virtual tutors, adaptive learning platforms, and AI-driven educational content are examples of this transformation.
6. **Finance:**
   - **Algorithmic Trading:** AI algorithms are used in financial markets for high-frequency trading, risk management, and portfolio optimization, improving efficiency and responsiveness to market dynamics.
   - **Fraud Detection:** AI helps financial institutions detect and prevent fraudulent activities by analyzing patterns, anomalies, and transaction data in real-time.
   - **Customer Service:** Chatbots and virtual assistants powered by AI enhance customer interactions, providing personalized recommendations, assisting with transactions, and answering queries.
7. **Ethical Considerations:**
   - The integration of AI raises ethical concerns related to bias, privacy, accountability, and the impact on employment. Society must navigate these challenges to ensure the responsible development and deployment of AI technologies.
8. **Smart Cities:**
   - AI can contribute to the development of smart cities by optimizing traffic management, improving energy efficiency, and enhancing public services. Smart infrastructure, IoT devices, and data analytics powered by AI can lead to more sustainable and livable urban environments.
9. **Environmental Impact:**
   - AI technologies can be employed to address environmental challenges, including climate change. Applications range from optimizing energy consumption to monitoring and managing natural resources.
10. **Human-AI Collaboration:**

- The future may involve increased collaboration between humans and AI systems, where AI complements human capabilities rather than replacing them. This collaboration could lead to innovative solutions in science, research, and problem-solving.

11. **Global Competitiveness:**
    - Countries and industries investing in AI research and development may gain a competitive advantage in the global economy. AI is likely to play a crucial role in shaping the economic landscape and determining the competitiveness of nations.
12. **Social and Cultural Impact:**
    - AI can influence social interactions, communication, and cultural trends. Social media algorithms, virtual assistants, and AI-generated content are examples of how AI can impact the way people connect, share information, and consume media.
13. **Ethical AI Governance:**
    - As AI becomes more pervasive, there is an increasing need for ethical governance frameworks and regulations to ensure the responsible use of these technologies. This includes addressing issues such as bias, accountability, and transparency.

👉🏽 See [all notes](https://notes.thanni.co/artificial-intelligence-fundamentals/) in this series
