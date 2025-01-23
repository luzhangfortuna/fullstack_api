主要改了chat_api.py的部分，读csv文档

chatdemo对话界面放到文件夹，老师可以看一下



# Flask-based Chatbot

This repository includes a simple Python Flask app that streams responses from OpenAI
to an HTML/JS frontend using [NDJSON](http://ndjson.org/) over a [ReadableStream](https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream).

## Start the app
1. Using conda to create a new environment
    ```shell
    y
    
    ```

2. Install required packages
    ```shell
    pip install -r requirements.txt
    ```

3. Create a .env file, and put your OPENAI_API_KEY and PINECONE_API_KEY in this.

4. Change the port in gunicorn.conf.py according to your machine's setup.

5. For the first time to start the app, you need to create the database
    Using the following code in python to initialize the DB:
    ```python
    from src.app import app, db
    with app.app_context():
        db.create_all()
    ```

6. Start the flask app
    ```shell
    gunicorn src.app:app
    ```

    If you want to start it in the background
    ```shell
    nohup gunicorn app:app &
    ```

7. Navigate to 'http://localhost:50505' to access this Web app if it's local environment. Change the port to the one you specified if needed.

