# Echo Service for fanout ingress with Kong

### Step 1. Install Kong if not exist

kubectl apply -f ./kong.yaml

### Step 2. Install echo service helm chart with hostname

helm upgrade echo-svc-kong-ingress helm --install \
--atomic --debug --timeout 2m0s \
--set app.hostName=${your-hostname-to-serve-echo-service}

** NOTE: substitute ${your-hostname-to-serve-echo-service} with real hostname
E.g. echo.mydomain.com

### Step 3. Access the echo service endpoints

http://${your-hostname-to-serve-echo-service}/boo-7070

http://${your-hostname-to-serve-echo-service}/foo-8080

http://${your-hostname-to-serve-echo-service}/

** NOTE: substitutes ${your-hostname-to-serve-echo-service} with real hostname
E.g. echo.mydomain.com

The output should look like sample-output.txt
