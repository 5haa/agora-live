# Agora Token Server

A simple Python server for generating Agora tokens for live streaming.

## Setup

1. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

2. Set environment variables:
   ```
   export AGORA_APP_ID=your_app_id
   export AGORA_APP_CERTIFICATE=your_app_certificate
   ```

   On Windows:
   ```
   set AGORA_APP_ID=your_app_id
   set AGORA_APP_CERTIFICATE=your_app_certificate
   ```

3. Run the server:
   ```
   python app.py
   ```

## Deployment to Heroku

1. Install the Heroku CLI
2. Login to Heroku: `heroku login`
3. Create a Heroku app: `heroku create agora-token-server`
4. Set environment variables:
   ```
   heroku config:set AGORA_APP_ID=your_app_id
   heroku config:set AGORA_APP_CERTIFICATE=your_app_certificate
   ```
5. Deploy: `git push heroku main`

## API Usage

### Generate Token

**Endpoint:** `POST /generate-token`

**Request Body:**
```json
{
  "channelName": "your_channel_name",
  "uid": 0,
  "role": 1,
  "expirationTimeInSeconds": 3600
}
```

**Response:**
```json
{
  "token": "generated_token_string"
}
```

## Security Considerations

- Keep your Agora App Certificate secure
- Use HTTPS in production
- Consider adding authentication to the token server
