# Twitter OAuth App

This Python project is a simple Twitter OAuth application that allows users to authorize your app to post tweets on their behalf.

## Prerequisites

1. **Twitter Developer Account**: Sign up at [Twitter Developer](https://developer.twitter.com/).
2. **API Keys and Tokens**: Create an app in the Twitter Developer Portal to get:
   - `API Key`
   - `API Key Secret`
   - `Bearer Token` (optional for this project)
   - **Note**: Make sure your app has **Read and Write** permissions in the Twitter Developer Portal to allow posting tweets.

## Project Structure

twitter_oauth_app/
├── twitter_oauth.py
└── README.md

## Setup

1. Clone this repository.
2. Install the required libraries:

   pip install tweepy

3. Replace the `API_KEY` and `API_KEY_SECRET` in `twitter_oauth.py` with your credentials from the Twitter Developer Portal.

## Running the App

1. Run `twitter_oauth.py`:

   py twitter_oauth.py

2. The script will print a URL. Open this URL in your browser to authorize the app to access your Twitter account.

3. Twitter will provide a **PIN** after authorization. Enter this PIN into the terminal when prompted.

4. If everything is set up correctly, the app will post a tweet (`Hello, world!`) to your Twitter account.

## Explanation of Code

### 1. **Initialize OAuth Handler**

   We use `tweepy.OAuth1UserHandler` to handle the OAuth flow. The app requests permissions based on the credentials you enter.

### 2. **Redirect to Twitter for Authorization**

   After setting up the OAuth handler, the app generates an authorization URL. By opening this URL in a browser, users can authorize the app. Twitter will return a **PIN** which allows the app to request an access token.

### 3. **Request Access Token**

   Using the PIN, the app requests an access token. This token allows the app to post tweets on behalf of the user.

### 4. **Post a Tweet**

   The `api.update_status` function posts a tweet with the given text. If successful, you'll see a "Tweet posted successfully!" message.

## Troubleshooting

- **Error: 401 Unauthorized**: Ensure your API keys are correct and your app has `Read and Write` permissions.
- **Permission Denied on Tweet**: Verify the account used to authorize the app has `Read and Write` permissions.
- **Callback URI**: If using a production app with a specific URL, update `CALLBACK_URI` to point to your callback URL.

## Important Notes

- This script is designed for demonstration and testing purposes.
- Always ensure the security of your keys and tokens.
- If deploying this app, consider implementing secure storage for tokens.

## License

This project is open-source and available under the MIT License.

ijeehiqf