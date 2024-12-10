# || [mini lab : Cloud Storage : 3](https://www.cloudskillsboost.google/games/5702/labs/36442) ||

## # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

---
## ⚠️ **Disclaimer:**
#### This script and guide are provided for educational purposes to help you understand the lab process. Please ensure you understand the steps before using any scripts. Before using the script, I encourage you to open and review it to understand each step.The goal is to help you learn how to complete the labs effectively while following Qwiklabs' terms of service and YouTube's community guidelines.
---

## Copy and run :

```
BUCKET=""
REGION=""
BUCKET_NAME=""
```

```
gcloud storage buckets create gs://$BUCKET_NAME --location=$REGION
gcloud storage cp --recursive gs://$BUCKET/* gs://$BUCKET_NAME
gcloud storage buckets update gs://$BUCKET_NAME --no-uniform-bucket-level-access
gcloud storage buckets add-iam-policy-binding gs://$BUCKET_NAME --member=allUsers --role=roles/storage.admin
gcloud storage buckets update gs://$BUCKET_NAME --web-main-page-suffix=index.html --web-error-page=error.html
gcloud compute addresses create example-ip --network-tier=PREMIUM --ip-version=IPV4 --global
gcloud compute addresses describe example-ip --format="get(address)" --global
gcloud compute backend-buckets create cp-backend-bucket --gcs-bucket-name=$BUCKET_NAME
gcloud compute url-maps create cp-load-balancer --default-backend-bucket=cp-backend-bucket
gcloud compute target-http-proxies create cp-tp --url-map=cp-load-balancer
gcloud compute forwarding-rules create cp-ff --load-balancing-scheme=EXTERNAL --network-tier=PREMIUM --target-http-proxy=cp-tp --ports=80 --address=example-ip --global
sleep 30
IP_ADDRESS=$(gcloud compute addresses describe example-ip --format="get(address)" --global)
echo "This is IP address: $IP_ADDRESS"
curl http://$IP_ADDRESS
```
---

## Congratulations ..!!🎉  You completed the lab shortly..😃💯

## *Well done..!* 👏

## Thank you for visiting.... :) 🗯️

## [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)

## Join to our community [Digital Dominators](https://chat.whatsapp.com/J0o1beFGCHfJ8ZHGKjcqkd)
