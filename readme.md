# Homework 7
### Lev Zelenin

## QR code image for my student github account homepage:
![Lev's QR code](res/QRCode_20250405115042.png)

## Image of the log:
(venv) levz@LevsLaptop:~/projects/homework7$ docker build -t qr_code .
[+] Building 14.5s (13/13) FINISHED                                                      docker:default
 => [internal] load build definition from Dockerfile                                               0.1s
 => => transferring dockerfile: 1.32kB                                                             0.0s
 => [internal] load metadata for docker.io/library/python:3.12-slim-bullseye                       1.2s
 => [auth] library/python:pull token for registry-1.docker.io                                      0.0s
 => [internal] load .dockerignore                                                                  0.1s
 => => transferring context: 80B                                                                   0.0s
 => [1/7] FROM docker.io/library/python:3.12-slim-bullseye@sha256:00ead89513b0a58e3805e7e88fc522a  5.1s
 => => resolve docker.io/library/python:3.12-slim-bullseye@sha256:00ead89513b0a58e3805e7e88fc522a  0.1s
 => => sha256:0bb7bb6ad0b375cbbc791cf5d6131c6c9e0bda49b8f917c69889f5f04050b60d 248B / 248B         0.2s
 => => sha256:fe62b43e26b7767c5d690f792a2ffc6d7a1596ae7623b4ae82d3eb8231319cb8 12.93MB / 12.93MB   1.1s
 => => sha256:a66e2dcd5f01c465b021864c90740190fa24ef3090f03cd9a87a88773762212 871.25kB / 871.25kB  0.6s
 => => sha256:55147cbf65d4d152c070165835355b8ea7a090d48d81ba52cbeb9bbe8d629fc0 30.25MB / 30.25MB   3.0s
 => => extracting sha256:55147cbf65d4d152c070165835355b8ea7a090d48d81ba52cbeb9bbe8d629fc0          1.1s
 => => extracting sha256:a66e2dcd5f01c465b021864c90740190fa24ef3090f03cd9a87a887737622124          0.1s
 => => extracting sha256:fe62b43e26b7767c5d690f792a2ffc6d7a1596ae7623b4ae82d3eb8231319cb8          0.6s
 => => extracting sha256:0bb7bb6ad0b375cbbc791cf5d6131c6c9e0bda49b8f917c69889f5f04050b60d          0.0s
 => [internal] load build context                                                                  0.8s
 => => transferring context: 28.40MB                                                               0.7s
 => [2/7] WORKDIR /app                                                                             0.2s
 => [3/7] RUN useradd -m myuser                                                                    0.5s
 => [4/7] COPY requirements.txt ./                                                                 0.1s
 => [5/7] RUN pip install --no-cache-dir -r requirements.txt                                       3.8s
 => [6/7] RUN mkdir logs qr_codes && chown myuser:myuser logs qr_codes                             0.4s
 => [7/7] COPY --chown=myuser:myuser . .                                                           0.4s
 => exporting to image                                                                             2.5s
 => => exporting layers                                                                            1.4s
 => => exporting manifest sha256:665548c50cc727b7b02a09ef5c5386cda488144469cfaaf8a6056e091c2f432c  0.0s
 => => exporting config sha256:e26223afc8d11c8fb9d5f78fadb0c74f0205746db839df88189db3648ced969d    0.0s
 => => exporting attestation manifest sha256:278e562c4406415bdc79978201cb571fb4448c524acd7a29828d  0.0s
 => => exporting manifest list sha256:131e09cf0791abd7832cd3341a807b646a7b1ae25362ef4a5dc95d97652  0.0s
 => => naming to docker.io/library/qr_code:latest                                                  0.0s
 => => unpacking to docker.io/library/qr_code:latest                                               1.0s
(venv) levz@LevsLaptop:~/projects/homework7$ docker run -v $(pwd):/app qr_code
2025-04-05 16:22:28,811 - INFO - QR code successfully saved to /app/qr_codes/QRCode_20250405162228.png
(venv) levz@LevsLaptop:~/projects/homework7$ docker run -v $(pwd):/app qr_code --url=https://github.com/SOME_OTHER_GITHUB
2025-04-05 16:23:21,094 - INFO - QR code successfully saved to /app/qr_codes/QRCode_20250405162321.png
