# **YouTube Channel Analytics Project**

## **Table of Contents**

- [Motivation](#motivation)
- [Data Source](#data-source)
- [Data Analysis](#data-analysis)

---

## **Description**

I have a youtube channel with 137k views and 500 subscribers. In my channel I post instrumental tracks that I compose for artists to write their own lyrics, and release songs if they have purchased the lease for it. I make music as a hobby for about 4 years now, but releasing them and collaborating with new artists from all around the globe is a fairly new thing for me. I decided to make my data science project about a general analysis of my channel & my music.

![Ekran görüntüsü 2024-11-30 172626](https://github.com/user-attachments/assets/02af43a0-cc64-4279-82ec-4469a1f6752d)

## **Hypothesis**

My hypothesis is that the more effort I put into composing the track, the better it performs. 

## **Motivation**

### **Why Am I Working on This Project?**

**Personal and Professional Development:**

- **Channel Growth:** To understand the factors influencing my YouTube channel's performance, aiming to increase views, likes, and overall engagement.
- **Content Optimization:** By analyzing the relationship between my effort and audience response, I can modify my content strategy for better results.
- **Data Science Application:** This project allows me to apply data analysis techniques to a real-world scenario.

**Creative Ideas:**

- **Effort Evaluation:** Quantify the effort put into each track (e.g., hours spent, complexity) to see how it correlates with audience engagement.
- **Predicting Stuff:** Analyze how different parameters affect others. (For example I have observed that when a view time for a video spikes considerably more than the views for the same video that I made, it means that an artist is writing lyrics and most likely will purchase a lease for the instrumental in the following weeks.) 

---

## **Data Source**

### **Where Did I Get This Data? How Did I Collect It?**

**YouTube Analytics:**

- **Platform Data:** Utilized YouTube Studio's analytics to collect data on views, likes, comments, watch time, audience retention, and demographic information.
- **Data Export:** Scraped the channel information, and video information for my youtube channel. Used Google Cloud API and Youtube Data API for the process.

![image](https://github.com/user-attachments/assets/b4cb8f36-b985-4b25-a931-8d86247d0b06)

**FL Studio:**

- **Time Tracking:** Logged the number of time spent composing each track. Exported in an excel file. The numbers in the .xlsx file represent how many minutes I spent on one track.

![image](https://github.com/user-attachments/assets/ccdd8f07-0c8e-4889-9caa-71f07c24bb90)

---

## **Data Analysis**

These are analysis' for the project.

### **Effort Invested vs. Views, Likes and Comments**

To understand how the effort I put into each track affects its performance, I looked at the time spent composing each instrumental (logged from FL Studio) and compared it to the number of views and likes each video received. This helped me see if there's a correlation between the time investment of a track and audience engagement.

## **Implementation Process**

1. **Getting Channel Info from YouTube API**
   - Used the YouTube Data API to fetch basic info about my channel, like total views, subscribers, and uploads.
   - Made an authenticated API request using my API key (which i revoked before uploading the .ipynb file to github).

2. **Getting Video IDs from YouTube API**
   - Pulled all the 53 video IDs from my channel’s upload playlist using the API.
   - Saved them in a list for the next steps.

3. **Getting Video Info from YouTube API**
   - Fetched detailed data for each video ID, like views, likes, comments, and publish dates.
   - Organized everything into a JSON format.

4. **Putting Data into a DataFrame**
   - Converted the JSON data into a pandas DataFrame.
   - Exported it to Excel to combine with FL Studio project times for better implementation.

5. **Combining FL Studio Data with Video Info**
   - Imported my time logs from FL Studio into Excel.
   - Merged it with YouTube video data using the video publish dates.

6. **Analyzing Video Views and Dates**
   - Looked for trends by plotting views against the publish dates of each video.

7. **Analyzing FL Studio Times and Dates**
   - Plotted effort (hours spent) against publish dates to see if my effort increased over time.

8. **Pairplots of Effort, Views, Likes, Comments**
   - Used `seaborn` to create pairplots of these values to visualize correlations between them.

9. **Scaled Effort and Views Correlation Chart**
   - Normalized "Effort" and "Views" by multiplying the effort with 100.
   - Plotted them on the same chart with a regression line to visualize the trend.

10. **Regression Analysis**
    - Used linear regression to predict views based on effort.
    - Plotted the regression line on the effort-views chart.

11. **P-Value Analysis**
    - Ran a hypothesis test to check if effort influences views.
    - Got a p-value of 0.000, rejected H0 (null hypothesis), and concluded that effort does cause an increase in views.

---

## **Limitations and Future Plans**

Limitations: The FL Studio spent time values may be misleading. For instance if I got a call while composing a track and talked on the phone while the project was open, this analysis would assume that I put unusual effort into that track.

Future Plans: Making a competitive analysis with Youtube channels from similar niches to mine. Analysing what they did with their upload schedule and how much effort they put into their compositions would help me maintain my audience.

---

*By focusing this project on my YouTube channel analytics, I'm integrating my passion for music with data science. This approach not only meets course requirements but also equips me with valuable insights to make better videos.*

---
