Cloud SQL & Google App Engine

This sample application demonstrates how to use Cloud SQL with Google App Engine.

Setup

Before running this sample:

Prerequisites

Install composer
Install dependencies by running:
composer install
Setup

Before you can run or deploy the sample, you will need to do the following:

Create a First Generation Cloud SQL instance. You can do this from the Cloud Console or via the Cloud SDK. To create it via the SDK use the following command:

$ gcloud sql instances create YOUR_INSTANCE_NAME
Set the root password on your Cloud SQL instance:

$ gcloud sql instances set-root-password YOUR_INSTANCE_NAME --password YOUR_INSTANCE_ROOT_PASSWORD
Update the connection string in app.yaml with your configuration values. These values are used when the application is deployed.

Run locally

To run locally, you can either run your own MySQL server locally and set the connection string in app.yaml, or you can connect to your CloudSQL instance externally.

cd php-docs-samples/appengine/standard/cloudsql

# set local mysql connection parameters
export MYSQL_DSN="mysql:host=127.0.0.1;port=3306;dbname=guestbook"
export MYSQL_USERNAME=root
export MYSQL_PASSWORD=

php -S localhost:8080
be sure the MYSQL_ environment variables are appropriate for your mysql instance
Now you can view the app running at http://localhost:8080 in your browser.

Deploy to App Engine

Prerequisites

Install the Google Cloud SDK.
Deploy with gcloud

gcloud config set project YOUR_PROJECT_ID
gcloud app deploy
gcloud app browse
The last command will open https://{YOUR_PROJECT_ID}.appspot.com/ in your browser.

Create the MySQL Tables

Once your application is running, browse to /create_table to create the required tables for this example.
