# YouTube Channel Analytics and Popular Video Analysis

This project is designed to provide insights and analytics for YouTube channels and their popular videos. It utilizes the YouTube Data API to gather data on channels, their videos, and video statistics.

## Prerequisites
Before you can use this project, you need to have the following set up:

1. **Google API Key**: You will need a Google API Key to access the YouTube Data API. You can obtain one by following the instructions provided by Google.

2. **Python and Required Libraries**: Make sure you have Python installed on your system. You also need to install the following libraries: pandas, google-api-python-client, seaborn, and matplotlib. You can install these libraries using pip:

   ```python
   pip install pandas google-api-python-client seaborn matplotlib
   ```

## Usage

### Gathering Channel Data

1. Set up your Google API Key in the `api_key` variable in the code.

2. Specify the `channel_ids` list with the YouTube channel IDs you want to analyze.

3. Run the `get_channel_stats` function to gather data about the specified channels, such as their names, descriptions, subscriber counts, view counts, and more.

### Visualizing Channel Data

1. After gathering channel data, you can use the `create_barplot` function to visualize this data. The function creates bar plots to compare channel statistics, such as view counts, subscriber counts, and video counts.

   ```python
   create_barplot(channel_data, 'Channel_name', ['views_count', 'subscribers', 'video_count'])
   ```

### Analyzing Popular Videos

1. Use the `get_playlist_id` function to get the playlist ID of a specific channel. Provide the channel name as an argument.

   ```python
   playlist_id = get_playlist_id(youtube, "Channel Name")
   ```

2. Obtain the video IDs from the playlist using the `get_video_ids` function. This function retrieves video IDs from the specified playlist.

   ```python
   video_ids = get_video_ids(youtube, playlist_id)
   ```

3. Fetch details of the individual videos, including titles, publication dates, view counts, likes, and comments, using the `get_video_details` function.

   ```python
   video_data = get_video_details(youtube, video_ids)
   ```

4. Visualize the most popular videos based on views, likes, and comments using the `create_popular_videos` function.

   ```python
   popular_by_views = create_popular_videos(video_data, 'views_count')
   popular_by_likes = create_popular_videos(video_data, 'Likes')
   popular_by_comments = create_popular_videos(video_data, 'Comments')
   ```

### Visualizing Popular Videos

1. The project also includes code to create bar plots and scatter plots to visualize popular videos based on views, likes, comments, and other metrics.

   - The code creates bar plots to show the most viewed videos, liked videos, and videos with the most comments.
   - It also generates scatter plots to analyze the relationship between views, likes, and comments.

## Acknowledgments
This project utilizes the YouTube Data API provided by Google to fetch channel and video data.

## License
This project is open-source and can be used and modified under the [MIT License](LICENSE).
