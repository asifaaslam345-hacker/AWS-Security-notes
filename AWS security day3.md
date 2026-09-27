# Class 3 — Migration, Shared Responsibility & IAM Basics

## 1. Cloud Migration

Cloud Migration ka matlab hai kisi application, website, database ya IT system ko apne khud ke servers (on-premises) se Cloud par le jaana.

Misal: agar ek company ka application uske apne physical server par chal raha ho, aur wo usay AWS par move kar de, to isko Cloud Migration kehte hain.

---

## 2. Migration ke 6 Tareeqe (6 R's)

### 1. Rehost
Isay Lift and Shift bhi kehte hain. Application ko baghair zyada change kiye, jaisa hai waisa hi Cloud par move kar dete hain.

Example: Existing Server → AWS EC2

### 2. Replatform
Application ko Cloud par move karte waqt thodi si optimization kar dete hain, lekin basic structure same rehta hai.

Example: Application ko AWS par move karke uske saath managed database service use karna.

### 3. Repurchase
Purani software ko migrate karne ke bajaye, uski jagah nayi Cloud-based service use karna shuru kar dete hain.

Example: Purani Software → SaaS Solution

### 4. Refactor / Re-architect
Application ko dobara se design karte hain taake wo Cloud ki khoobiyon ka poora faida utha sake.

Example: Purani application ko microservices ya serverless design mein tabdeel karna.

### 5. Retire
Jo applications ab kaam ki nahi rahin, unko band kar dena ya hata dena.

Example: Purani application jo company ab use nahi karti.

### 6. Retain
Application ko abhi Cloud par nahi le jate, use jahan hai wahin rehne dete hain.

Example: Aisi purani application jise abhi migrate karna theek nahi.

---

## 3. Shared Responsibility Model

Iska matlab hai ke AWS ki security ki zimmedari AWS aur customer dono ke darmiyan baati hoti hai.

### Security OF the Cloud
Ye zimmedari AWS ki hoti hai. AWS apna poora infrastructure secure rakhta hai, jaise:
- Physical Data Centers
- Hardware
- Networking
- Physical Security

### Security IN the Cloud
Ye zimmedari customer ki hoti hai. Customer ko apna secure rakhna hota hai:
- Data
- Users
- Passwords
- IAM Permissions
- Applications
- Security Settings

**Simple example:** AWS building aur uski physical security sambhalta hai, jabke customer building ke andar apna data aur resources sambhalta hai.

---

## 4. Har Service Mein Zimmedari Ka Farq

Jitni service zyada managed hoti hai, customer ki zimmedari utni kam hoti hai.

| Service | AWS ki Zimmedari | Customer ki Zimmedari |
|---|---|---|
| EC2 | Physical infrastructure | OS, Applications, Data, Security Settings |
| RDS | Infrastructure aur Database Platform | Data, Users, Access, Configuration |
| Lambda | Infrastructure aur Runtime | Code, Data, Permissions |

**EC2:** Customer ko zyada cheezein khud manage karni parti hain — OS, applications, data, security settings.

**RDS:** AWS database ka infrastructure aur platform khud sambhalta hai, is liye customer ki zimmedari EC2 se kam hoti hai.

**Lambda:** AWS servers aur infrastructure khud manage karta hai, customer sirf code, data aur permissions par tawajju deta hai.

**Yaad rakhein:**
EC2 → Customer ki zyada zimmedari
RDS → Customer ki kam zimmedari
Lambda → AWS zyada manage karta hai

---

## 5. IAM — Identity and Access Management

IAM ka poora naam Identity and Access Management hai.

IAM AWS mein identities aur permissions manage karne ke liye use hota hai.

Iska maqsad yeh decide karna hai: kaun AWS resources ko access kar sakta hai, aur wo kya kaam kar sakta hai?

**Example:** Ek employee ko S3 files padhne (read) ki ijazat di ja sakti hai, lekin unko delete karne ki ijazat nahi di jati.

---

## 6. Authentication vs Authorization

### Authentication
Iska matlab hai identity verify karna — "Aap kaun hain?"

Example: Username aur password se AWS account mein login karna.

### Authorization
Iska matlab hai user ko ijazat dena ke wo kya kaam kar sakta hai — "Aap kya kar sakte hain?"

Example: User S3 files padh sakta hai, lekin delete nahi kar sakta.

| Concept | Matlab |
|---|---|
| Authentication | Aap kaun hain? |
| Authorization | Aap kya kar sakte hain? |

---

## 7. IAM ke Bunyadi Elements — User aur Group

### IAM User
IAM User AWS account ke andar ek individual identity hoti hai. Ye kisi bhi banda ya kisi specific zaroorat ko represent kar sakti hai.

Example: Developer, Security Engineer, Administrator

Har IAM User ko uski zaroorat ke mutabiq alag permissions di ja sakti hain.

### IAM Group
IAM Group kayi IAM Users ka ek collection hota hai. Iska fayda yeh hai ke har user ki permissions alag se manage karne ke bajaye, group level par ek saath manage ki ja sakti hain.

Example: Developers Group mein Ali, Ahmed, Sara shamil hain. Agar is group ko koi permission di jaye, to sab members ko wo permission mil jati hai.

**Simple concept:**
User = Ek individual identity
Group = Kayi users ka collection

---

## Quick Revision

| Topic | Simple Matlab |
|---|---|
| Cloud Migration | System ko Cloud par le jaana |
| Rehost | Seedha Cloud par move karna |
| Replatform | Thodi change ke saath move karna |
| Repurchase | Purani solution ki jagah nayi lena |
| Refactor / Re-architect | Application ko dobara design karna |
| Retire | Purani system ko hata dena |
| Retain | System ko wahin rehne dena |
| Shared Responsibility | AWS aur customer dono security ke zimmedar hain |
| Security OF the Cloud | AWS ki zimmedari |
| Security IN the Cloud | Customer ki zimmedari |
| Authentication | Aap kaun hain? |
| Authorization | Aap kya kar sakte hain? |
| IAM User | Ek individual identity |
| IAM Group | Kayi users ka collection |
| EC2 | Customer ki zyada zimmedari |
| RDS | AWS zyada manage karta hai |
| Lambda | AWS underlying infrastructure manage karta hai |
