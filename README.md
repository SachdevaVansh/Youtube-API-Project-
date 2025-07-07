# YouTube API Analysis Project

An analytical project using the **YouTube Data API v3** to extract, analyze, and display structured data from a YouTube channel. This project is entirely built using Python within a Jupyter Notebook environment.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Technologies Used](#technologies-used)
4. [Steps Involved](#steps-involved)
5. [Challenges Faced](#challenges-faced)
6. [Results and Outputs](#results-and-outputs)
7. [Graphical Analysis](#graphical-analysis)
8. [Future Enhancements](#future-enhancements)
9. [Author](#author)

---

## Project Overview

This project connects to the YouTube API to retrieve data such as:

* Channel-level statistics
* List of all video IDs
* Individual video performance metrics

The data is extracted programmatically and presented using Python data structures and visualizations.

---

## Features

* Fetch detailed channel metrics
* Retrieve a complete list of video IDs from a given channel
* Extract key statistics from individual videos:

  * Views
  * Likes
  * Comments
  * Titles
  * Upload dates

---

## Technologies Used

* Python 3
* Jupyter Notebook
* YouTube Data API v3
* pandas
* requests
* json
* seaborn, matplotlib

---

## Steps Involved

### 1. Channel Statistics Function

Implemented a Python function to retrieve:

* Channel Title
* Subscriber count
* Total video count
* Channel description

### 2. Video ID Collection

Fetched all video IDs by traversing the Uploads playlist of the channel using pagination.

### 3. Video Metadata Function

Developed a loop to iterate over each video ID and call the API to collect:

* Video Title
* Published Date
* View Count
* Like Count
* Comment Count

---

## Challenges Faced

* **API Pagination**: Managed through careful use of `nextPageToken` to retrieve all video data.
* **Quota Management**: Avoided excessive API usage by batching requests efficiently.
* **Data Cleaning**: Needed to handle missing values and inconsistencies in the response JSON.

---

## Results and Outputs

* Created a pandas DataFrame holding video-level details
* Statistical summaries of channel performance

---

## Graphical Analysis

This section includes key visualizations created in the project for better insight into YouTube channel data.

### Top Channels by Subscribers

```python
sns.set(rc={'figure.figsize':(10,8)})
ax = sns.barplot(x='Channel_name', y='Subscribers', data=channel_data)
ax.plot()
```
![image](https://github.com/user-attachments/assets/955d759d-1474-4649-9618-20f6a9467da9)


**Insight**: This chart helps rank the channels based on subscriber count, giving a clear view of which channels have the largest audience reach.

### Top Channels by Views

```python
ax = sns.barplot(x='Channel_name', y='Views', data=channel_data)
```
![image](https://github.com/user-attachments/assets/84ce6463-c8f9-4c6b-8562-a009dd2666cc)


**Insight**: This bar plot showcases total views per channel, indicating overall content consumption irrespective of subscriber size.

### Channels by Total Videos

```python
ax = sns.barplot(x='Channel_name', y='Total_videos', data=channel_data)
```
![image](https://github.com/user-attachments/assets/dde3f7a2-8059-48b8-8f34-796302a66450)

**Insight**: Reveals which channels are the most prolific in terms of content volume, not necessarily correlated with popularity.

### Top 10 Most Viewed Videos

```python
sns.set(rc={'figure.figsize':(8,10)})
ax1 = sns.barplot(x='Views', y='Title', data=top10_videos)
```
![image](https://github.com/user-attachments/assets/f3a20c7a-8ae6-4c3c-a223-5bfebea7ec05)


**Insight**: Lists the individual videos that performed best by views, offering valuable clues about trending topics and viewer interests.

---

## Future Enhancements

* Export data to CSV for further offline use
* Add NLP-based title/topic analysis
* Create a dashboard using Plotly Dash or Streamlit
* Automate periodic data extraction with scheduling

---

## Author

**Vansh Sachdeva**

This project was created for understanding and exploring the YouTube API for data analysis use cases.

---
