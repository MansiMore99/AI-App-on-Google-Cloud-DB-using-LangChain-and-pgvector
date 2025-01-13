# 🧸 AI-App-on-Google-Cloud-DB-using-LangChain-and-pgvector 🎲


![image](https://github.com/user-attachments/assets/496cbcf2-466d-400a-a20a-79a766d83d65)

Say Goodbye to dull and uninspiring captions mentioning ‘orange and white cat stuffed animal’ like you did years ago – with the help of AI, you can come up with captions like 
```
A fun and fierce friend to accompany your child, from the crib till pre-school
```

Here we will create a **Python application** that would be able to process and answer questions in natural language template by extracting information from your PostgreSQL database. Next, we will explore even more advanced ideas to encode the new text and generate new **AI-derived product descriptions** 🛍️🎨 for children toys 🎲🧩 based on the dataset we have. 

Oh come on let’s put our AI-generated taglines 🤖✨ to work and probably get some interesting results! 🎯


### 🚀 Features:
-----------------------------------------------------------------------------------------------------------------------------------------
**1. 📋 Structured Database:**
   * product_id 🆔
   * product_name 🎁
   * description 📝
   * list_price 💵

**2. 🔍 Semantic Similarity Search**

**3. ✂️ Intelligent Text Splitting**

**4. 🧠 AI-Generated Descriptions**


### How to install pgvector in Cloud SQL for PostgreSQL:
-----------------------------------------------------------------------------------------------------------------------------------------

The pgvector extension can be created into an existing Cloud SQL for PostgreSQL instance with the help of the following command. If you don’t have an instance yet, you can create one for [Cloud SQL](https://cloud.google.com/sql/docs/postgres/create-instance).

```
>> CREATE EXTENSION IF NOT EXISTS vector;
>> CREATE EXTENSION
```

### 'vector` data type:
-----------------------------------------------------------------------------------------------------------------------------------------

The sample code below includes three-dimensional vectors It is worth stating that in real-life AI/ML applications, vectors possess hundreds of dimensions, even though, for the sake of demonstration, we used four-dimensional data only.


```
>> CREATE TABLE embeddings(
      id INTEGER,
      embedding vector(3)
);
CREATE TABLE


>> INSERT INTO embeddings 
           VALUES
                   (1, '[0, 0, 0]'),
                   (2, '[9, 9, 9]');
INSERT 0 2
```

<img width="1261" alt="Screenshot 2025-01-12 at 4 41 00 AM" src="https://github.com/user-attachments/assets/8e371471-0900-4013-b2f5-03f316c631a9" />


# Building an application with a dataset:


Now that you have a general understanding of pgvector and LLMs, let’s begin the process of constructing your application with these tools. Not only that, but we also will utilize LangChain, which is an open-source tool offering several built-in modules to ease the development of intricate applications with LLMs.

### Summary:
-----------------------------------------------------------------------------------------------------------------------------------------

1. Fetch the Records and copy it in a PostgreSQL table of the name products.
   This table has 4 fields:
   * product_id: Int;
   * product_name: varchar ;
   *  description: LONGTEXT;
   *   list_price: decimal
     
2. Read each text value in the long description field, then break up each resultant value into smaller textual values for which vector embeddings are to be generated.
   
4. Split long text into smaller chunks with LangChain using [RecursiveCharacterTextSplitter](https://python.langchain.com/api_reference/text_splitters/character/langchain_text_splitters.character.RecursiveCharacterTextSplitter.html) method.
   
6. The vector embeddings are then stored in another PostgreSQL table known as product_embeddings by using the pgvector extension. The product_embeddings table contains a foreign key representing a table with products.
   
8. After filtering the products according to the user query, generate vectors for the current user query and use the pgvector vector similarity search operators to find the most similar products to the vector of the current user query.


### Results:

* **Case 1:** **🔍 Finding similar toys using pgvector cosine search operator**

<img width="708" alt="Screenshot 2025-01-13 at 2 10 04 AM" src="https://github.com/user-attachments/assets/d3037ceb-dbaf-44f7-96dc-7c9fa384a222" />


* **Case 2: 🤖 Building an AI-curated contextual hybrid search**

<img width="1383" alt="Screenshot 2025-01-13 at 2 20 40 AM" src="https://github.com/user-attachments/assets/82bb9916-8977-48e2-837d-e22ceca8350d" />

For in-detail code knowledge, I would suggest going through [How to build an AI App on Google Cloud PostgreSQL DB using LangChain and pgvector](https://medium.com/@mansi.more943/how-to-build-an-ai-app-on-google-cloud-postgresql-db-using-langchain-and-pgvector-ad5a0f7e23a4)


## References:

1. [Document1](https://cloud.google.com/blog/products/ai-machine-learning/deploy-langchain-on-cloud-run-with-langserve)
2. [Document2](https://cloud.google.com/blog/products/ai-machine-learning/deploy-langchain-on-cloud-run-with-langserve)
3. [pgvector genAI demo](https://colab.research.google.com/github/GoogleCloudPlatform/python-docs-samples/blob/main/cloud-sql/postgres/pgvector/notebooks/pgvector_gen_ai_demo.ipynb#scrollTo=jPPUSBKb1Soc)


## 💬 Feedback & Support:

I'm always looking to improve! Share your thoughts and suggestions:

- **Email:** mansi.more943@gmail.com
- **GitHub:** [MansiMore99](https://github.com/MansiMore99)
- **Linkedin:** [MansiMore](https://linkedin.com/in/mansi-more-0943)

## 📢 Contributing:

Would you be interested in contributing? I welcome your improvements and ideas. You can Fork the repository, make changes, and submit a pull request!


<a href="https://www.linkedin.com/in/mansi-more-0943/"> ![LinkedIn Profile](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white) </a>


