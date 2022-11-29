# tie-api-example-twilio-whatsapp
This node.js example connector allows you to make your Teneo bot available on WhatsApp using the [Twilio API for WhatsApp](https://www.twilio.com/whatsapp). This guide will take you through the steps of setting up a Twilio WhatsApp sandbox phone number and deploying the connector so it can respond to messages sent using WhatsApp.

> Note that the Twilio API for WhatsApp is currently in Beta and is subject to change before becoming generally available.

## Prerequisites
### Https
Making the connector available via https is preferred. Ngrok is recommended for this.

### Teneo Engine
Your bot needs to be published and you need to know the engine url.

## Setup instructions
### Download, install and start connector
1. Download or clone the connector source code:
    ```
    git clone https://github.com/artificialsolutions/tie-api-example-twilio-whatsapp.git
    ```
2. Install dependencies by running the following command in the folder where you stored the source:
    ```
    npm install
    ``` 
3. Start the connector with the following command (replacing the environment variable with the appropriate value):
    ```
    TENEO_ENGINE_URL=<your_engine_url> node server.js
    ```

### Make the connector available via https
You can make your locally running connector available via https using ngrok as follows:

1. The connector runs on port 4337 by default, so execute the following command:
    ```
    ngrok http 4337
    ```
2. Running the command above will display a public https URL, copy it, we will use it in the following steps.

### Setup a Twilio WhatsApp phone number
1. Setup a free [Twilio](https://www.twilio.com/try-twilio) account, which comes with free credit money you can spend on buying a number.

2. Go to the left panel menu and click the **Programmable Messaging** item, then from the submenu choose **Try it Out > Try Whatsapp**. 

3. Follow the 5-step process to setup communication between Twilio Sandbox and WhatsApp on your phone.

4. Next, in **Programmable Messaging > Settings > Whatsapp Sandbox Settings** submenu, add the https URL you copied earlier to the **When a message comes in** field. Hit save at the bottom of the page.

That's it! Now you can use the WhatsApp sandbox to interact with your bot!

## Running the connector on Heroku

**Note: Starting November 28, 2022, free Heroku Dynos, free Heroku Postgres, and free Heroku Data for Redis® plans will no longer be available.**

Click the button below to deploy the connector to Heroku:

[![Deploy](https://www.herokucdn.com/deploy/button.svg?classes=heroku)](https://heroku.com/deploy?template=https://github.com/artificialsolutions/tie-api-example-twilio-whatsapp)

In the 'Config Vars' section, add the following:
* **TENEO_ENGINE_URL:** The engine url

Next, follow the 'Setup a Twilio WhatsApp phone number' instructions above. Make sure that in the step 4 you set the 'When a message comes in' URL to the url of the Heroku app.

## Twilio API for WhatsApp
The Twilio API for Whatsapp is currently in beta. For more details, visit the Twilio website: [Twilio API for WhatsApp](https://www.twilio.com/docs/sms/whatsapp/api).


