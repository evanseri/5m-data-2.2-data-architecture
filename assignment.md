# Assignment

## Brief

Write the Python codes for the following questions.

## Instructions

Paste the answer as Python in the answer code section below each question.

### Question 1

Question: How would you create a new hash in Redis to store information about a person, with `john_doe` as the key and include the name (`John Doe`), age (`35`), and email address (`john@email.com`)?

```python
import redis

r = redis.Redis(
  host='redis-10908.c252.ap-southeast-1-1.ec2.cloud.redislabs.com',
  port=10908,
  password='EgIvxgDuiuk2Sh5VnJzUGXDMtLrtK5Hk')
```

Answer:

```python
key = 'john_doe'
fields = {
    'name': 'John Doe',
    'age': 35,
    'email': 'john@email.com'
}

# Add the hash to Redis
r.hset(key, mapping=fields)

print(f'Hash {key} created with fields: {fields}')
```

### Question 2

Question: Write Python code to list the first 10 objects (blob name) in the "gcp-public-data-landsat" bucket, along with their sizes.

```python
from google.cloud import storage

client = storage.Client()
bucket = client.get_bucket("gcp-public-data-landsat")
```

Answer:

```python
from google.cloud import storage

# Initialize the client
client = storage.Client()

# Reference the bucket
bucket = client.get_bucket("gcp-public-data-landsat")

# Get blobs in the bucket and list the first 10 with their sizes
blobs = bucket.list_blobs()

# Initialize a counter to keep track of the first 10 blobs
count = 0
max_count = 10

print("First 10 objects in the bucket along with their sizes:")
for blob in blobs:
    print(f"Blob Name: {blob.name}, Size: {blob.size} bytes")
    count += 1
    if count >= max_count:
        break
```

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
