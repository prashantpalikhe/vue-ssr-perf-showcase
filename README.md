# Vue SSR perf issue showcase

## Steps to reproduce

1. Download K6
   ```sh
   brew install k6
   ```
2. Install deps 
    ```sh
    pnpm install
    ```
3. Build and serve the app
    ```sh
    pnpm build && pnpm serve
    ```
4. Run K6 load test in a separate terminal tab 
    ```sh
    k6 run load-test.js
    ```
5. Curl the server periodically in a separate terminal tab 
    ```sh
    curl -o /dev/null -s -w "Total time: %{time_total}s\n" http://localhost:6173/test/
    ```

## What happens

As K6 increases the number of concurrent users, the server starts to slow down dramatically.

When you curl the server, on the server log, you will see the time it took to render the app.

As the concurrent users increase, this app render time stays low. But the server response increases dramatically.

> tl;dr: as the concurrent users increase, the app stays fast, but the server response time increases.

## What should happen

The server response time should stay low, even as the concurrent users increase.
