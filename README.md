# Olympic Dashboard - Power BI Paris 2024 Olympic Games

## An Interactive Analysis of the Upcoming Global Sporting Event
Dive into the world of sports analytics with our Power BI Paris 2024 Olympic Games Dashboard. This comprehensive and interactive dashboard is designed to provide detailed insights and visualizations for the highly anticipated Paris 2024 Olympics. Harnessing the power of Power BI, Python, and data from Kaggle, this project offers a dynamic way to analyze and explore Olympic-related data, all in one place.

![Dashboard Overview](https://github.com/user-attachments/assets/30600da6-ac1c-4b34-b1ad-a8ce1d400acb)
![Additional Visual](https://github.com/user-attachments/assets/4e437ec4-098b-4975-a6f3-fee3c7eb044d)

## What You Get with This Power BI Dashboard

### Comprehensive Olympic Data
Track and analyze the performance of athletes, countries, and sports in the Paris 2024 Olympics. Get real-time updates on medal tallies, athlete profiles, country-wise performances, and event schedules, all presented in visually appealing charts and graphs.

![Data Visualization](https://github.com/user-attachments/assets/441f7aea-7d09-4279-95db-36e3302c4e60)

### Dynamic Visualizations
The dashboard features a variety of interactive visuals, allowing users to filter and explore data by country, sport, event, or athlete. Easily compare performances across different nations and sports to understand trends and key insights.

![Interactive Visualization](https://github.com/user-attachments/assets/85359644-4bd5-4b4b-80ff-10f2d3a36c10)

### Data Integration and Automation
The dashboard leverages data from Kaggle, seamlessly integrated using Python scripts to pull the latest data via the Kaggle API. This ensures users always have access to the most up-to-date information for deep analysis and reporting.

### Advanced Analytics with Python
The use of Python adds advanced analytics capabilities, including predictive modeling for medal forecasts, performance trend analysis, and historical comparisons. Gain insights into which countries or athletes are expected to excel and why.

### User-Friendly Interface
Whether you are a sports analyst, a fan, or a data enthusiast, the dashboard is designed to be intuitive and easy to use. No prior experience with data analytics is needed to explore and gain insights from this dashboard.

    ```python
    import kaggle
    import os
    import pandas as pd
    
    # Set Kaggle API credentials directory
    os.environ['KAGGLE_CONFIG_DIR'] = 'C:/Users/faisa/.kaggle'  # Update this path to your Kaggle configuration directory
    
    # Specify the dataset identifier
    dataset = 'piterfm/paris-2024-olympic-summer-games'
    
    # Set the download path
    download_path = 'C:/Users/faisa/Downloads/Power BI_Imp Summary/Olympic/Source'  # Change this to your preferred download directory
    
    # Remove existing files in the folder to prevent duplicates or outdated files
    for file in os.listdir(download_path):
        file_path = os.path.join(download_path, file)
        try:
            if os.path.isfile(file_path):
                os.unlink(file_path)  # Delete the file
                print(f"Deleted {file_path}")
        except Exception as e:
            print(f"Error deleting {file_path}: {e}")
    
    # Download the dataset using the Kaggle API and unzip the files
    kaggle.api.dataset_download_files(dataset, path=download_path, unzip=True)
    
    # List of CSV files to be imported
    csv_files = [
        'athletes.csv',
        'events.csv',
        'medallists.csv',
        'medals.csv',
        'medals_total.csv',
        'schedules.csv',
        'schedules_preliminary.csv',
        'teams.csv',
        'torch_route.csv',
        'venues.csv'
    ]
    
    # Initialize a dictionary to hold DataFrames
    dataframes = {}
    
    # Iterate through each CSV file and load it into a DataFrame
    for file in csv_files:
        # Construct the full path to the CSV file
        file_path = os.path.join(download_path, file)
        
        # Load the CSV file into a Pandas DataFrame
        df = pd.read_csv(file_path)
        
        # Add the DataFrame to the dictionary using the file name as the key
        table_name = file.split('.')[0]  # Remove the .csv extension
        dataframes[table_name] = df


### Key Features

Medal Tally and Analysis: Track the overall medal standings for each country in real-time. Dive deeper into specific countries or sports to understand their performance and historical trends.

Athlete and Event Insights: Get detailed profiles of top athletes, including their historical performances, current form, and event schedules. Analyze which events and athletes are drawing the most attention.

Historical Comparisons and Trend Analysis: Compare the 2024 Olympics with previous events to identify trends, performance improvements, or declines. Visualize data from past Olympic Games to see how countries and athletes have evolved.

Interactive Maps and Charts: Explore geographical data with interactive maps, showing where athletes are coming from, which countries dominate in particular sports, and much more.

Custom Filters and Drill-Downs: Utilize Power BI’s powerful filtering capabilities to drill down into specific data points, such as country performance in a specific sport or the number of medals won by a specific athlete over time.

![image](https://github.com/user-attachments/assets/bebb893f-a8ef-4f5d-bbc5-19992f6c54aa)

### Who will benefit from this dashboard?

Sports Enthusiasts and Fans: Stay updated with the latest statistics and performance data of your favorite athletes and countries in the Paris 2024 Olympics.

Data Analysts and Sports Analysts: Leverage this dashboard to create impactful reports and presentations. Understand trends, analyze performances, and inform strategic decisions based on data.

Content Creators and Journalists: Use the visualizations and data insights to create compelling content, articles, or reports around the Olympics and sports analytics.

Power BI Learners and Enthusiasts: This project serves as a practical, hands-on example for those looking to enhance their skills in data visualization, analytics, and the use of Power BI for sports data.
