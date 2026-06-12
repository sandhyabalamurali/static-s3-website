# 🌐 Static Website Deployment on AWS S3

A simple static website built with **HTML & CSS** and hosted on **Amazon S3** as a public static website.

---

## 🚀 Live Demo

🔗 [Click here to view the live website](http://aurora-website-001.s3-website.eu-north-1.amazonaws.com/)


---

## 📁 Project Structure

```
├── index.html       # Main HTML + CSS file
└── README.md        # Project documentation
```

---

## 🛠️ Tech Stack

| Technology | Usage |
|---|---|
| HTML5 | Page structure |
| CSS3 | Styling & layout |
| AWS S3 | Static website hosting |

---

## ☁️ AWS Deployment Workflow

### Step 1 — Create an S3 Bucket

- Go to **AWS Console → S3 → Create Bucket**
- Enter a unique bucket name
- Select your preferred **AWS Region**
- **Uncheck** "Block all public access"

![Create S3 Bucket](<img width="334" height="250" alt="image" src="https://github.com/user-attachments/assets/27615c5a-5ede-45e0-820c-029f3d608f5b" />
)

---

### Step 2 — Enable Static Website Hosting

- Open your bucket → Go to **Properties** tab
- Scroll to **Static website hosting** → Click **Edit**
- Select **Enable**
- Set **Index document** to `index.html`
- Save changes


---

### Step 3 — Set Bucket Policy (Make it Public)

- Go to **Permissions** tab → **Bucket Policy**
- Paste the following policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```

> ⚠️ Replace `your-bucket-name` with your actual bucket name.


---

### Step 4 — Upload Website Files

- Go to the **Objects** tab → Click **Upload**
- Add your `index.html` file
- Click **Upload**

---

### Step 5 — Access the Live Website

- Go to **Properties → Static website hosting**
- Copy the **Bucket website endpoint** URL
- Open it in your browser 🎉

![Live Website](<img width="806" height="524" alt="image" src="https://github.com/user-attachments/assets/7fda829b-a5fb-46c9-b8ff-015dc7303f52" />
)


---

## 📌 How to Update the Website

1. Edit your `index.html` file locally
2. Go to **AWS S3 Console → Your Bucket → Upload**
3. Re-upload the updated `index.html`
4. Refresh the browser — changes are live instantly ✅

---
