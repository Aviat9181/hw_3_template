
⚡➜ hw_3_template (! 6b) docker compose up -d --build
[+] Building 1.6s (12/12) FINISHED                                              
 => [internal] load local bake definitions                                 0.0s
 => => reading from stdin 516B                                             0.0s
 => [internal] load build definition from Dockerfile                       0.0s
 => => transferring dockerfile: 224B                                       0.0s
 => [internal] load metadata for docker.io/library/python:3.13             1.4s
 => [internal] load .dockerignore                                          0.0s
 => => transferring context: 2B                                            0.0s
 => [1/5] FROM docker.io/library/python:3.13@sha256:ecbe213fb818d557fd19d  0.0s
 => => resolve docker.io/library/python:3.13@sha256:ecbe213fb818d557fd19d  0.0s
 => [internal] load build context                                          0.0s
 => => transferring context: 127B                                          0.0s
 => CACHED [2/5] WORKDIR /app                                              0.0s
 => CACHED [3/5] COPY app/requirements.txt .                               0.0s
 => CACHED [4/5] RUN pip install --no-cache-dir -r requirements.txt        0.0s
 => CACHED [5/5] COPY app/ .                                               0.0s
 => exporting to image                                                     0.0s
 => => exporting layers                                                    0.0s
 => => exporting manifest sha256:ca2cd7419866600fa6c69130889fe1a00464cfd1  0.0s
 => => exporting config sha256:0e5ff014f9c71c4ea1197147550ece32d190ec428a  0.0s
 => => exporting attestation manifest sha256:bc83f029f6a5520ae1b8765b2040  0.0s
 => => exporting manifest list sha256:aa6a29a72944ac2403323eb2a9710940a46  0.0s
 => => naming to docker.io/library/docker-app:6b                           0.0s
 => => unpacking to docker.io/library/docker-app:6b                        0.0s
 => resolving provenance for metadata file                                 0.0s
[+] up 4/4
 ✔ Image docker-app:6b       Built                                          1.7s
 ✔ Volume docker-hw_app-data Created                                        0.0s
 ✔ Network docker-hw_default Created                                        0.1s
 ✔ Container docker-hw-app-1 Started                                        0.3s
⚡➜ hw_3_template (! 6b) docker volume ls 
DRIVER    VOLUME NAME
local     docker-hw_app-data
⚡➜ hw_3_template (! 6b) curl -fsS http://127.0.0.1:8080/
{"greeting": "Hello, Docker!", "count": 0, "hostname": "b5298425e2d9", "storage": "sqlite"}%                                                                    ⚡➜ hw_3_template (! 6b) сurl -fsS -X POST http://127.0.0.1:8080/increment
zsh: command not found: сurl
⚡➜ hw_3_template (! 6b) curl -fsS -X POST http://127.0.0.1:8080/increment
{"greeting": "Hello, Docker!", "count": 1, "hostname": "b5298425e2d9", "storage": "sqlite"}%  

⚡➜ hw_3_template (U! 6b) docker compose down
[+] down 2/2
 ✔ Container docker-hw-app-1 Removed                                       10.2s
 ✔ Network docker-hw_default Removed                                        0.1s
⚡➜ hw_3_template (U! 6b) docker compose up           
[+] up 2/2
 ✔ Network docker-hw_default Created                                        0.1s
 ✔ Container docker-hw-app-1 Created                                        0.0s
Attaching to app-1
app-1  | 2026-11-09 09:15:32,269 listening port=8000 storage=sqlite
⚡➜ hw_3_template (U! 6b) curl -fsS http://127.0.0.1:8080/
{"greeting": "Hello, Docker!", "count": 1, "hostname": "be8e5cb1e23c", "storage": "sqlite"}%                                                                    ⚡➜ hw_3_template (U! 6b) 
