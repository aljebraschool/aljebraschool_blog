---
title: "Step-by-Step Guide to Building an AI Content Generator"
datePublished: Wed Mar 05 2025 08:39:47 GMT+0000 (Coordinated Universal Time)
cuid: cm7vo2yzs000k0ale2b43dcxg
slug: step-by-step-guide-to-building-an-ai-content-generator
tags: artificial-intelligence, streamlit, generative-ai, large-language-models

---

Large Language Models (LLMs) are reshaping how we interact with technology, allowing anyone to create and automate content using simple, natural language. This innovation bridges the gap between complex AI systems and non-technical users, sparking creativity and solving real-world problems.

I’m Ridwan Ibidunni, an AI practitioner with experience building and deploying AI models that automate content generation and streamline workflows. I’ve developed and fine-tuned large language models for text-based applications, integrated GPT-powered services, and deployed AI-driven tools using frameworks like Streamlit and FastAPI. From automating CV analysis to generating realistic content from text prompts, I’ve applied these techniques in practical, hands-on projects.

In this guide, I’ll take you through the process of building your own AI-powered content generator. Each step reflects methods I’ve used in real projects, ensuring you gain practical insights and create something you can use right away.

## **Technology and Tools Used for This Project**

To follow along with this step-by-step guide, it's essential to have the right tools in place. Below is a list of the key technologies and tools we’ll be using:

* **Integrated Development Environment (IDE):** An IDE is crucial for every developer, helping streamline the process of writing, debugging, and refining your code. For this project, we’ll be using [**Cursor AI**](https://www.cursor.com/), but you can also follow along using any Python IDE of your choice, such as [**PyCharm**](https://www.jetbrains.com/pycharm/) or [**Visual Studio Code**](https://code.visualstudio.com/). Choose the one you're most comfortable with to get started!
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735896426143/00816028-8b63-49ed-9fa8-f81b46763771.png align="left")

* **GitHub Repository:** GitHub will be used to host the code before deploying it to Streamlit Cloud for easy access by everyone. Sign up for a GitHub account [here](https://github.com/) or follow this [video tutorial](https://www.youtube.com/watch?v=Gn3w1UvTx0A) [to get started](https://www.youtube.com/watch?v=Gn3w1UvTx0A).
    
* **Streamlit/Streamlit Cloud:** Streamlit makes it simple to deploy and showcase our LLM-powered application on the web for users around the world. The web app hosted on GitHub will be deployed via Streamlit Cloud. You can sign up for Streamlit [here](https://streamlit.io/). Be sure to **log in** with your GitHub account to authorize access to your repository.
    
* **Free Cohere API:** The final piece required is the LLM API that powers the chatbot. Cohere offers a free API that you can access [here](https://dashboard.cohere.com/api-keys). Make sure to sign up before using the API!
    

# Project Structure

As mentioned earlier, we will structure this project using best programming practices. The first step is to create a **virtual environment**, which will be used to install all the necessary dependencies for the project.

In your project directory, open a terminal (CMD on Windows) and run the following commands:

* **On linux/Mac** : `python3 -m venv venv`
    
* **On Windows** : `python -m venv venv`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735898695471/0ca51ff4-e4c1-4097-affa-75569e0082c9.png align="left")

After creating the virtual environment, you need to activate it:

* **On linux/Mac :** `source venv/bin/activate`
    
* On Windows : `venv\\Scripts\\activate`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735899156564/77c23933-b495-4b4f-a319-2e6768779bfd.png align="left")

Once activated, you should see `(venv)` appear before your project path in the terminal, indicating that the virtual environment is active.

## Set Up Project Folders and Files

* **.streamlit folder**: Inside the project directory, create a folder called `.streamlit`. Inside this folder, create a file named `secrets.toml`. This file will securely store your Cohere API key to prevent it from being exposed when deploying the app. You can refer to the [Streamlit documentation](https://docs.streamlit.io/deploy/streamlit-community-cloud/deploy-your-app/secrets-management) for more details on this.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735899495034/d86832ac-f48b-4a66-b65b-3b122c1dfb77.png align="left")

* **Other Required Files**:
    
    * [`app.py`](http://app.py/): This is where your program's main logic will reside.
        
    * `requirements.txt`: This file will list all the dependencies required for the project.
        
    * `.gitignore`: This file should be placed at the root of your project. It will specify the files and directories to exclude from version control, ensuring sensitive data (like the API key) or unnecessary files are not pushed to the public GitHub repository.
        
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1741163865412/0edd68b3-10e3-48c9-9761-930ca12f0295.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1741163834019/eb41a0cb-2afc-4377-b29e-a2371169fcc0.png align="center")
    
    ![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4d392bda-55cb-47c2-8dd1-4fd99e3ca8e0/44fa60de-d412-463f-a0c5-77bc5874574c/image.png align="left")
    

# Project Implementation

The first step in the implementation process is to install the project dependencies. You can do this by running the following command in your terminal:

```python
pip install -r requirements.txt
```

Next, you'll need to securely store your Cohere API key in the `secrets.toml` file. You can do this by adding the following code:

```python
COHERE_API_KEY = "your_cohere_api_key"
```

* **Import the required libraries** after installation and configure the API.
    

```python
import cohere
import streamlit as st

# Set up Cohere client
co = cohere.ClientV2(st.secrets["COHERE_API_KEY"])
```

* **Define a function** that will generate content based on specific parameters.
    

```python
def generate_writeup(write_up_type, topic, tone, length, temperature):
    prompt = f"""

        Generate a {write_up_type} about {topic}. Follow these guidelines.

        - Length : {length} words
        - Tone : {tone}
        - Format : Properly structured with paragraphs. Ensure the content is engaging and informative. Avoid unnecessary commentary or fillers
        - Include : clear introduction, body and conclusion

        Use these structures for different content types:

        Blog Post:
        - Engaging hook
        - Personal perspective
        - Actionable insights
        - Conversational style
        - Clear takeaways

        Article:
        - Formal introduction
        - Well-researched points
        - Expert analysis
        - Professional tone
        - Citations where relevant

        Technical Guide:
        - Step-by-step instructions
        - Code examples if relevant
        - Technical specifications
        - Practical implementation
        - Troubleshooting tips

        Social Media Post:
        - Attention-grabbing opener
        - Concise message
        - Engaging call-to-action
        - Relevant hashtags
        - Shareable format

    Now write a {write_up_type} about {topic}:
       """

    response = co.chat(
        messages = [{"role": "user", "content": prompt}],
        model="command-r-plus-08-2024",
        temperature = temperature
    )

    return response.message.content[0].text
```

* **Create another function** to generate a corresponding title for each output.
    

```python
def generate_title(content, content_type, temperature):
    prompt = f"""
            Generate an engaging title for this {content_type}. The title should be :

            - Attention-grabbing
            - Relevant to the content
            - SEO-friendly
            - Under 60 characters
            - No clickbait

            content: {content[:500]}

            Title :

            """
    response = co.chat(
        messages = [{'role': "user", "content": prompt}],
        model="command-r-plus-08-2024",
        temperature = temperature
    )

    return response.message.content[0].text
```

* **Design the frontend** of your application using Streamlit.
    

```python
#frontend code
st.write("📝 Professional Write-up Generator")

form = st.form(key="user_settings")

# Move these variables to be accessible outside the form
content = ""
title = ""

with form:
    # Content type selection
    content_type = st.selectbox(
        "Content Type",
        ["Blog Post", "Article", "Technical Guide", "Social Media Post"],
        key = "content_type"
    )

    # Topic input
    st.write("Enter your topic")
    topic_input = st.text_input("Topic", key="topic_input")

     # Create three columns for additional settings
    col_1, col_2, col_3 = st.columns(3)

    with col_1:
        # Tone selection
        tone = st.select_slider(
            "Tone",
            options = ["formal", "Professional", "Neutral", "casual", "conversational"],
            value = "Professional",
            key = "tone_input"
        )
    with col_2:
        # Length selection
        length = st.select_slider(
        "Length (words)",
        options=[300, 500, 750, 1000, 1500, 2000],
        value = 500,
        key = "input_length"
        )
    with col_3:
        # Creativity level
        creativity = st.slider(
            "Creativity",
            min_value = 0.1,
            max_value = 0.9,
            value = 0.5,
            key = "creativity_input",
            help="Lower values for more focused content, higher for more creative"
        )

    generate_button = form.form_submit_button("Generate Content")

    if generate_button:
        if topic_input == "":
            st.error("Topic field cannot be blank")

        else:
            st.spinner("Generating your content...")
            # Generate content
            content = generate_writeup(content_type, topic_input, tone, length, creativity)
            title = generate_title(content, content_type, creativity)

            # Display results
            st.markdown("""---""")
            st.markdown(content)

    # Move download button outside the form
if content:  # Only show download button if content has been generated
    st.download_button(
        label="Download as Text",
        data=f"{title}\\n\\n{content}",
        file_name=f"{content_type.lower().replace(' ', '_')}.txt",
        mime="text/plain"
    )
```

# Project Deployment

Before deploying your project via Streamlit Cloud, it must first be uploaded to GitHub as a complete project. However, be mindful not to commit any sensitive files, such as your API key or private data, to a public GitHub repository. To prevent this, ensure these files are added to the `.gitignore` file you created earlier.

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4d392bda-55cb-47c2-8dd1-4fd99e3ca8e0/44fa60de-d412-463f-a0c5-77bc5874574c/image.png align="left")

**Deploy to Streamlit Cloud**:

[Log in](https://share.streamlit.io/) to your Streamlit account and connect your GitHub repository to Streamlit Cloud. Click on the **Create App** option in the top-right corner, as shown below.

**Deploy to Streamlit Cloud**:

[Log in](https://share.streamlit.io/) to your Streamlit account and connect your GitHub repository to Streamlit Cloud. Click on the **Create App** option in the top-right corner, as shown below.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735973704411/46342b16-51ac-4692-8262-ba9a4149ecfc.png align="left")

**Select GitHub**:

Choose GitHub from the available options.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735973825705/d7c688be-fe8f-4d16-8373-b096e1fd7f73.png align="left")

**Link Your Repository**:

You’ll be redirected to a screen where you can select the path to your project on GitHub.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735973986334/39e4d74f-fe18-496d-a425-58a07c4cef3f.png align="left")

**Set Up Secrets**:

Before clicking **Deploy**, go to **Advanced Settings** and add any sensitive code stored in the `secrets.toml` file by copying and pasting the contents directly into this page.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735974218526/8e740921-d721-48a8-8be4-b6c6798336aa.png align="left")

**And voilà!** Your app is now live and running on the cloud, accessible to everyone!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735974365926/849ee559-21ea-4957-8f4d-fea0041e07cc.png align="left")

# **Conclusion**

Congratulations! You've successfully built and deployed your very own AI-powered content generator. By following this guide, you’ve learned how to set up the necessary tools, implement the project step-by-step, and deploy it to the cloud for global access. This project not only demonstrates how to integrate a powerful large language model but also highlights the importance of using best practices in coding and deployment.

Now, you have a fully functional AI tool that can help you generate content tailored to specific keywords or domains. With this foundation, you can expand and personalize the app to meet your unique needs, whether it's for creating blog posts, articles, or other forms of written content.

As you continue your journey with AI, remember that the possibilities are endless—whether it's refining your model, enhancing the user interface, or exploring new ways to integrate AI into different applications. The skills and knowledge you’ve gained here are just the beginning of what you can achieve with AI and technology!

If you'd like to explore the full code for this project, check out the complete source code on my [GitHub repository](https://github.com/aljebraschool/Build-Your-Own-AI-Powered-Content-Generator.git). Feel free to clone the repo, experiment with the code, and make it your own!

# References

1. Cohere, "Deploy LLMs with Streamlit," LLM University. \[Online\]. Available: [https://cohere.com/llmu/deploy-streamlit](https://cohere.com/llmu/deploy-streamlit)
    
2. Streamlit, "Documentation," [Streamlit.io](http://Streamlit.io). \[Online\]. Available: [https://streamlit.io](https://streamlit.io)