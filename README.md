kubectl apply -f app-secrets.yaml 

kubectl create secret docker-registry ghcr-secret `
  --docker-server=ghcr.io `
  --docker-username=<> `
  --docker-password=<your-personal-access-token> `
  --docker-email=<> `
  -n default

kubectl create job --from=cronjob/my-playwright-app manual-playwright-job -n helm-test
