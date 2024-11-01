# ADF-Real-Time-Scenarios

Project 1:
Situation: I needed to create an Azure Data Factory (ADF) pipeline to copy files from one folder to another within Azure Data Lake Storage (ADLS). The challenge was to ensure each file retained its original name in the new folder, requiring a dynamic solution for handling multiple files efficiently.

Task: My task was to design a robust ADF pipeline that dynamically copied files from the source folder to the destination folder, preserving each file's name and making the process scalable for various file sets.

Action:

Create Linked Services: Set up linked services in ADF to establish a secure connection to the ADLS storage account.
Create a Dataset: Created a dataset to specify the location of files in the source folder.
Fetch File Names Dynamically: Used the Get Metadata activity to retrieve the list of files from the source folder, setting the field list to Child Items to capture each file's name dynamically.
Loop Through Files: Implemented a ForEach activity to iterate through each file retrieved by the metadata activity. Within this loop, I used a Copy activity with dynamic parameters to assign each file its original name in the destination folder.
Result: The pipeline successfully automated the process, copying files to the destination folder with their original names. This dynamic solution enabled efficient file transfers without requiring manual updates, ensuring data consistency and minimizing processing time.
