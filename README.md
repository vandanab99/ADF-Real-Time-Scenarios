# ADF-Real-Time-Scenarios

Project 1:

Situation: I needed to create an Azure Data Factory (ADF) pipeline to copy files from one folder to another within Azure Data Lake Storage (ADLS). The challenge was to ensure each file retained its original name in the new folder, requiring a dynamic solution for handling multiple files efficiently.

Task: My task was to design a robust ADF pipeline that dynamically copied files from the source folder to the destination folder, preserving each file's name and making the process scalable for various file sets.

Action:

Create Linked Services: Set up linked services in ADF to establish a secure connection to the ADLS storage account.
![image](https://github.com/user-attachments/assets/3459a0e8-99b7-416b-9ae4-be7c983f5de2)


Create a Dataset: Created a dataset to specify the location of files in the source folder.
![image](https://github.com/user-attachments/assets/80fbdffe-f653-4a2a-b389-7257d88ceb50)


Fetch File Names Dynamically: Used the Get Metadata activity to retrieve the list of files from the source folder, setting the field list to Child Items to capture each file's name dynamically.
![image](https://github.com/user-attachments/assets/42dd34fd-0923-4cd5-94e6-e5087d069578)


Loop Through Files: Implemented a ForEach activity to iterate through each file retrieved by the metadata activity. Within this loop, I used a Copy activity with dynamic parameters to assign each file its original name in the destination folder.
![image](https://github.com/user-attachments/assets/0cb003c5-41ce-4289-8c3b-c36769603b6a)
![image](https://github.com/user-attachments/assets/58de8685-df39-43a9-9d25-235666bb8ec1)
![image](https://github.com/user-attachments/assets/f5db12c7-d50a-45dd-9102-b4d317dd807b)
![image](https://github.com/user-attachments/assets/cb1714d3-2485-415e-98a9-6b141d6b01f8)
![image](https://github.com/user-attachments/assets/be16a7df-f439-4a00-8cbb-803c971c66a3)
![image](https://github.com/user-attachments/assets/b3c22cac-738d-41d3-bad0-3a6dfd9639c3)

Result: The pipeline successfully automated the process, copying files to the destination folder with their original names. This dynamic solution enabled efficient file transfers without requiring manual updates, ensuring data consistency and minimizing processing time.

![image](https://github.com/user-attachments/assets/51411097-b61a-4268-9224-2038bb4630f1)
![image](https://github.com/user-attachments/assets/4a8df522-f94a-4db6-ae2e-d66d2c88cbae)


Project 2:
Situation: I was tasked with creating an Azure Data Factory (ADF) pipeline to efficiently transfer files between folders in Azure Data Lake Storage (ADLS). The main challenge was to ensure that only non-empty files were transferred, optimizing storage and reducing unnecessary data movement.

Task: My goal was to design a pipeline that would dynamically filter out empty files, transferring only those containing data from the source to the destination folder. This required setting up the pipeline to detect and handle file sizes effectively.

Action:

Configure ADF for ADLS: Created linked services to connect ADF to the source and destination folders in ADLS.
Set up Metadata and File Validation: Used the Get Metadata activity to retrieve file information from the source folder, setting it to check each file’s size.
Loop and Filter with ForEach Activity: Implemented a ForEach activity to iterate through files, dynamically validating each one’s size to confirm it wasn’t empty.
Execute Conditional Copy: Within the ForEach loop, applied a Copy activity with conditional logic, transferring only files that met the non-empty requirement to the destination folder.
Result: The pipeline successfully automated the selective transfer of non-empty files. By eliminating empty files from the process, it optimized storage and processing costs, enhancing the efficiency of data management.

This STAR-based description highlights the steps and rationale for your pipeline’s design, showing how you ensured the solution was both efficient and scalable. Let me know if you'd like any further adjustments!
