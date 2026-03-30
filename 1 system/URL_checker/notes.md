# URL checker notes

## Initial Setup

```bash
# download python
sudo pacman -S python3
```
```bash
# download docker
sudo pacman -S docker
```
```bash
# download docker builder
sudo pacman -S docker-buildx
```

made requirements.txt file , starting with pythonping

Created Dockerfile

```bash
FROM python:3.12-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["python3", "URL_checker.py"]
```

```bash
# begin the docker application
sudo systemctl start docker
```
```bash
# have docker automatically startup on computer startup
sudo systemctl enable docker
```
```bash
# adding current user to the docker to avoid needing 'sudo' every time
sudo usermod -aG docker $USER
```
```bash
# build
docker build -t url-checker .
```
```bash
# run
docker run url-checker
```
