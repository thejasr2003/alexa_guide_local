# Alexa Local Guide 🎤

A simple Alexa skill that lets you create a personalized guide for your local area. Ask Alexa about local attractions, upcoming events, news, and interesting facts about your city!

## 📋 What This Project Does

This is an **Amazon Alexa skill** (voice application) that helps people discover information about their local area. Users can ask Alexa questions like:

- "Tell me about attractions"
- "What events are happening?"
- "Tell me some local news"
- "Share a fun fact about our area"

## 🎯 Features

- **Attractions**: Share information about popular places to visit
- **Events**: Tell users about upcoming local events
- **News**: Provide local news and updates
- **Facts**: Share interesting facts about your area
- **Help Feature**: Users can ask for help to learn what the skill can do
- **Analytics**: Built-in tracking to understand how people use your skill (optional)

## 📁 Project Structure

```
alexa-local-guide/
├── lambda/                    # The main skill code
│   ├── index.js              # Entry point for the Alexa skill
│   ├── package.json          # Dependencies needed
│   └── handlers/             # Response handlers for different questions
│       ├── Attractions.js
│       ├── Events.js
│       ├── News.js
│       ├── Facts.js
│       ├── LaunchRequest.js  # When someone opens the skill
│       ├── Goodbye.js        # When someone closes the skill
│       └── ... (other handlers)
├── speechAssets/             # Voice configuration
│   ├── IntentSchema.json     # Defines what users can ask
│   └── SampleUtterances.txt  # Example phrases users might say
├── publish_lambda.sh         # Script to upload to AWS
└── zip_lambda.sh            # Script to prepare the skill for upload
```

## 🚀 Getting Started

### Prerequisites (What You Need)

Before you begin, make sure you have:

1. **Amazon Developer Account** - Free at [developer.amazon.com](https://developer.amazon.com)
2. **AWS Account** - Free tier available at [aws.amazon.com](https://aws.amazon.com)
3. **Node.js** - Download from [nodejs.org](https://nodejs.org)
4. **AWS CLI** - Command-line tool to upload your skill
5. **Git** - For version control (optional but recommended)

### Step 1: Get the Code

Download or clone this project to your computer.

### Step 2: Install Dependencies

Open a terminal in the `lambda` folder and run:

```bash
npm install
```

This downloads the required packages (Alexa SDK and analytics tools).

### Step 3: Customize Your Content

Edit the handler files in `lambda/handlers/` to add your own local information:

- Add your attractions to `Attractions.js`
- Add your events to `Events.js`
- Add your news to `News.js`
- Add your facts to `Facts.js`

### Step 4: Set Up in Amazon Developer Console

1. Go to [developer.amazon.com/alexa](https://developer.amazon.com/alexa)
2. Create a new Alexa skill
3. Copy the content from `speechAssets/IntentSchema.json` to the Intent Schema
4. Copy the content from `speechAssets/SampleUtterances.txt` to the Sample Utterances

### Step 5: Deploy to AWS Lambda

1. Create an AWS Lambda function:

   - Go to [aws.amazon.com/console](https://aws.amazon.com/console)
   - Create a new Lambda function
   - Choose Node.js runtime
   - Copy the code from `lambda/` folder to your function

2. **Or** use the provided script:
   ```bash
   ./zip_lambda.sh        # Creates a compressed file
   ./publish_lambda.sh    # Uploads to AWS
   ```

### Step 6: Test Your Skill

- Use the Amazon Developer Console to test with voice commands
- Or test on any Alexa device linked to your Amazon account

## 🛠️ Customization Guide

### Adding Your Own Information

**For Attractions:**
Edit `lambda/handlers/Attractions.js` and add your local places.

**For Events:**
Edit `lambda/handlers/Events.js` and add upcoming events.

**For News:**
Edit `lambda/handlers/News.js` and add local news stories.

**For Facts:**
Edit `lambda/handlers/Facts.js` and add interesting facts.

### Example of Adding Content

```javascript
// In any handler file, add your information in quotes:
const attractions = [
  "Visit the beautiful Central Park",
  "Check out the local history museum",
  "Explore the downtown shopping district",
];
```

## 📊 Analytics (Optional)

This project includes Opearlo Analytics to track how people use your skill. To enable it:

1. Sign up at [analytics.opearlo.com](https://analytics.opearlo.com)
2. Set your analytics credentials as environment variables in AWS Lambda:
   - `OPEARLO_USER_ID`
   - `OPEARLO_VOICE_APP_NAME`
   - `OPEARLO_API_KEY`

## 🔗 Helpful Resources

- [Amazon Alexa Developer Documentation](https://developer.amazon.com/alexa)
- [AWS Lambda Console](https://aws.amazon.com/console)
- [AWS CLI Installation](https://aws.amazon.com/cli)
- [Utterance Expander Tool](http://www.makermusings.com/amazon-echo-utterance-expander)
- [Opearlo Analytics](https://analytics.opearlo.com)

## ❓ Troubleshooting

**Skill not responding?**

- Check that your Lambda function code is deployed
- Verify the Alexa skill is linked to the correct Lambda function
- Check AWS CloudWatch logs for errors

**Can't understand voice commands?**

- Review your `SampleUtterances.txt` file
- Add more example phrases that users might say
- Use the Utterance Expander tool to generate more variations

## 📝 License

ISC

## 👤 Author

Created by MerryOscar

---

**Enjoy building your local guide! 🌟**
"# alexa_guide_local" 
