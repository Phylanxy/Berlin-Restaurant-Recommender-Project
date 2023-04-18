# Drop into Berlin – Location Recommender Project using Deep Learning 


## 1. About the Project

Drop into Berlin is a project that helps people who are new to Berlin or frequent city hoppers who are looking for new and unique dining experiences. We understand that it can be challenging to find comparable unique locations in a new city, especially with the variety of restaurants, bars, and clubs available in big cities. Browsing multiple platforms to find promising places is time-consuming, and long waiting times can be frustrating, particularly in large cities where people need to queue up for restaurant access.

Our solution is a location recommender that utilizes artificial intelligence (AI) based personalized recommendations to help users find comparable unique locations based on their preferences. Users can input their dining preferences and our recommender will provide personalized recommendations based on their preferences. Additionally, users can search for locations using filters, making it easier to find the ideal location. Our recommender considers real-time user reviews and ratings, ensuring that users get up-to-date information on the quality and popularity of a location. It also allows users to discover "hidden" gems - locations that are not as well-known or popular but offer unique experiences.

### Technology

- [Python](https://www.python.org/) (e.g. Pandas, Scikitlearn, BERTopic)<br>
- [Google Places API via GCP](https://developers.google.com/maps/documentation/places/web-service?hl=de)<br>
- [GPT-3.5 API](https://platform.openai.com/docs/models/overview)<br>
- [Anvil](https://anvil.works/)<br>

## 2. How did we built the project?

1.  Creation of Database against which preferred location is being measured [1. Database]
    - Scraping of Restaurants in Berlin via Google Maps API
    - Enhancing of data with “hidden” feature via openAI's GPT 3.5 API
2. Training and tweaking of AI model, i.e. BERTopic parameters [2. AI_Model]
3. Data Cleaning and prediction of restaurant recommendation and hosting via Anvil infrastructure [3. Drop_into_Berlin_App ]

## 3. Getting Started

### Clone GitHub Repo
- Run the following command in your terminal to clone our GitHub repository:

```git clone https://github.com/lukas-bst/Berlin-Restaurant-Recommender-Project.git```

### Setup Google Places API and Get Google API Key
- Follow the instructions in [this video](https://www.bing.com/videos/search?q=how+to+set+up+google+places+api+key&view=detail&mid=577E7FFA4ED4FB8766CF577E7FFA4ED4FB8766CF&FORM=VIRE) tutorial to set up the Google Places API and obtain a Google API key

### Open main.py with Google Colab
- Open the ```3. Drop_into_Berlin_App > main.ipynb file``` using Google Colab by following [this link](https://colab.research.google.com/)
- Note: The underlying AI model needs CUDA access, which regular notebooks do not provide. Therefore, we rely on Google's cloud services
- To enable CUDA access, set the runtime type to GPU under Colab's runtime settings. To do this, click on <br>```Runtime -> Change runtime type -> Select "GPU" under the Hardware accelerator option```

### Download the BERTopic_model_CPU.joblib file
- Follow the [link](https://drive.google.com/file/d/1ObRZgucFnGLUIjAsdmoBwsTE8MwFT1Jp/view?usp=sharing) to download or directly transfer the ```BERTopic_model_CPU.joblib``` file to your own Google Drive account (the size of the model was too large, wherefore it could not be uploaded to GitHub)

### Upload and connect BERTopic_model_CPU.joblib and database.csv Files with Google Drive
- Follow the instructions in [this tutorial](https://medium.com/@jayantspeaks/how-to-upload-data-to-google-colab-c7f4f59c4291) to upload and connect the ```BERTopic_model_CPU.joblib``` and ```1. Database > database.csv``` files to your Google Drive account

### Replace variables in main.py
- Replace the ```database```, ```trial_model```, and ```api_key``` variables in the ```3. Drop_into_Berlin_App > main.ipynb file``` file with your previously generated Google API key, and the paths to the ```1. Database > database.csv``` and the ```BERTopic_model_CPU.joblib``` files on Google Drive

### Install Necessary Libraries and Run the Script
- Install the necessary libraries and run the entire script by clicking on <br>
```Runtime -> Run all```

### Access the Drop into Berlin App
- Visit [Drop into Berlin](https://drop-into-berlin.anvil.app/) to access our official application
- Find your favorite restaurant's place ID via [this link](https://developers.google.com/maps/documentation/javascript/examples/places-placeid-finder) and copy paste it into the search bar at the top of the website
- Select your preferred filtering options, and enjoy browsing through similar restaurant recommendations.

## 4. Limitations and further outlook
1. **COMPLETE DATABASE**: As of now, the recommendation system has scraped data of around 4500 restaurants in Berlin from the Google Places API. The goal should be to obtain data for all restaurants in Berlin to make the recommendation system more comprehensive.

2. **IMPROVE AI MODEL**: The recommendation system's AI model - based on BERTopic - should be further tweaked to ensure more accurate and relevant recommendations. This will be done in line with the latest research in the field to enhance the matching results and improve user satisfaction.

3. **IMPLEMENT URL AND DESCRIPTION FEATURES**: The recommendation system should be adapted to accept a Google Maps URL or a description of a place as input instead of the Place ID. This will allow users to input more descriptive information, making the system more flexible and user-friendly.

4. **CREATE UNIQUE IDENTIFIER FOR EACH VENUE AND IMPROVE UX/UI**: A unique identifier should be created for each venue to replace the Place ID of the Google Maps API. This will enable easier management and better tracking of the data. Additionally, the user experience and interface should be improved to make the recommendation system more intuitive and engaging.

5. **BUILD TAGGING SYSTEM FOR PERSONALIZED SEARCH**: A tagging system should be built to allow users to personalize their search by adding tags for specific features, such as "outdoor seating" or "vegetarian options." This will make the recommendation system more tailored to individual preferences.

6. **GROW DATABASE TO INCLUDE MORE TYPES OF VENUES**: The database should be expanded to include other types of venues, such as bars, cafes, clubs, etc., to provide a more comprehensive selection of recommendations.

7. **EXPAND REACH TO OTHER CITIES AND COUNTRIES**: Finally, the database should be updated with data from other cities and countries to expand the reach of the recommendation system and provide recommendations for travelers and tourists.

## 5. Further description of the files
- ```1. Database > restaurant_scraper_google_api.ipynb```: Python Jupyter Notebook with which we scraped the data from the Google Places API
- ```1. Database > GPT3.5_feature_extraction_hidden.ipynb```: Python Jupyter Notebook with which we enhanced the data with the "hidden" feature by using OepnAI's GPT3.5 model
- ```1. Database > berlin_zip_codes.xlsx```: Excel file with zip codes from all districts of Berlin. The file serves as input for the restaurant_scraper_google_api.ipynb notebook
- ```1. Database > database.csv```: Final database against which the inserted user location is being measured
- ```2. AI_model > BERTopic_model_creation.ipynb```: Python Jupyter Notebook, with which we trained and tweaked the underlying AI model's parameters, i.e. BERTopic parameters
- ```2. AI_model > BERTopic_model_CPU.joblib```: Final BERTopic model
- ```3. Drop_into_Berlin_App > main.ipynb```: Main file, which is setting up the backend infrastructure (i.e. anvil server)
- ```4. Project Presentation > Drop_into_Berlin_presentation_vFinal.pptx```: Project presentation which gives an overview of the problem and the solution


## 6. Team

- Lukas Bauerschmidt | [LinkedIn](https://www.linkedin.com/in/lukas-bauerschmidt-a4681b14b/)
- Leo Krohne | [LinkedIn](https://www.linkedin.com/in/leo-krohne-03411725b/)