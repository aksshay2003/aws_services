# 🧪Hosting a Static Website on AWS S3

This experiment walks through the process of creating an Amazon S3 bucket, uploading a ReactJS application, and configuring it as a static website.

## 🔧 What Was Done

- **Created an S3 Bucket**
  - Configured with versioning, encryption (SSE-S3), and proper naming rules.
- **Access Management**
  - Disabled Block Public Access and added a bucket policy to allow public `GET` access.
- **ReactJS Web App**

  - Built a simple app that:
    - Takes a user's name input.
    - Displays a welcome message like:  
      _“Hi ‘Name!!!’ Welcome to S3 Bucket”_
  - Built the app using `npm run build`.
  - Uploaded the build folder files to the S3 bucket.

- **Enabled Static Website Hosting**
  - Set the hosting type to "Host a static website".
  - Defined `index.html` as the entry point.

## 🌐 Final Output

Once configured, the application is publicly accessible via the S3 static website URL, such as:
