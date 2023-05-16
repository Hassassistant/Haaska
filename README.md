
#   Haaska

This repository contains scripts that help you set up a Haaska.
Haaska is used to have alexa be able to communicate with all Home Assistant entities.

## Prerequisites

 - [ ] Home Assistant Configuration: Ensure the following YAML entries
       are added to your Home Assistant configuration.yaml file:
       
 ```yaml
api:
       
alexa:   
 smart_home: 
 ```
 
 - [ ] Long-lived Access Token: In Home Assistant, create a long-lived
       access token and keep it for later use.

    

 - [ ] AWS Account: Sign up for a free tier AWS account if you do not
       already have one.

    

 - [ ] AWS Access Key: Create an AWS Access Key and keep it for later
       use.

    

 - [ ] Alexa Skill: Create an Alexa skill in the Alexa Developer Console
       and take note of the Skill ID.

    

## Setup

1.  Clone this repository on your local machine.
    
2.  Fill in the `constants.py` file with the information captured during the Prerequisites steps (Home Assistant URL, long-lived access token, AWS access key and secret key, AWS region, and Alexa Skill ID).
    
 ```py
    
# constants.py
    
AWS_ACCESS_KEY = 'Your AWS Access Key'
AWS_SECRET_KEY = 'Your AWS Secret Key'
AWS_REGION = 'Your AWS Region' # example: 'us-west-2'
HOME_ASSISTANT_URL = 'Your Home Assistant URL' # example: 'https://your-home-assistant-url.com'
BEARER_TOKEN = 'Your Long-lived Access Token'
ALEXA_SKILL_ID = 'Your Alexa Skill ID'
```
<br>
Region Select<br>
This is based on the region you are using for your Alexa Skill
<br>

<br>

| Skill language                                             |  Endpoint Region               |  Lambda Function Region |   Constants File |
|------------------------------------------------------------|--------------------------------|-------------------------|------------------|
|  English (US), English (CA)                                |  North America                 |  US East (N. Virginia)  |  us-east-1       |
|  English (UK), French (FR), German, Italian, Spanish (ES)  |  Europe, India                 | EU (Ireland)            |  eu-west-1       |
|  English (IN)                                              | Europe, India                  | EU (Ireland)            |  eu-west-1       |
|  Japanese, English (AU)                                    |  Far East                      | US West (Oregon)        |   us-west-2      |


<br>
<br>


3.  If you already have Python installed, you can directly run the `main.py` file.
    
    ```bash
python main.py
    ```
    If you don't have Python installed, run the `run.ps1` PowerShell script. 
    This will install Python and necessary Python packages before running `main.py`.
    
4.  Once the script has successfully run, it will output an ARN for the AWS Lambda function that was created. Copy this ARN and paste it into the 'Default' endpoint in your Alexa skill in the Alexa Developer Console.
    
5.  Set up account linking for your Alexa skill.
    
6.  Finally, activate the skill through your Alexa app. Your Alexa device should now be able to interact with your Home Assistant.
    

## Notes

Please ensure to test everything thoroughly before distributing this script. There can be many factors that affect its success, including the user's system configuration, internet connection, and security settings.
