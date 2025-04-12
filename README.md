# T212 to Digrin CLI
n8n tool for fetching T212 reports via API call and transforming them to be used in Digrin portfolio tracker. Stores the reports in AWS S3.

1. ~~Get input year_month from cli~~
2. Get first day of current year_month selected in ad1 and first day of next year_month
3. POST request on T212 API report creation endpoint with payload containing dates from ad2.
4. GET request on T212 API list reports endpoint, loop until the created report from ad3 is finished
5. Download raw T212 csv report from ad3.
6. Store downloaded T212 csv from ad5 in AWS S3.
7. Decode, transform into Digrin, encode.
8. Store Digrin csv from ad6 locally for upload
9. Store Digrin csv from ad6 in AWS S3.

## Setup

* Setup in credentials as Header Auth with:
    * name=Authorization
    * value=T212_API_KEY

* Setup AWS credentials