# FS Postman

Just getting started with [FullStory REST APIs](https://developer.fullstory.com/introduction)? Or want something more convenient than cURL?  Use the FullStory [Postman](https://www.getpostman.com) collection.

## Installation

1. Download [Postman](https://www.getpostman.com/downloads/).
2. In Postman, click the **Import** button and then the **Import From Link** tab.
3. Enter the URL `https://raw.githubusercontent.com/van-fs/fs-postman/master/FullStory.postman_collection.json` in the textbox.
4. Click the **Import** button.

## Configuration

The collection uses Postman environment variables to make API requests more convenient. Let's set the most important variable, the `API_KEY`.

1. Obtain your API Key from FullStory per [documentation](https://help.fullstory.com/hc/en-us/articles/360020624834-Where-can-I-find-my-API-key-). Copy this to your clipboard.
2. In Postman, click the **Manage Environments** button on the far right. (It looks like a cog.)
3. Click the **Add** button to add a new environment and provide an **Environment Name**.
4. Create a **Variable** named `API_KEY`. Set the **Initial Value** to be your API Key you copied from step 1.

As needed, add other environment variables such as `USER_ID` or `USER_EMAIL`. You'll see these variables used in request URLs, for example `{{USER_EMAIL}}`. If the variable is red in color, it is not yet set.

Some environment variables like `EXPORT_ID` or `OPERATION_ID` are automatically assigned for convenience. You can update any environment variable, for example `START`, by editing the **Current Value** in environment variables.

## Sample Usage

To obtain data exports, perform the following.

1. Select the **List Data Exports** request from the **Export** folder in the collection.
2. Click the **Send** button. (By default, this will look for data exports created in the last 36 hours. You can change this by setting the `START` environment variable.)
3. Click the **Get Data Export** request - also in the **Export** folder.
4. Click the **Send** button to view the export as JSON. Alternatively, click the **Send** button's dropdown and **Send and Download** to save the export.
5. Return to the **List Data Exports** request and re-**Send**. You'll notice that the list is one less. This is because everytime the request is sent, the next bundle is used as the starting point.
6. Re-issue the  **Get Data Export** and **List Data Exports** until all bundles have been collected.

## Next Steps

Use the [Tests](https://learning.getpostman.com/docs/postman/scripts/test_scripts/) and [Pre-request Script](https://learning.getpostman.com/docs/postman/scripts/pre_request_scripts/) feature to build your own quick and easy FullStory app.