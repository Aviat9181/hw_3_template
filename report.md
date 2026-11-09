⚡➜ hw_3_template (! 4b) docker run --rm -p 8080:8000 -e 'GREETING=Привет из контейнера!' docker-app
2026-11-09 08:43:38,395 listening port=8000 storage=sqlite
2026-11-09 08:44:11,017 http 172.17.0.1 "GET / HTTP/1.1" 200 -
2026-11-09 08:44:13,755 http 172.17.0.1 "POST /increment HTTP/1.1" 200 -
2026-11-09 08:44:16,303 http 172.17.0.1 "POST /increment HTTP/1.1" 200 -

⚡➜ ~ curl -fsS http://127.0.0.1:8080/                 
{"greeting": "Привет из контейнера!", "count": 0, "hostname": "8cb3e12cac4a", "storage": "sqlite"}%                                                             ⚡➜ ~ curl -fsS -X POST http://127.0.0.1:8080/increment
{"greeting": "Привет из контейнера!", "count": 1, "hostname": "8cb3e12cac4a", "storage": "sqlite"}%                                                             ⚡➜ ~ curl -fsS -X POST http://127.0.0.1:8080/increment
{"greeting": "Привет из контейнера!", "count": 2, "hostname": "8cb3e12cac4a", "storage": "sqlite"}%                                                             ⚡➜ ~ 

