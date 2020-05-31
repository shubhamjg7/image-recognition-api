# Image recognition api

Recognize object in image by providing image url.

## Install

Prerequisite: Docker

```
sudo docker-compose build
```

## Usage

```
sudo docker-compose up
```

## Api

### Register users

Register a new user.

#### Request

POST /register/

```curl -i -H 'Accept: application/json' -d 'username=Xyz&password=abc' http://localhost:5000/register```

#### Response

```{"status": 200,"msg": "You successfully signed up for the API"}```

### Submit image classification request

Submit url of image to recognize object in the image.

#### Request

POST /classify/

```curl -i -H 'Accept: application/json' -d 'username=Xyz&password=abc&url=image.com/input.jpeg' http://localhost:5000/classify```

#### Response

```{"tiger	": 0.946,"zebra": 0.664}```

### Alot more tokens to user

Alot more tokens to specified username so that user can classify more images. Admin password is needed.

#### Request

POST /refill/

```curl -i -H 'Accept: application/json' -d 'username=Xyz&admin_pw=password' http://localhost:5000/refill```

#### Response

```{"status":200,"msg": "Refilled successfully"}```