### Before you install the gcloud CLI, make sure that your operating system meets the following requirements:

```
apt update
apt install -y apt-transport-https ca-certificates gnupg curl
```

### Installation

Import the Google Cloud public key:

```
curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo gpg --dearmor -o /usr/share/keyrings/cloud.google.gpg
```

Add the gcloud CLI distribution URI as a package source:

```
echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
```

Update and install the gcloud CLI:

```
apt update && apt install -y google-cloud-cli
```

Run gcloud init to get started:

```
gcloud init
```