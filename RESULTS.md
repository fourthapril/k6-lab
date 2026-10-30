# K6 lab results

## Part 0

- Step 0.1: `http_req_duration` p(95) was 267.40 ms (one request).
- Step 0.2: 80 requests at 3.837 requests/s, with p(95) of 268.08 ms. The rate stays below 5 requests/s because each of the 5 VUs sleeps for one second after its request, and the HTTP request itself also takes time.
- Step 0.3: 20 iterations completed exactly, shared by 5 VUs; the run ended when the twentieth iteration finished.
- Step 0.4: The authenticated pizza API run passed all three checks: status 200, a pizza name was present, and every ingredient was vegetarian.
- Step 0.5: The request without an Authorization token was correctly refused with status 401.
- Step 0.6: The normal run exited with code 0 and p(95) of 364.12 ms. The stricter `P95=300` run exited with code 99 because its measured p(95) was 372.21 ms.
- Step 0.7: The requirement run passed `http_req_failed < 1%`, `p(95) < 1000 ms`, `p(99) < 1500 ms`, and `checks > 99%`. Measured p(95) was 384.63 ms and p(99) was 397.57 ms; exit code was 0. After changing the p(95) limit from 1000 ms to 300 ms, p(95) was 375.41 ms and the exit code was 99.
- Step 0.8: The exploratory API response listed `Pepperoni` and `Knife` with capital letters. The original lowercase request therefore did not match QuickPizza's case-sensitive catalog. The buggy run had 187/225 checks pass (83.11%), including 15 pepperoni failures and 23 knife failures. The fixed script sends `Pepperoni` and `Knife`; its run had 225/225 checks pass (100%).
