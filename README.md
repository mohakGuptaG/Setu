# Setu - Cloud-Backed File Sharing Platform

Setu is a high-speed file-transfer and relay platform designed to move large payloads efficiently. It leverages AWS S3 as an ephemeral transit pipeline, supporting both anonymous guest uploads and authenticated dashboard sharing. 

## Architecture & Data Flow
**Upload Pathway**: Client -> Express Server -> AWS S3 Transit Bucket -> MongoDB Metadata Indexing.

## REST API Reference

### File Dispatch & Download
- `POST /api/files/upload`: Dispatch a file payload.
- `GET /api/files/download/:id`: Download a file.
- `GET /api/files/info/:id`: Retrieve file metadata.

### User Auth
- `POST /api/users/register`: Authenticate a new user.
- `POST /api/users/login`: Authenticate an existing user.
- `GET /api/users/profile`: Retrieve user profile.

## Local Setup & Environment Variables

Create a `.env` file in the `server` directory with the following structure:

```env
MONGODB_URL=your_mongodb_uri
PORT=6600
SERVER_URL=http://localhost:6600/api/files
CLIENT_URL=http://localhost:5173
NODE_ENV=development

JWT_SECRET=your_secret_jwt_key

AWS_ACCESS_KEY_ID=your_aws_access_key
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
AWS_REGION=your_aws_region
AWS_BUCKET_NAME=your_bucket_name

MAIL_USER=your_email@gmail.com
MAIL_PASS=your_email_password

BASE_URL=http://localhost:6600
```

1. Install dependencies in `/client` (`npm install`).
2. Install dependencies in `/server` (`npm install`).
3. Run dev server in `/server` (`npm start`).
4. Run dev client in `/client` (`npm run dev`).

