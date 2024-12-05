# Project2-472 : Wildfire Watch

# Goal of the project

The goal of this project is to implement threading, file processing and multiprocessing on dataset for forest fires. We want to perform these operations on the data so we can simulate fire spreads and generate emergency alerts when a threshhold is passed. There will be alerts for dangerous conditions that correlate with fire spreads such as high temperatures, low humidities or high winds.

# Significance of the project

This project demonstrates the integration of multithreading in C for real-time data processing, specifically focused on fire risk assessment based on environmental sensor data. The system processes data (temperature, wind speed, humidity, and the fire spread index) and triggers alerts if certain thresholds are exceeded, indicating heightened fire risk. This approach can be applied in wildfire management systems, providing real-time alerts and early warnings, potentially saving lives and property by improving response times to fire outbreaks.

# Installation and Instruction to use
Access the colab link here:
https://colab.research.google.com/drive/1VxsSmNKk1_2zzeX4tmz198-QLIvD6OU_?usp=sharing

# Structure of the code
This C program processes sensor data (such as temperature, wind speed, humidity, and the Fire Spread Index) to check for conditions that may trigger alerts related to forest fire risks. The program uses multithreading for reading the sensor data and processing it in parallel.
### Constants and Thresholds:
The program defines various constants such as MAX_LINE_LENGTH, PROCESSING_DELAY_MS, and thresholds for temperature, wind speed, humidity, and the Fire Spread Index. These thresholds are used to trigger alerts when specific conditions are met.

### Enums and Structs:
ProcessorType enum: Represents different processing tasks (FIRE_SPREAD, ALERTS, VISUALIZATION).
ProcessorArgs struct: Holds the type of processing (ProcessorType) and the processor's name.
FireParameters struct: Holds the parameters parsed from the CSV line (temperature, wind speed, humidity, and initial spread index).

### Global Variables:
sensor_data: A global variable to store a line of sensor data.
data_ready: A boolean flag indicating if the data is ready to be processed.
should_exit: A boolean flag that controls the program's termination.
Synchronization variables: pthread_mutex_t and pthread_cond_t are used to manage access to shared data between threads.

### Helper Functions:
parse_csv_line: This function parses a line of CSV data to extract the temperature, wind, humidity, and Fire Spread Index values.
check_and_alert: This function checks the parsed data against the thresholds and triggers alerts if any condition is met.
process_data: A thread function that processes data, waits for new data, and calls check_and_alert if the processing type is ALERTS.
read_sensor_data: A thread function that reads data from a CSV file line by line and signals the processor threads when new data is available.

### Main Function:
- Creates a reader thread to read sensor data from a file.
- Creates three processor threads to handle different tasks (Fire Spread, Alerts, and Visualization).
- Waits for all threads to finish processing before exiting.

### Flow Chart
![image](https://github.com/user-attachments/assets/e666f2fe-a6ac-4a72-b98d-0f6132cd82a5)

# Functionalities and Test Results
![Screenshot 2024-12-05 153749](https://github.com/user-attachments/assets/0ed82564-57da-4ad0-bd41-8df0dba58730)

# Showcasing the achievement of project goals
We see this project as a huge success especially for people that live or work up in the fire towers in recreational parks. This project can be a great tool to help these workers detect a potential forest fire before it event starts. By keeping track and reporting their daily weather journals, they can prepare for the worst with our tool. The built in alerts can keep emergency protocols at the ready.


# Discussion and Conclusions
In conclusion, our project is able to sucessfully utilize mutlithreading and multiprocessing to analyze fores fire data and draw critical alarms from certain high risk data. By analyzing this high risk data and sending alarms, we can inform the user about potential fires base on certain conditions. Statistical fire trends across periods of time can be introduced to the data to further keep a more safe environment. 
