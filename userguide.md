# Overview
An exercise created for attendees of the Autodesk Forge Workshop by BIMLauncher CEO John Egan (@bigdoods).

The exercise is designed to get Forge newcomers up and running fast. Just follow the steps below.

## Summary

Access Dublin Docklands BIM model in Forge viewer (and Query it!)
1. Create a bucket
2. Upload a design file
3. Convert design file to SVF
4. Create basic webpage with model viewer
5. Query file metadata on Server and Browser


## Getting started

* Please load and refer to the Postman collection for this exercise.
* Notes/Comments on an instruction in this repo follow "//"
* Documentation for each Postman request to Forge endpoint is placed in the request description

## Prerequisites
1. Create a developers account at https://forge.autodesk.com/
2. Download Github Repo to local filesystem from https://github.com/bimlauncher/3dDataHack-forge-training
3. Ensure you have Postman installed https://www.getpostman.com/downloads

## Step-by-step guide
### Step 1. Setup Postman
1. Postman import postman/collection.json // Import at top-left
2. Postman import postman/environment // Settings cog at top-right

### Step 2. Setup App on Forge
1. Login https://forge.autodesk.com
2. Click button to Create App. Set callback url: http://localhost:8000/callback
3. Set ClientId and ClientSecret in Postman Environment

### Step 3. Authenticate App with Forge
1. Navigate to Authenticate tab
2. Click (Send)
3. Set postman environment variable by highlighting access_token value in response, then right click and hover to Forge Training Environment, then select authToken.
4. (Send)

### Step 4. POST Bucket Create
1. Navigate to bucket create tab
2. Update bucketKey environment variable with the name of the bucket to create
3. (Send)

### Step 5. Upload object to bucket
1. Navigate to upload object to bucket tab
2. Choose file to upload from filesystem (I have included Dublin _docklands.zip_ model as a sample).
3. Update isZipped environment variable to true/false depending on if uploaded object is a zip file.
4. Update objectName variable. // This is the name used to reference this object in later steps and does not have to match filename you are uploading. Include file extension.
5. (Send)

### Step 6 - Start translation job
1. Navigate to start translation job tab
2. Encode the objectId value from the response from step 5 i.e urn:adsk.objects:os.object:bimlauncher.projects/fbx.zip. Use https://www.freeformatter.com/base64-encoder.html (RFC 4648). Encoded URN should look like: dXJuOmFkc2sub2JqZWN0czpvcy5vYmplY3Q6YmltbGF1bmNoZXIucHJvamVjdHMvZmJ4LnppcA== (The urn will end in "=" "==" or an ascii character)
3. Update sourceURN environment variable with value from previous step
4. Update the rootFileName environment variable with the name (and extension) of the file to be translated. For the included sample file this value should be _sourcemodel.fbx_ 
6. Update the destFormat environment variable with the value of the format that you want your source file to be translated to.
7. (Send)

### Step 7 - Verify job is complete
1. Navigate to get job status tab
2. (Send)
3. Repeat until status: success

### Step 8 - Load model in viewer
1. Open viewer > index.html in your favourite text editor
2. Update access_token and sourceURN values on lines 35,37
3. Open index.html in webGl enabled browser to view model

### Step 9 - Try out viewer customisation
1. Open chrome dev tools > Console
2. Get started with viewer/viewer-prompts.md

### Step 10 - Create your own request 
1. Review documentation for an endpoint you want to try // See additional Postman requests to make queries on 3D data not used (yet) in this exercise
2. Update Http request method, URL and required header/ body key:values in a new request.
3. (Send) and repeat :)








