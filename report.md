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


