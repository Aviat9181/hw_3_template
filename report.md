[+] up 4/4
 ✔ Image docker-app:8b         Built                                                                                                     1.0s
 ✔ Network docker-hw_default   Created                                                                                                   0.0s
 ✔ Container docker-hw-redis-1 Healthy                                                                                                   5.2s
 ✔ Container docker-hw-app-1   Started                                                                                                   5.3s
⚡➜ hw_3_template (U 8b) curl -fsS http://127.0.0.1:8080/
{"greeting": "Hello, Docker!", "count": 0, "hostname": "9666f6e984c6", "storage": "redis"}%                                                  ⚡➜ hw_3_template (U 8b) curl -fsS http://127.0.0.1:8080/increment
curl: (22) The requested URL returned error: 404
⚡➜ hw_3_template (U 8b) curl -fsS -X POST http://127.0.0.1:8080/increment
{"greeting": "Hello, Docker!", "count": 1, "hostname": "9666f6e984c6", "storage": "redis"}%                                                  ⚡➜ hw_3_template (U 8b) curl -fsS -X POST http://127.0.0.1:8080/increment
{"greeting": "Hello, Docker!", "count": 2, "hostname": "9666f6e984c6", "storage": "redis"}%                                                  ⚡➜ hw_3_template (U 8b) curl -fsS -X POST http://127.0.0.1:8080/increment
{"greeting": "Hello, Docker!", "count": 3, "hostname": "9666f6e984c6", "storage": "redis"}%                                                  ⚡➜ hw_3_template (U 8b) curl -fsS -X POST http://127.0.0.1:8080/increment
{"greeting": "Hello, Docker!", "count": 4, "hostname": "9666f6e984c6", "storage": "redis"}%                                                  ⚡➜ hw_3_template (U 8b) curl -fsS -X POST http://127.0.0.1:8080/increment
{"greeting": "Hello, Docker!", "count": 5, "hostname": "9666f6e984c6", "storage": "redis"}%                                                  ⚡➜ hw_3_template (U 8b) 

⚡➜ hw_3_template (U 8b) docker compose down         
[+] down 3/3
 ✔ Container docker-hw-app-1   Removed                                                                                                  10.2s
 ✔ Container docker-hw-redis-1 Removed                                                                                                   0.1s
 ✔ Network docker-hw_default   Removed                                                                                                   0.1s
⚡➜ hw_3_template (U 8b) docker compose up -d        
[+] up 3/3
 ✔ Network docker-hw_default   Created                                                                                                   0.0s
 ✔ Container docker-hw-redis-1 Healthy                                                                                                   5.2s
 ✔ Container docker-hw-app-1   Started                                                                                                   5.2s
⚡➜ hw_3_template (U 8b) curl -fsS http://127.0.0.1:8080/         
{"greeting": "Hello, Docker!", "count": 5, "hostname": "5367c9b989af", "storage": "redis"}%                                                  ⚡➜ hw_3_template (U 8b) 

⚡➜ hw_3_template (U 8b) docker compose stop redis
[+] stop 1/1
 ✔ Container docker-hw-redis-1 Stopped                                                                                                   0.2s
⚡➜ hw_3_template (U 8b) curl -isS http://127.0.0.1:8080/healthz
HTTP/1.0 200 OK
Server: BaseHTTP/0.6 Python/3.13.18
Date: Sun, 15 Nov 2026 15:01:42 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 19
Cache-Control: no-store

{"status": "alive"}%                                                                                                                         ⚡➜ hw_3_template (U 8b) curl -isS http://127.0.0.1:8080/readyz
HTTP/1.0 503 Service Unavailable
Server: BaseHTTP/0.6 Python/3.13.18
Date: Sun, 15 Nov 2026 15:01:58 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 32
Cache-Control: no-store

{"error": "storage_unavailable"}%                                                                                                            ⚡➜ hw_3_template (U 8b) curl -isS -X POST http://127.0.0.1:8080/increment
HTTP/1.0 503 Service Unavailable
Server: BaseHTTP/0.6 Python/3.13.18
Date: Sun, 15 Nov 2026 15:02:13 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 32
Cache-Control: no-store

{"error": "storage_unavailable"}%                                                                                                            ⚡➜ hw_3_template (U 8b) curl -isS http://127.0.0.1:8080/      
HTTP/1.0 503 Service Unavailable
Server: BaseHTTP/0.6 Python/3.13.18
Date: Sun, 15 Nov 2026 15:02:25 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 32
Cache-Control: no-store

{"error": "storage_unavailable"}%

⚡➜ hw_3_template (U 8b) docker compose start redis
[+] start 1/1
 ✔ Container docker-hw-redis-1 Started                                                                                                   0.1s
⚡➜ hw_3_template (U 8b) curl -isS -X POST http://127.0.0.1:8080/increment
HTTP/1.0 200 OK
Server: BaseHTTP/0.6 Python/3.13.18
Date: Sun, 15 Nov 2026 15:03:08 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 90
Cache-Control: no-store

{"greeting": "Hello, Docker!", "count": 6, "hostname": "5367c9b989af", "storage": "redis"}%                                                  ⚡➜ hw_3_template (U 8b) 

