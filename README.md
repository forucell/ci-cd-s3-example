# Build and Deploy React App to AWS S3 using CircleCI



## Step 1: Create your app
```
$ npx create-react-app ci-cd-s3-example
  cd example-app
  npm start
```

## Step 2: Push to Github
Create repo and push your project to the Github repo
```
$ git init
  git add .
  git commit -m "first commit"
  git branch -M main
  git remote add origin https://github.com/account-name/project-name.git
  git push -u origin main
```

## Step 3: Setup AWS S3 Bucket

1. The first step is to create an IAM user with programatic access and save Access and Secret keys.

2. The next step is to assign Administrative Access to the user.

3. Next step on AWS is to Create Bucket withh all public access.

4. On the Permissions page, under Bucket policy, paste the following code. 

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::bucket-name/*"
        }
    ]
}
```

5. Click on Properties, go down to Static website hosting. Enable static website.

6. Click edit, type index.html inside index document and save.

## Step 4: Setup Circleci



