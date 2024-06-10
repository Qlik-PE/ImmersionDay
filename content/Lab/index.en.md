---
title: "Lab : Real-time SAP Data Analytics on AWS using Qlik Cloud"
weight: 20
---

# AWS Qlik Immersion Day Workshop

CONTENTS

[Document Version](#document-version)

[Introduction](#introduction)

[Agenda](#agenda)

[Objective for the Workshop](#objective-for-the-workshop)

[Overview](#overview)

[Goals for this Workshop](#goals-for-this-workshop)

[Getting Started](#getting-started)

[Getting access to your lab environment](#getting-access-to-your-lab-environment)

[Accessing QCDI(Qlik Cloud Data Integration)](#getting-access-to-your-lab-environment)

[Tutorial](#tutorial)

[Prerequisites](#prerequisite-for-starting-tutorials)

[Navigating the Tutorial](#navigating-the-tutorial)

[Qlik Lab 1 - SAP to Kafka in Realtime](#qlik-lab-1-:-sap-to-kafka-in-realtime)

[Qlik Lab 2 - SAP to Amazon Aurora PostgreSQL in Realtime](#qlik-lab-2-:-sap-to-amazon-aurora-postgresql-in-realtime)

[Qlik Lab 3 - SAP to Amazon Redshift in Realtime](#qlik-lab-3-:-sap-to-amazon-redshift-in-realtime)

[Resources](#resources)

[Videos](#videos)

[Contacts](#contacts)

[AWS Partner Team)](#aws-partner-team)

[Qlik Partner Team](#qlik-partner-team)

[Register for a free SAP to Qlik POC](#register-for-a-free-qlik-qlik cloud data integration-poc)

# Preface

This document outlines steps to be followed by participants to complete the AWS Qlik Immersion Day workshop.

## Document Version

  ------------------------------------------------------------------------------
  |Version   |Description                  |Author             |Workshop Version
  |--------- | ----------------------------|------------------ |---------------
  |1.0       |Initial Version to fulfill AWS Immersion Day requirements for Workshop Platfrom     |John Park, Qlik Partner Engineering & Sathisan Vannadil, AWS|AMI - AWS Immersion Day v1.8
  |2.0       |Initial Version to fulfill AWS Immersion Day requirements for Workshop Platfrom with modifications to port over to Qlik Cloud Platform    |John Park, Qlik Partner Engineering |AMI - AWS Immersion Day v1.9

# Introduction

## Agenda

Day Agenda (9:30 AM - 12:30 PM)

- **09:10 am**  Data Foundations for analytics and Generative AI on AWS - AWS

- **09:30 am**  Cloud and Generative AI on AWS - AWS

- **09:50 am**  Qlik Cloud Data Integration with AWS and Qlik - Qlik

- **10:10 am**  Workshop Account Sign-up

- **11:00 am** - **Qlik Lab1(Demo)**  SAP to Amazon S3 Using QCDI(Qlik
    Qlik Cloud Data Integration)
- **11:15 am** - **Qlik Lab2**  SAP to Amazon Aurora Using QCDI(Qlik
    Qlik Cloud Data Integration)
- **11:45 am** - **Qlik Lab3**  SAP to Amazon Redshift Using QCDI(Qlik
    Qlik Cloud Data Integration)
- **11:55 am** - **Qlik - Presentation**
  - **Demo:** Agile data warehouse automation for SAP Data using Qlik Cloud Data Integration - Qlik
- **12:15 pm** **Qlik Data Analytics**
  - **Demo:** Modern, AI-powered analytics: Qlik Cloud Analytics - Qlik
- **12:20 pm** Conclusion & AWS event survey - AWS

## Objective for the Workshop

This tutorial will demonstrate how to use Qlik Cloud to ingest and deliver data in real-time to your various environments. Follow the step-by-step tutorial to quickly load sample data from a SAP S/4 database into your Amazon S3, Amazon Auroa Postgres, Amazon Redshift data warehouse. Then watch as data updates happen in real time and discuss details of Data migration and using Qlik Cloud for your CDC and Transformation tool.

***The Objective of this tutorial is to get introductory hands-on experience using Qlik's Data Integration capabilities not to become an expert at using QCDI(Qlik Cloud Data Integration).***

# Overview

## Goals for this Workshop

1. Learn how to Configure Qlik Cloud Data Integration to Work with Source and Target Endpoints.

2. Learn how to Design Qlik Cloud Data Integration Tasks for Landing and Transforming Data.

3. Learn how to Monitor Qlik Cloud Data Integration Tasks.

Our tutorials will consist of 1 demo to get students to understand the flow of Qlik Cloud Data Integration. Subsequently there is 2 real life scenarios for students get hands on experience with Qlik Cloud Data Integration.

While the tutorial scenario quickly highlights the concept of data ingestion and streaming to PostgresSQL, Amazon S3, and Amazon Redshift there are additional tuning that can be done to make efficiency gains. Qlik Cloud Data Integration can also deliver any data from popular relational database systems, mainframes, or SAP applications that you might have in your enterprise.

# Getting Started

## Preface

Before beginning with the tutorial, we like to tell you that your Qlik and AWS team is here to help you please do not hesitate to reach out.

This lab consists of many components to demonstrate for you how easy it is to create connections in QCDI(Qlik Cloud Data Integration) and execute tasks.

A few of the main technical use cases are following.

- Stream Data to another Database

- Stream Data to Object Store / Kafka Queue

- Stream Data into Cloud Data Warehouse

Inside your AWS account a CloudFormation script ran and created an environment where you have a your own Amazon S3, Amazon Aurora Postgres and Amazon Redshift.

## Getting access to your lab environment

### AWS Environment

At this time, you should be able to access AWS Console for this lab via Workshop Studio

pressing **Open AWS Console** as described earlier.

You should see following resources created for your Lab.

1. Amazon Aurora Postgres
2. Amazon S3 Bucket for Data Lake
3. Amazon Redshift Cluster

## Accessing Qlik Cloud Data Integration for Workshop

Before starting tutorial and labs make sure you can log into the following:
This is the Qlik Cloud Tenant that we will run our workshop in.

<https://tinyurl.com/qliklab>


Please make sure you have received your credentials to log into above tenant.
**If you do not have credentials please check your spam or let the instructor know**


# Tutorial

## Prerequisites for Starting Tutorials

1. Log into Qlik Cloud and Access Qlik Data Integration

2. Create your Person Space inside Qlik Data Integration
    What is your Space ? 
    Spaces are areas of Qlik Cloud Data Integration that are used to create and store data projects. Inside the space, you can also create new data connections using connectors, and manage access to Data Movement gateways. You can use your Personal space, or governed data spaces.

3.**For your Redshift and RDS Instances the passwords are generated and stored in AWS Secrets Manager Service**

Please go into AWS Console and access **AWS Secrets Manager**

![ ](/static/qlik-images/image83.png)


## Navigating the Tutorial

To navigate the tutorial, it is best to follow the steps in order. If for some reason you want to skip to a particular section of the lab you can navigate via the table of contents listed below.

In this tutorial you will be using an SAP HANA DB and S/4 system setup by our team as your source. We will step through setting up connections, so you get an idea of how to unlock your data from SAP System.

## Qlik Lab 1 : SAP to Amazon S3 Data in Realtime

### Step 1 - SAP Source Configuration

The first thing we need to do is create a source endpoint. We do this by clicking the "Manage Endpoint Connections" button at the top of the
screen.

![ ](/static/qlik-images/image12.png)

Pressing "Manage Endpoint Connections" will bring this window.

![ ](/static/qlik-images/image13.png)

From there, click on "Add New Endpoint Connection" button at the top of the screen or the "+ New Endpoint Connection" link will bring you
following window.

![ ](/static/qlik-images/image14.png)
To Create an SAP Source End Point for SAP S/4 system you need to take 2
steps:

1. Create an SAP Database Source End Point for **Back End Source End
    Point**

2. Create SAP Application Source End Point using the **Back End Source
    End Point**

For this lab today our public SAP S/4 HANA System uses xxx.xxx.xxx.xxxx IP address.

The IP address for the lab section will be notified to students

This demo relies on S/4 system backed by HANA so we will use SAP HANA DB as **Back End Source End Point**

We will now create an **SAP Database Source Endpoint** using SAP HANA DB:

- Replace the text **New Endpoint Connection 1** with something more
    descriptive like "SAP HANA DB Source."

- Make sure the "Source" radio button is selected,

- and then select "SAP HANA" from the dropdown selection box.

![ ](/static/qlik-images/image15.png)
You will notice as we proceed that the content of the configuration window is context sensitive.

![ ](/static/qlik-images/image16.png)
Fill in the blanks as indicated in the images above:

*Please note only for Instance number will be '2'*

- Server: "xxx.xxx.xxx.xxxx"

- Instance Number: "2"

- User: "SAPHANADB"

- Password: "Ql1k1234"

Click on "Test Connection" button.

Your screen should look like the following with a green check box over Test Connection; indicating that your connection succeeded.

![ ](/static/qlik-images/image17.png)

Assuming so, click "Save" and the configuration of your SAP HANA source
endpoint is complete.

We will now create an **SAP Application Source Endpoint** using SAP Application:

*Please note the version we are using SAP S/4 1909*

- Press +New Endpoint Connection" button at the top of the screen.

```{=html}
<!-- -->
```

- Replace the text **New Endpoint Connection 1** with something more descriptive like SAP Application,

- make sure the Source radio button is selected,

- and then select SAP Application from the dropdown selection box.

![ ](/static/qlik-images/image18.png)
You will notice as we proceed that the content of the configuration
window is context sensitive.

![ ](/static/qlik-images/image19.png)

Fill in the blanks as indicated in the images above:

*Please note only for Instance number will be '00' and Client is '100.'*

- Connection Type: "Application"

- Server name: "XXX.XXX.XXX.XXX"

- Instance Number: "00"

- Client: "100"

- Username: "qlik"

- Password: "qlikpass"

**Very Important Click on Browse button and Select you SAP HANA Database for Backend Endpoint that you created earlier.**

![ ](/static/qlik-images/image20.png)

Press "**OK"** button.

Your screen should look like the following with a green check box overTest Connection; indicating that your connection succeeded.

![ ](/static/qlik-images/image21.png)

Assuming so, click "Save" and the configuration of your SAP Application source endpoint is complete.

Click "Close" to close the window.

### Step 2 - Kafka Target Configuration

Next, we need to configure our Kafka target endpoint. The process is much the same as you saw with the endpoints, and once again you will note that the configuration process is context sensitive as we move along.

As before, the first step in the configuration process is to tell Qlik Cloud Data Integration that we want to create a new endpoint. If you are back on the main window, you will need to click on "Manage Endpoint Connections" button.

![ ](/static/qlik-images/image12.png)

and then press the "+ New Endpoint Connection" button.

![ ](/static/qlik-images/image22.png)

and you will see a window that resembles this:

![ ](/static/qlik-images/image14.png)

We will now create a Kafka Target endpoint:

- Replace the text **New Endpoint Connection 1** with something more descriptive like "Kafka JSON Target."

- Make sure the "Target" radio button is selected,

- Select "Kafka" from the dropdown selection box.

![ ](/static/qlik-images/image23.png)

![ ](/static/qlik-images/image24.png)

![](/static/qlik-images/image25.png)

![ ](/static/qlik-images/image26.png)

Fill in the blanks as indicated in the images above:

- Broker servers: "kafka:29092"

- Security/Use SSL: NOT Checked.

- Security/Authentication: None

- Message Properties/Format: "JSON"

- Message Properties/Compression: "None"

- Data Message Publishing/Specific topic: "Separate topic for each table"

- Data Message Publishing/Partition strategy: "By message key

- Data Message Publishing/Message key: "Primary key columns"

- Metadata Message Publishing/Publish: "Do not publish metadata messages".

- Metadata Message Publishing/Wrap data: "NOT Checked".

and then click on "Test Connection". Your screen should look like the following, indicating that your connection succeeded.

![ ](/static/qlik-images/image24.png)
Assuming so, click Save and the configuration of your Kafka target endpoint is complete. Click "Close" to close the window.

### Step 3 - Configure Your Task

Now that we have configured our SAP source and Kafka target endpoints, we need to tie them together in what we call a Qlik Cloud Data Integration **task**. In
short, a task defines the following:

- A source endpoint

- A target endpoint

- The list of tables that we want to capture.

- Any transformations we want to make on the data.

To get started, we need to create a task. Click on the "+ New Task" button at the top of the screen.

![ ](/static/qlik-images/image27.png)

Once you do, a window like below will pop up:

![ ](/static/qlik-images/image28.png)

Give this task a meaningful name like "SAP to Kafka". For this task we will take the defaults:

- Name: "SAP to Kafka"

- Please select: Unidirectional

- Full Load: enabled *(Blue highlight is enabled; click to enable /
    disable.)*

- Apply Changes: enabled *(Blue highlight is enabled; click to enable
    / disable.)*

- Store Changes: disabled *(Blue highlight is enabled; click to enable
    / disable.)*

When you have everything set, press "OK" to create the task. Once you have completed this step you will see a window that looks like this:

![ ](/static/qlik-images/image29.png)

Qlik Cloud Data Integration is all about **ease of use**. The interface is point-and-click, drag-and-drop. To configure your task, we need to select a source endpoint (SAP Application) and a target endpoint (Kafka). You can either drag the "SAP Application Source" endpoint from the box on the left of the screen and drop it into the circle that says Drop source endpoint here, or you can click on the arrow that appears just to the right of the endpoint when you highlight it.

![ ](/static/qlik-images/image30.png)
Repeat the same process for the Kafka Target endpoint. Your screen should now look like this:

![ ](/static/qlik-images/image31.png)
Our next step is to select the tables we want to qlik cloud data integration from SAPApplication into Kafka. Click on the "Table Selection\..." button in the
top center of your browser.

![ ](/static/qlik-images/image32.png)

and from there select the "ADEMO" Business Groups.

![ ](/static/qlik-images/image33.png)

Press the "Search" button. This will retrieve a list of all the Tables in the *ADEMO* group.

![ ](/static/qlik-images/image34.png)

In the **SAP to Redshift** and **SAP to Aurora Postgres** task, we willc apture all the tables in the schema. For this exercise, we will instead choose only a few tables.

- VBAP

- VBAK

- MARA

Select each table from the **Results** list and press the "\>" button to move them into the **Selected Tables** list. Note that multi-select is enabled. You can select the tables all at once or move them individually.

![ ](/static/qlik-images/image35.png)

At this point we could define transformations on the selected tables if we wanted, but we will keep it simple for this part of the lab and move
the data as is instead. Just push "OK" at the bottom of the screen.

![ ](/static/qlik-images/image36.png)

That completes configuration of the task. We are now ready to and run
it. Press "Save" at the top left of the window and then press "Run".

![ ](/static/qlik-images/image37.png)

###

### Step 4 - Run Your Task

When you press "Run" Qlik Cloud Data Integration will automatically switch from **Designer** mode to **Monitor** mode. You will be able to watch the status of the full load as it occurs, and then switch to monitoring view.

![ ](/static/qlik-images/image38.png)

While in monitoring login to Kafdrop and look and the Kafka Topics via. **URL: YOUR_SERVER_IP_ADDRESS:9000**

Initially you will not see your Kafka Topics configured for each table but after a few second you see it populate from SAP Application via Qlik
Qlik Cloud Data Integration.

Pre-Load:

![ ](/static/qlik-images/image10.png)

After Initial Load:![A screenshot of a computer Description automatically generated](/static/qlik-images/image39.png)

Now switch back to Qlik Cloud Data Integration Task manager. After **Full Load** is complete, click on the "Completed" bar to display the tables. If there
is DML activity running in the background. Click on the "Change Processing" tab to see it in action.

![ ](/static/qlik-images/image40.png)

*Note: for SAP lab we did not create a Daemon to simulate DML activity but you may ask your instructor for explanation. Example DML Activity in from MySQL Lab.*

If you would like to see some of the messages we are delivering to Kafka, log on to Kafdrop and click on Topics to view the messages.

![ ](/static/qlik-images/image41.png)

When you have seen enough, you can declare Victory for this part of the Lab!

Press "Stop" in the top left corner of the **Qlik Cloud Data Integration** console to
end the task. Click "Yes" in the confirmation dialog and close the **SAP to Kafka** tab or click on the "TASKS" tab to return to
the main window.

![ ](/static/qlik-images/image42.png)

### Summary

Following concepts were covered in the lab:

- Defined access and authentication into an SAP Application source and a Kafka target

- Defined the source tables from which you want to create Kafka Topics/Messages

- Configured the SAP Application to Kafka task.

- Captured initial data from the source without while maintaining business continuity (DML activity was going on in the background to simulate users working on the source database)

- Automatically created Kafka messages from the initial table state

- Captured all new transactions which were happening while the initial load was running

- Turned net new data into Kafka messages.

- Observed change data being recorded as it is sent to and applied at the target.

## Qlik Lab 2 : SAP to Amazon Aurora PostgreSQL in Realtime

### Step 1 - SAP Source Configuration

> Please see Step above [here](#step-1---sap-source-configuration)

### Step 2 - Amazon Aurora PostgreSQL Target Configuration

Next, we need to configure our Amazon Aurora PostgreSQL target endpoint. The process is much the same as you saw with the SAP source, and once
again you will note that the configuration process is context sensitive as we move along.

During the initial setup of the lab Amazon Aurora Database has been created for your need. As before, the first step in the configuration process is to tell Qlik Cloud Data Integration that we want to create a new endpoint. If you are back on the main window, you will need to click on "Manage Endpoint Connections" button.

![ ](/static/qlik-images/image12.png)

and then press the "+New Endpoint Connection" button.

![ ](/static/qlik-images/image22.png)

and you will see a window that resembles this:

![ ](/static/qlik-images/image14.png)

We will now create a PostgreSQL Target endpoint:

- Replace the text **New Endpoint Connection 1** with something more descriptive like "Aurora Postgres Target".

- Make sure the Target radio button is selected,

- Select "PostgreSQL" from the dropdown selection box.

![ ](/static/qlik-images/image43.png)
Here is where you will go into AWS Console and Find your connections end points.

Please click on RDS to see Dashboards.

![ ](/static/qlik-images/image44.png)

At the RDS Dashboard find you cluster pre created.

![ ](/static/qlik-images/image45.png)

Click on your Database Writer Instance and you should be able to locate the **endpoint address.**

![ ](/static/qlik-images/image46.png)

Fill in the blanks as indicated in the image above:

- Host: ***You Connection from Above Figure***

- Port: "5432"

- User: "qlik123"

- Password: *please access AWS Secrets Manager for your RDS password*

- Database: "aws_immersion_day"

- Security/SSL Mode: "disable"

and then click on "Test Connection". Your screen should look like the following, indicating that your connection succeeded.

![ ](/static/qlik-images/image47.png)

Assuming so, click "Save" and the configuration of your Postgres target endpoint is complete. Click "Close" to close the window.

*For more details about using PostgreSQL as a target, please review the section "Using a PostgreSQL-Based as a Target" in Chapter 9 "Adding and Managing Target Endpoints" of the*

### Step 3 - Configure Your Task

Now that we have configured our SAP source and Aurora Postgres target endpoints, we need to connect them together in what we call a
Qlik Cloud Data Integration **task**. In short, a task defines the following:

- A source endpoint

- A target endpoint

- The list of tables that we want to capture.

- Any transformations we want to make on the data.

To get started, we need to create a task. Click on the "+ New Task"button at the top of the screen.

![ ](/static/qlik-images/image27.png)

Once you do, a window like this will pop up:

![ ](/static/qlik-images/image48.png)

Give this task a meaningful name like SAP to Aurora Postgres. For this task we will take the defaults:

- Name: "SAP to Aurora Postgres"

- Unidirectional

- Full Load: **enabled** *(Blue highlight is enabled; click to enable / disable.)*

- Apply Changes: **enabled***(Blue highlight is enabled; click to enable / disable.)*

- Store Changes: **disabled** *(Blue highlight is enabled; click to enable / disable.)*

Once you have everything set, press "OK" to create the task. When you have completed this step, you will see a window that looks like this:

![ ](/static/qlik-images/image49.png)

Qlik Cloud Data Integration is all about **ease of use**. The interface is point-and-click, drag-and-drop. To configure our task, we need to select
a source endpoint (SAP Application) and a target endpoint (Aurora). You can either drag the "SAP Application Source" endpoint from the box on
the left of the screen and drop it into the circle that says "Drop source endpoint here" or you can click on the arrow that appears just to the right of the endpoint when you highlight it.

![ ](/static/qlik-images/image50.png)

Repeat the same process for the Aurora Postgres Target endpoint. Your screen should now look like this:

![ ](/static/qlik-images/image51.png)

Our next step is to select the tables we want to qlik cloud data integration from SAP Application into Aurora Postgres. Click on the "Table Selection\..." button in the top center of your browser.

![ ](/static/qlik-images/image32.png)

and from there select the "ADEMO" Business Groups.

![ ](/static/qlik-images/image33.png)

Press the "Search" button. This will retrieve a list of all the Tables in the *ADEMO* group.

Press the "\>\>" button to move all of the tables from the **Results** list into the **Selected Tables** list. Note that we also had the option of simply wildcarding all tables, or selectively choosing tables from the **Results** list.

![ ](/static/qlik-images/image34.png)

That completes configuration of the task. We are now ready to save our task and run it. Press "Save" at the top left of the window and then
press "Run".

### Step 4 - Run Your Task

After you press "Run", Qlik Cloud Data Integration will automatically switch from **Designer** mode to **Monitor** mode. You will be able to watch the status of the full load as it occurs, and then switch to monitoring change data capture as well.

![ ](/static/qlik-images/image52.png)

When **Full Load** is complete, click on the "Completed" bar to display the tables. if there is DML activity running in the background. Click on
the "Change Processing" tab to see it in action.\
**Please note for SAP Lab we do not have DML Scheduled**

![ ](/static/qlik-images/image53.png)
If you would like to explore the data that we have delivered to Postgres, go to the following link:

**http://YOUR_SERVER_IP_ADDRESS:3000**

This link will open SQLPad in another window in your browser. Log in
with:

- User: "<admin@qlik.com>"

- Password: "Aws_immersion123"

From there, click on drop down bar in the navigation pane. **For SAP LAB Please follow directions from Instructor**

When you have seen enough, you can declare Victory! for this part of the Lab. Press "Stop" in the top left corner of the **Qlik Cloud Data Integration** console to
end the task. After pressing "Stop" and clicking "Yes" in the confirmation dialog, click on the "TASKS" tab at the top of the screen. This will return you to the main window.

![ ](/static/qlik-images/image54.png)

### Summary

Following concepts were covered in the lab:

- Defined access and authentication into a source and a target database

- Defined the source tables you want to create and keep in sync on the target

- Configured the SAP Application to Aurora Postgres task.

- Captured initial data from the source without while maintaining business continuity (DML activity was going on in the background to simulate users working on the source database)

- Automatically created the target tables.

- Loaded the target tables.

- Captured all new transactions which were happening while the initial load was running.

- Automatically began the process to apply net new data to the target once the target was loaded.

- Observed change data being recorded as it is sent to and applied at the target.

## Qlik Lab 3 : SAP to Amazon Redshift in Realtime

### Step 1 - SAP Source Configuration

> Please see Step above [here](#step-1---sap-source-configuration)

### Step 2 - Amazon Redshift Target Configuration

Next, we need to configure our Redshift target endpoint. The process is much the same as you saw with the SAP source but for Redshift, we need
to have S3 Bucket, and once again you will note that the configuration process is context sensitive as we move along.

As before, the first step in the configuration process is to tell Qlik Cloud Data Integration that we want to create a new endpoint. If you are back on the
main window, you will need to click on "Manage Endpoint Connections" button.

![ ](/static/qlik-images/image12.png)

and then press the "+ New Endpoint Connection" button.

![ ](/static/qlik-images/image22.png)
and you will see a window that resembles this:

![ ](/static/qlik-images/image14.png)

We will now create an Amazon Redshift Target endpoint:

- Replace the text **New Endpoint Connection 1** with something more descriptive like "Redshift Target",

- make sure the "Target" radio button is selected,

- and then select "Amazon Redshift" from the dropdown selection box.

![ ](/static/qlik-images/image55.png)

At this Point we need grab the end point for our Amazon Redshift Instance.

Go to your EC2 Console and Find Amazon Redshift under "Services."

![ ](/static/qlik-images/image56.png)

On your Dashboard you should see your Cluster already running.

![ ](/static/qlik-images/image57.png)

Navigate to the Cluster and you should see the properties of your cluster looking something like.

![ ](/static/qlik-images/image57.png)

Click on the button to copy the endpoint.

![ ](/static/qlik-images/image58.png)

**Once the endpoint is copied you should see that it has port number and database appended.**

**Manually remove the values and use endpoint as a reference to fill in the variables.**

![ ](/static/qlik-images/image59.png)
Fill in the blanks as indicated in the image above:

- Host: "YOUR REDSHIFT ENDPOINT"

- Port: "5439"

- User: "qlik123"

- Password: *please access AWS Secrets Manager for your Redshift password*

- Database: "testdrive"

Due to Design of Redshift Cluster you need to use S3 as intermediate staging area

### Step 2.1 Amazon S3 and IAM Configuration

Next, we need to configure our IAM Policy and Download Access and Secret Keys for Qlik Cloud Data Integration to stage the data to Amazon S3 prior to writing it Redshift.

AWS IAM Policies, Users, and Roles are way AWS Secures resources and gives the right amount of access.

For this process we will give our current user access to all S3 buckets but your Cloud admin can secure it so user/role only has access to a single bucket we need.

First grab the bucket name

![ ](/static/qlik-images/image60.png)

Go to AWS S3 and you should see a bucket name that and in "-qlikqlik cloud data integration"

![ ](/static/qlik-images/image61.png)
Click on the bucket and "Properties."

![ ](/static/qlik-images/image62.png)

Please get the name of the bucket and what AWS Region the bucket belongs in

- Please create a folder inside your bucket and name it "Aws_immersion_day"

- This will help during S3 setup.

Go back to Qlik Cloud Data Integration and Fill in following from End Point Configurations

- Bucket Name: " YOURBUCKETNAME"

- Region: "YOUR-REGION"

Now you will need to add an user with full s3 access. Go into IAM
section of AWS add an User Add a Role for that with S3Full Access.

**for this tutorial we will just log in user with full s3 access**

Go to IAM section on your AWS Console by clicking on services (top left) -\> IAM. If it does not show up, you can search for 'IAM' as well.

![ ](/static/qlik-images/image63.png)

At this point you will see IAM dashboard; click on "Users. "

![ ](/static/qlik-images/image64.png)

Click on and press "Add User"

![ ](/static/qlik-images/image65.png)

Input your Amazon S3 Username:

- **Username: "qlik-qlik cloud data integration"**

- **Select Programmatic access only.**

![ ](/static/qlik-images/image66.png)

Press Button "Next Permissions"

![ ](/static/qlik-images/image67.png)

Press Button "Next Permissions"

![ ](/static/qlik-images/image68.png)
Optional Add Tags and Press Button "Next Review"

![ ](/static/qlik-images/image69.png)

Review you Username and Press Button "Create User"

![ ](/static/qlik-images/image70.png)

**At this point your new user with Full Amazon S3 privileges are
created**

Copy Access Key and Secret Key to Qlik Cloud Data Integration Connection window (Click on Show on access key to view the key)

![ ](/static/qlik-images/image71.png)

Download your keys or copy the keys into Qlik Cloud Data Integration Connection Window.(Please Click on Show to see your secret key)

Please copy the keys to your Qlik Cloud Data Integration Connection Window

- Access Key: "YOUR ACCESS KEY"

- Your Secret Key: "YOUR SECRET KEY"

- At this point press **Browse...** button and
    select **Aws_immersion_day** folder.

![ ](/static/qlik-images/image72.png)

Press "Test" to test connection

![ ](/static/qlik-images/image73.png)

*Note if you run into issues with Qlik Cloud Data Integration complaining about S3 access please verify the qlik-qlik cloud data integration user has access to S3 buckets.*

![ ](/static/qlik-images/image74.png)

*Qlik Cloud Data Integration can write directly to S3 For more details about using Amazon S3 as a target, please review the section "Using a Amazon S3 as a Target" in Chapter 9 "Adding and Managing Target Endpoints" of the [Qlik Cloud Data Integration User Guide](<https://qlik-aws-sap.netlify.app/files/Qlik_Qlik> Cloud Data Integration_User_Guide.pdf)*

###

### Step 3 - Configure Your Task

Now that we have configured our SAP source and Redshift target endpoints, we need to tie them together in what we call a Qlik Cloud Data Integration **task**. In short, a task defines the following:

- A source endpoint

- A target endpoint

- The list of tables that we want to capture.

- Any transformations we want to make on the data.

To get started, we need to create a task. Click on the "+ New Task" button at the top of the screen.

![ ](/static/qlik-images/image27.png)

Once you do, a window like this will pop up:

![ ](/static/qlik-images/image48.png)

Give this task a meaningful name like SAP Application to Redshift. For this task we will take the defaults:

- Name: "SAP Application to Redshift"

- Replication Profile: "Unidirectional"

- Full Load: **enabled** *(Blue highlight is enabled; click to enable
    / disable.)*

- Apply Changes: **enabled** *(Blue highlight is enabled; click to
    enable / disable.)*

- Store Changes: **disabled** *(Blue highlight is enabled; click to
    enable / disable.)*

Once you have everything set, press "OK" to create the task. When you have completed this step, you will see a window that looks like this:

![ ](/static/qlik-images/image75.png)
Qlik Cloud Data Integration is all about **ease of use**. The interface is point-and-click, drag-and-drop. To configure our task, we need to select a source endpoint (SAP) and a target endpoint (Redshift). You can either drag the "SAP Application Source" endpoint from the box on the left of the screen and drop it into the circle that says "Drop source endpoint here", or you can click on the arrow that appears just to the right of the endpoint when you highlight it.

![ ](/static/qlik-images/image50.png)

![ ](/static/qlik-images/image76.png)

Repeat the same process for the Redshift Target endpoint. Your screen
should now look like this:

![ ](/static/qlik-images/image77.png)

Our next step is to select the tables we want to qlik cloud data integration from SAP Application into Aurora Postgres. Click on the "Table Selection" button in the top center of your browser.

![ ](/static/qlik-images/image32.png)
and from there select the "ADEMO" Business Groups.

![ ](/static/qlik-images/image33.png)

Press the "Search" button. This will retrieve a list of all the Tables
in the *ADEMO* group.

Press the "\>\>"button to move all the tables from the **Results** list into the **Selected Tables** list. Note that we also had the option of simply wildcarding all tables, or selectively choosing tables from the **Results** list.

![ ](/static/qlik-images/image34.png)

That completes configuration of the task. We are now ready to save our task and run it. Press "Save" at the top left of the window and then press "Run".

### Step 4 - Run Your Task

After you press "Run", Qlik Cloud Data Integration will automatically switch from **Designer** mode to **Monitor** mode. You will be able to watch the status of the full load as it occurs, and then switch to monitoring change data capture as well.

![ ](/static/qlik-images/image78.png)

When **Full Load** is complete, click on the "Completed" bar to display the tables. if there is DML activity running in the background. Click on the "Change Processing" tab to see it in action.\
**Please note for SAP Lab we do not have DML Scheduled**

![ ](/static/qlik-images/image79.png)

If you would like to explore the data that we have delivered to Redshift please go to SQLPad

- URL: **https://YOUR_SERVER_IP_ADDRESS:9000**

Connect to your Cluster by Creating your Connection

Press the Edit on Top Right at SQLPad

![ ](/static/qlik-images/image80.png)

![ ](/static/qlik-images/image81.png)

Press the Edit on Top Connections

- Connection name: "Redshift"

- Driver: "Redshift"

- Host: **REDSHIFT_CLUSTER_NAME**

- Port: "5439"

- Database: "testdrive"

- Database Username: "qlik123"

- Database Password: *please access you

When you have seen enough, you can declare Victory! for this part of the Lab. Press "Stop" in the top left corner of the **Qlik Cloud Data Integration** console to end the task. After pressing "Stop" and clicking "Yes" in the confirmation dialog, click on the "TASKS" tab at the top of the screen.This will return you to the main window.

### Summary

Following concepts were covered in the lab:

- Defined access and authentication into a source and a target database.
- Defined the source tables you want to create and keep in sync on the target.
- Configured the SAP Application to Redshift task.
- Captured initial data from the source without while maintaining business continuity (DML activity was going on in the background to simulate users working on the source database)
- Automatically created the target tables.
- Loaded the target tables.
- Captured all new transactions which were happening while the initial load was running.
- Automatically began the process to apply net new data to the target once the target was loaded
- Observed change data being recorded as it is sent to and applied at the target.

# Resources

### Thanks for taking the Qlik Cloud Data Integration Lab for a spin. Assuming you followed all the steps and completed the exercises, we are confident that you will have found the experience to be a good one and that our focus on ease of use was evident

### The product documentation and help can be found at

[Qlik Cloud Data Integration Online
Guide](<https://help.qlik.com/en-US/qlik> cloud data integration/November2020-SR1/Content/Qlik Cloud Data Integration/Main/Introduction/Home.htm) - Online Help Guide for Qlik Cloud Data Integration

[Qlik Cloud Data Integration Offline User
Guide](<https://qlik-aws-sap.netlify.app/files/Qlik_Qlik> Cloud Data Integration_User_Guide.pdf) -PDF Help Guide for Qlik Cloud Data Integration

[Qlik Community](https://community.qlik.com/) - Community page for Qlik Cloud Data Integration

### About the Sample Data

The sample data used in this tutorial comes from the [Sean Lahman Baseball Archive](http://www.seanlahman.com/baseball-archive/statistics)

Copyright 1996-2018 by Sean Lahman. It is licensed for use under a [Creative Commons Attribution-ShareAlike 3.0 Unported License](http://creativecommons.org/licenses/by-sa/3.0/)([legalcode](https://creativecommons.org/licenses/by-sa/3.0/legalcode).

# Videos

### Thanks for taking the Qlik Cloud Data Integration Lab for a spin. Here are some Video resource for the Labs as well other Video Assets produced by the Qlik Team

### The product documentation and help can be found at

- [Qlik Cloud Data Integration Explainer and Demo Video](https://youtu.be/3UBa5WgOfio)

- [Qlik Cloud Data Integration Real Time Data Ingestion](https://youtu.be/qU7tF7npJt0)

- [Qlik Cloud Data Integration Many to One](https://youtu.be/0mka2LNf7Sg)

- [Qlik Cloud Data Integration Installation on Linux](https://youtu.be/tMJhi2U2JLw)

# Contacts

## AWS Partner Team

- *Carter Johnson, Sr Partner Development Manager     - <cvjnston@amazon.com>*  
- *Sathisan Vannadil, Sr Partner Solution Architect     - <vannadil@amazon.com>*

## Qlik Partner Team

- *Boris Geller, Head of Strategic Tech BD - <boris.geller@qlik.com>*
- *Hugo Sheng, Sr Director, Partner Engineeing     - <hugo.sheng@qlik.com>*  
- *John Park, Principal Solution Architect - <john.park@qlik.com>*
- *Dalton Ruer, Sr. Solution Architect - <dalton.ruer@qlik.com>*
- *Matt Hayes, VP SAP Business - <matt.hayes@qlik.com>*
- *Tom Olivero, Senior Manager, SAP Data Architects - <tom.olivero@qlik.com>*
- *David Frerik, Evangelist and Technology Partnership - <david.frerik@qlik.com>*
- *Brad Songer, Regional Alliance Manager -<brad.songer@qlik.com>*

# Register for a free Qlik Cloud Data Integration POC

- For customers and prospect of AWS who are looking to do a POC Please register via this [link](https://www.qlik.com/us/try-or-buy/buy-now?campaignid=7013z000000j5hi)
![](/static/qlik-images/image82.png)

After you completed all the steps in the Quickstart, please return back to this workshop window.
