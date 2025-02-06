# Build an Apache Airflow to extract X Api data based on recent tweets from an account and store them in a minio storage bucket.

![architecture](https://github.com/user-attachments/assets/a676b5c9-2417-424a-9edc-209aba848d11)
# Methodology:
The traditional library 'tweepy' does not seem to work in Docker, hence we are using requests and a dynamic url retrieving the 50 latest tweets from that X account.
### Dynamic URL:
 url = f"{BASE_URL}?query=from:{USERNAME}&tweet.fields={','.join(FIELDS)}&expansions=author_id&max_results=50"
 <br></br>
 ## Note: you can remove from: to generate the 50 latest tweets based on that query topic.
 <br></br>
 To remove retweets, use : url = f"{BASE_URL}?query=from:{USERNAME} -is:retweet&tweet.fields={','.join(FIELDS)}&expansions=author_id&max_results=50"
 
# To apply:
1. Create your own .env file storing API keys neccessary
       - cp sample.env .env
2. Add your X Bearer Token
      - TWITTER_BEARER_TOKEN="bearer_token_example"
3. Unzip dag.zip file
      -  !unzip dags.zip
4. Start Docker instance
     -  docker compose up -d
5. Locate Pipeline task actions and success in:
    -  http://localhost:8080
6. Get data passed to minio bucket in:
     - http://localhost:9090
   
