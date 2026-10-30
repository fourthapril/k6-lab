# K6 lab results

## Part 0

- Step 0.1: `http_req_duration` p(95) was 267.40 ms (one request).
- Step 0.2: 80 requests at 3.837 requests/s, with p(95) of 268.08 ms. The rate stays below 5 requests/s because each of the 5 VUs sleeps for one second after its request, and the HTTP request itself also takes time.
- Step 0.3: 20 iterations completed exactly, shared by 5 VUs; the run ended when the twentieth iteration finished.
