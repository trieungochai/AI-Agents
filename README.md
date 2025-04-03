## A. Accessing OpenAI large language models
### A.1 Accessing OpenAI accounts and keys
1. Go to https://openai.com and log in, or register for an account and log in. If this is your first time creating an account, you’ll likely be given free credit in some amount. If you already have an account, you must register a payment method and type. It’s generally better to purchase a number of credits at a time. This will allow you to manage the costs better and avoid overruns.

2. After logging in to the platform, select ChatGPT or the API. Choose the API.
![Selecting the API section of the OpenAI platform](A.1.png)

3. Open the left menu, and select the API Keys option
![select the API Keys option](A.2.png)

4. Click the Create button to create a new key, enter a name for the key, and click the Create Secret Key button
![Create the secret API key](A.3.png)

5. Copy and paste the key to a notepad or another area for safekeeping using the Copy button. Keep this key secret, and ensure it remains only on your development machine.
![Copying and pasting the key to a well-known safe location](A.4.png)

After generating a key, you can continue to use it within an `.env` configuration file or through other means of registering an OpenAI key. Other services, such as Azure OpenAI, will require the configuration of a model deployment and a base URL.

