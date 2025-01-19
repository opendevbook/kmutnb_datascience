# **Section 3** Docker compose with Dockerfile

- Inside folder `dockerjupyterlab1`
- Create folder `notebooks`
- Create docker-compose.yml in sidefolder 

```
```


``` title="docker-compose.yml"
version: '3.8'

services:
  data-science-jupyterlab:
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "8888:8888" # Map Jupyter Lab's port to the host
    volumes:
      - ./notebooks:/app # Mount a local directory for persistent storage of notebooks
    container_name: data-science-container
    command: ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
```
Show file browser:
![](../assets/images/compose1.png)