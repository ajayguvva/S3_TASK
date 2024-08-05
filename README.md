# S3_TASK

**1.	Create a S3 bucket** 

      

- [ ]  Navigate to the S3 service in the AWS Management Console.
- [ ]       Create a new bucket (example: [task3-s3]
- [ ]       	Upload files to the bucket as needed.

![image](https://github.com/user-attachments/assets/65d132ca-3315-4f80-9c1d-2544bd01e47e)


**2.	Manage Data Lifecycle**

     

- [ ]  	Go to the S3 bucket you created.
- [ ]       	Select the "Management" tab.
- [ ]       	Under "Lifecycle rules," create a new rule.
- [ ]       	Enter a rule name {example task75}
- [ ]       	Choose a rule scope trick on the Apply to all objects in the bucket
- [ ]       	Set the rule to delete objects 75 days after creation.

**3.	Retrieve Old Versions of Files**

     

- [ ]  	Navigate to your S3 bucket.
- [ ]       	Go to the "Properties" tab.
- [ ]       	Enable versioning. This will allow you to keep track of all changes to your files.

**4.	Host a Static Website on AWS S3**

  

- [ ]       Upload your static website files (index.html, styles.css, and other resources) to the S3 bucket.

![image](https://github.com/user-attachments/assets/1db441d8-9956-4fce-8cbb-ae6881617a4d)



**Files Provided:**
      

- [ ]  	**index.html:** The main webpage.
- [ ]       	**error.html:** The error page when an invalid domain is used.
- [ ]       	**styles.css:** The stylesheet for the website.

- [ ]       	 Enable "Static website hosting" in the bucket properties.

- [ ]           Specify the index document (e.g., index.html) and error document (e.g., error.html).

![image](https://github.com/user-attachments/assets/90bb9fb3-a2f5-446a-af55-1b1165bddd46)


Now click on the permission tab and click on bucket policy then click on edit and paste below code
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::task3-s3/*"
        }
    ]
}
```

**Explanation :**

This policy allows public read access to the files in the bucket, enabling users to view the static website hosted on S3.

**•  Version: "2012-10-17"**
This specifies the version of the policy language. The date format indicates when this version of the policy language was introduced. Using this version ensures that the policy adheres to the syntax and features available as of that date.

**•  Statement:**
This is an array that contains one or more individual policy statements. In this case, there's only one statement.

**•	Sid: "PublicReadGetObject"**
The statement identifier (Sid) is an optional field that provides a unique identifier for the statement. In this case, it suggests that the policy allows public read access.

**•	Effect: "Allow"**
This specifies whether the policy allows or denies the specified action. Here, the effect is "Allow," meaning the action described will be permitted.

**•	Principal: "*"**
This field specifies the users or accounts to which the policy applies. The "*" means it applies to all users, making the bucket public.

**•	Action: "s3:GetObject"**
This defines the specific actions that are allowed or denied. In this case, s3:GetObject is the action that allows users to retrieve (read) objects from the S3 bucket.

**•	Resource: "arn:aws:s3:::task3-s3/*"**
This specifies the resources to which the policy applies. The Amazon Resource Name (ARN) format is used here. "arn:aws:s3:::task3-s3/*" means that the policy applies to all objects within the task3-s3 bucket.

Now click on the properties and scroll down and copy the Bucket website endpoint.
http://task3-s3.s3-website-us-east-1.amazonaws.com

now open the browser and paste the above link to open web page.
![image](https://github.com/user-attachments/assets/91582fe0-d873-4c74-9429-119d3eb83da1)

This setup ensures that the application can store, manage, and serve files efficiently while providing the necessary features like versioning, lifecycle management, and error handling.
