# How to run product page

## Prerequisite

* Python 3.8

```bash
pip install -r requirements.txt
python productpage.py 9080
```
## How to run with Docker

```bash
# Build Docker Image for this service
docker build . -t productpage

# Run this service on port 8083
docker run -d -p 8083:8083 --name productpage --link reviews:reviews --link ratings:ratings --link reviews:reviews --link details:details \
-e 'DETAILS_HOSTNAME=http://details:8081' -e 'RATINGS_HOSTNAME=http://ratings:8080' -e 'REVIEWS_HOSTNAME=http://reviews:9080' -e 'FLOOD_FACTOR=1' productpage

```