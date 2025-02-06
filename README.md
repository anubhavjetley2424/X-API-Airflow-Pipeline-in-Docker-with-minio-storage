Build an Apache Airflow to extract X Api data based on recent tweets from an account and store them in a minio storage bucket.

![architecture](https://github.com/user-attachments/assets/a676b5c9-2417-424a-9edc-209aba848d11)

# To apply:
1. Create your own .env file storing API keys neccessary
    cp sample.env .env
2. Add your X Bearer Token
    TWITTER_BEARER_TOKEN="bearer_token_example"
3. Start Docker instance
   docker compose up -d
4. Locate Pipeline task actions and success in:
   http://localhost:8080
5. Get data passed to minio bucket in:
   http://localhost:9090
   
