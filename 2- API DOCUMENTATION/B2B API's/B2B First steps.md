# B2B Company Documentation: Using Our APIs

Welcome to the documentation for B2B companies looking to use our APIs. Below are the detailed steps to set up and use our APIs effectively.

## Table of Contents
1. [Create a Company on Cloudsolute](#create-a-company-on-cloudsolute)
2. [Obtain OAuth Key from Google Cloud Console](#obtain-oauth-key-from-google-cloud-console)
3. [Create a Google Login Button](#create-a-google-login-button)
4. [Use Login and Verify APIs](#use-login-and-verify-apis)
5. [Use the Token to Make API Calls](#use-the-token-to-make-api-calls)

## Create a Company on Cloudsolute

1. **Go to Company Creation Page**:
   - Visit [b2b.cloudsolute.net/crear-company](https://b2b.cloudsolute.net/crear-company)

2. **Log In**:
   - Log in with your user account.

3. **Create Company**:
   - Fill out the form with your company details.
   - Submit the form to create the company.

4. **Wait for Approval**:
   - Wait for your company to be approved by our team. You will receive a notification once the process is complete.

## Obtain OAuth Key from Google Cloud Console

1. **Access Google Cloud Console**:
   - Go to [Google Cloud Console](https://console.cloud.google.com/).

2. **Log In**:
   - Log in with your Google account.

3. **Create a New Project**:
   - Click on the project dropdown menu at the top of the page.
   - Click on "New Project".
   - Name your project and click "Create".

4. **Enable Necessary APIs**:
   - In the navigation menu, select "APIs & Services" > "Library".
   - Search for and enable the APIs you need, such as "Google Drive API" or "Google Sheets API".

5. **Configure OAuth Consent Screen**:
   - In the navigation menu, select "APIs & Services" > "OAuth consent screen".
   - Configure the consent screen with the required information.

6. **Create OAuth Credentials**:
   - In the navigation menu, select "APIs & Services" > "Credentials".
   - Click on "Create Credentials" and select "OAuth Client ID".
   - Configure the application type and add authorized redirect URIs.
   - Download the JSON file with the credentials.

## Create a Google Login Button

1. **Implement the Login Button**:
   - Use the obtained OAuth credentials to implement a Google login button on your webpage.
   - Ensure the button redirects users to the Google authentication flow.

## Use Login and Verify APIs

### Login API

**Function to handle first-time user login**:
- **Endpoint**: `/api/user-login`
- **Method**: POST
- **Request Body**:
  ```json
  {
      "token": "eyJhbGH....hU"
  }```

#### Response 200:
```
{
    "message": "Data updated successfully",
    "result": [
        {
            "data": {
                "email": "user@yourcompany.com,
                "token": "ey...."
            }
        }
    ],
    "status": 200
}
```

#### Response 403:
```
{
    "message": "Invalid or expired token",
    "result": [],
    "status": 403
}
```

### Verify API

**Function to verify the token**:
- **Endpoint**: `/api/verify-token`
- **Method**: POST
- **Request Body**:
  ```json
  {
      "token": "eyJhbGH....hU"
  }```

#### Response 200:

```
{
    "message": "Token is valid current time 2025-02-10 09:53:23.841030+00:00",
    "result": [
        {
            "data": {
                "advanced_search_left": 10,
                "current_time": "Mon, 10 Feb 2025 09:53:23 GMT",
                "db_user_id": "user@yourcompany.com",
                "db_user_name": "YourName",
                "db_user_plan_id": 1,
                "db_user_token_exp": "Mon, 17 Feb 2025 01:52:36 GMT",
                "upload_thirdparty_videos_left": 5,
                "user_plan_id": 1
            }
        }
    ],
    "status": 200
}
```

#### Response 400:
```
{
    "message": "Empty values for parameters api function: handler_verify_token token",
    "result": [],
    "status": 400
}
```

#### Response 401:
```
{
    "message": "Invalid or expired user_token",
    "result": [],
    "status": 401
}
```

**Note**: With the Google token, you must first call `/api/user-login` and then `/api/verify-token` so that Cloudsolute can validate and modify the Google token, adding more data.

## Use the Token to Make API Calls

Once you have obtained the final token from Cloudsolute, you can use it to make various API calls. Below are some example endpoints:

### Apis for searching videos

- **Search String in All Videos**:

{{HOST}}/api/string-in-all-b2b

[!ref](/2-%20API%20DOCUMENTATION/B2B%20API's/B2B%20API%20DOCS/string-in-all-b2b.md)

- **Search String in All Videos with Pagination**:

{{HOST}}/api/string-in-all-paginate-framenumbers-b2b

[!ref](/2-%20API%20DOCUMENTATION/B2B%20API's/B2B%20API%20DOCS/string-in-all-paginate-framenumbers-b2b.md)

### APis for video playback

- **Get HLS Playlist**:

{{HOST}}/api/um-get-hls-playlist/vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0


[!ref](/2-%20API%20DOCUMENTATION/B2B%20API's/B2B%20API%20DOCS/um-get-hls-playlist.md)

- **Get HLS Segment**:

{{HOST}}/api/um-get-hls-segment/vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0/10

[!ref](/2-%20API%20DOCUMENTATION/B2B%20API's/B2B%20API%20DOCS/um-get-hls-segment.md)


### APis for video management

- **Upload Video**:

{{HOST}}/api/um-upload-video

[!ref](/2-%20API%20DOCUMENTATION/B2B%20API's/B2B%20API%20DOCS/um-upload-video.md)

- **Delete Video**:

{{HOST}}/api/um-delete-video

[!ref](/2-%20API%20DOCUMENTATION/B2B%20API's/B2B%20API%20DOCS/um-delete-video.md)

### APis for company management

- **Get All Videos from Company**:

{{HOST}}/api/get-all-videos-from-company

[!ref](/2-%20API%20DOCUMENTATION/B2B%20API's/B2B%20API%20DOCS/get-all-videos-from-company.md)

<!-- For more details on each endpoint, refer to the [complete API documentation](#). -->
---

Thank you for using our APIs! If you have any questions or need further information, please feel free to contact us.`
