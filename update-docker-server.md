## Updating Production Server w/ Docker
When using the docker build for a production server, follow these instructions to apply updates. 

After SSHing into the server:
**Make sure you are in the correct directory (probably user/bonaso_data_portal)**

-Run these commands to update the server:
```bash
cd bonaso_data_server
git pull
cd .. 
```
- Run these commands to update the frontend:
```bash
cd boanso_data_web
git pull
cd ..
```
- Run these commands to update the main repo (probably only necessary if you've updated docker-compose.yaml)
```bash
git pull
```
- Reload the Docker servce
```bash
sudo docker compose down
sudo docker compose up -d
```
- For more substantial changes  (db migrations, installed new package/dependency change) run
```bash
sudo docker compose down
sudo docker compose up -d --build
```
- If you adjusted the Django DB, run:
```bash
sudo docker compose exec web python manage.py migrate
```
- Verify services are running with
```bash
sudo docker compose ps
```