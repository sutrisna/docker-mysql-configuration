## Cara running dontainer
```bash
sudo docker compose up -d
```
## Cara stop & hapus container
```bash
sudo docker compose down
```
## Cek ID COntainer
```bash
sudo docker ps
```
## Masuk ke dalam container
```bash
sudo docker exec -it <ID_CONTAINER> bash
```
- Jika sudah masuk ke dalam container lalu ketik :
```bash
mysql -u root -p
```
- Masukan MYSQL_ROOT_PASSWORD yang sudah di buat di file docker-compose.yml
## Cara backup db
```bash
sudo docker exec -it <ID_CONTAINER> bash
```
```bash
mysqldump -u root -p <your_DB> > <path>lmu_db_backup.sql
```
- Contoh `mysqldump -u root -p lmu_db > /var/lmu_db_backup.sql`
- Masukan MYSQL_ROOT_PASSWORD yang sudah di buat di file docker-compose.yml
- lalu ls maka akan ada file `lmu_db_backup.sql`
## Cara copy backup dari docker ke local
```bash
sudo docker cp <ID_CONTAINER>:<lokasi path hasil backup> <path local>
```
- Contoh `sudo docker cp <ID_CONTAINER>:/var/lmu_db_backup.sql /home/mylaptop`

**Note env mysql pada file docker-compose.yml hanya contoh**