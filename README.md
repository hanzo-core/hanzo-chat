# hanzo-chat
Hanzo chat app.

## Run Locally
In general, Node.js projects require:

1. Install the [Google Cloud SDK](https://cloud.google.com/sdk/), including the
[gcloud tool](https://cloud.google.com/sdk/gcloud/), and
[gcloud app component](https://cloud.google.com/sdk/gcloud-app).
1. Setup the gcloud tool. This provides authentication to Google Cloud APIs and
services.

        gcloud init

1. Acquire local credentials for autheticating with Google Cloud Platform APIs:

        gcloud beta auth application-default login

2. Install depedencies using `npm` or `yarn`:

        npm install

    or

        yarn install

3. Run the sample with `npm` or `yarn`:

        npm start

    or

        yarn start

1. Visit the application at [http://localhost:8080](http://localhost:8080).

## Deploying

1. Use the [Google Developers Console](https://console.developer.google.com) to
create a project/app id. (App id and project id are identical.)

2. Setup the gcloud tool, if you haven't already.

        gcloud init

3. Use gcloud to deploy your app.

        gcloud app deploy

    Note: If there is a `yarn.lock` file then `yarn install` will be used during
    deployment. Delete the `yarn.lock` file to fall back to `npm install`.

4. Awesome! Your application is now live at `https://YOUR_PROJECT_ID.appspot.com`.

## Websocket Setup
You will need to create a new firewall rule to allow traffic on port 65080. This
port will be used for websocket connections. You can do this with the [Google
Cloud SDK](https://cloud.google.com/sdk) with the following command:

    gcloud compute firewall-rules create default-allow-websockets \
      --allow tcp:65080 \
      --target-tags websocket \
      --description "Allow websocket traffic on port 65080"
