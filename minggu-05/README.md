Cara Install CockroachDb menggunakan Docker

1. Jalankan Terminal
2. Jalankan perintah pull image cockroachdb, tunggu hingga proses selesai
```
$ docker pull cockroachdb/cockroach
Using default tag: latest
latest: Pulling from cockroachdb/cockroach
27833a3ba0a5: Pull complete
7eeeadc1cbce: Pull complete
58d28f3214d5: Pull complete
7c994667c40c: Pull complete
Digest: sha256:44249e8133bd5c02165703854a86d84089fa741a018071cfe41b5ce4cda7ac39
Status: Downloaded newer image for cockroachdb/cockroach:latest
```
3. Buat Bridge Network pada docker
```
$ docker network create -d bridge roachnet
49fccc74a2524ffd5a05eb011155380c072c0a31873f05d97e926667a1487e36
```
4. Jalankan service cockroachdb
```
$ docker run -d --name=roach1 --hostname=roach1 --net=roachnet -p 26257:26257 -p 8080:8080 cockroachdb/cockroach start --insecure
```
5. Cek container, pastikan UP
```
$ docker ps -a
CONTAINER ID        IMAGE                   COMMAND                  CREATED             STATUS              PORTS                                              NAMES
dbc1f3190f58        cockroachdb/cockroach   "/cockroach/cockro..."   4 seconds ago       Up 4 seconds        0.0.0.0:8080->8080/tcp, 0.0.0.0:26257->26257/tcp   roach1
```
6. Test Cluster
```
$ docker exec -it roach1 ./cockroach sql --insecure
# Welcome to the cockroach SQL interface.
# All statements must be terminated by a semicolon.
# To exit: CTRL + D.
#
# Server version: CockroachDB CCL v19.1.5 (x86_64-unknown-linux-gnu, built 2019/09/23 14:12:16, go1.11.6) (same version as client)
# Cluster ID: aec879f9-844b-46cc-aa81-0af7d201a408
#
# Enter \? for a brief introduction.
#
root@:26257/defaultdb>
```
7. Buat Database "nganu"
```
root@:26257/defaultdb> create database nganu;
CREATE DATABASE

Time: 4.420966ms

root@:26257/defaultdb> show databases;
  database_name
+---------------+
  defaultdb
  nganu
  postgres
  system
(4 rows)

Time: 672.14µs
```
8. Pilih Database
```
root@:26257/defaultdb> use nganu;
SET

Time: 247.812µs
```
9. Buat Tabel
```
root@:26257/nganu> CREATE TABLE nganu.accounts (id INT PRIMARY KEY, balance DECIMAL);
CREATE TABLE

Time: 5.573474ms
```
10. Memasukkan data ke Tabel
```
root@:26257/nganu> INSERT INTO nganu.accounts VALUES (1, 1000.50);
INSERT 1

Time: 4.914008ms
```
11. Lihat data dalam tabel
```
root@:26257/nganu> SELECT * FROM nganu.accounts;
  id | balance
+----+---------+
   1 | 1000.50
(1 row)

Time: 537.781µs
```