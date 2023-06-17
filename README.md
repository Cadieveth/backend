# backend
Back-end Basic Dicoding

PROJECT AKHIR DICODING
MONEY TRACKER APP

Information Project
Project Name		: submission-mgce-ade
Project ID		: submission-mgce-ade
Project Number	: 405697238800

Buat App Engine
Region		: asia-southeast2
App Engine default service account

Buka Cloud Shell > Code Editor > New Terminal

Deploy money-tracker-api ke Cloud Run (Back-End)
https://github.com/dicodingacademy/a133-gcp-labs/tree/money-tracker-api
git clone -b money-tracker-api https://github.com/dicodingacademy/a133-gcp-labs.git backend

Deploy money-tracker ke Cloud Run (Front-End) 
https://github.com/dicodingacademy/a133-gcp-labs/tree/money-tracker
git clone -b money-tracker https://github.com/dicodingacademy/a133-gcp-labs.git frontend

Buat Instance Cloud SQL
Instance ID	: myinstance
Password	: root1234
Region 	: asia-southeast2 (Jakarta) – Single Zone
Database Ver	: MySQL 5.7
Machine Type	: Shared Core (1 vCPU, 0.614 GB)
Storage	: SSD (10 GB)

Detail SQL Instance
Connetion Name	: submission-mgce-ade:asia-southeast2:myinstance
Public IP Address	: 34.101.43.21
Service Account	: p405697238800-ernj3c@gcp-sa-cloud-sql.iam.gserviceaccount.com
Authorized Networks	: Public (0.0.0.0/0)

Buat Storage GCS (Bucket)
Bucket Name	: decoding-storage-d003
Region		: asia-southeast2
Storage Class	: Standard
Access Control: Fine-grained
allUsers	: Storage Object Viewer
Public Access [v]

Buat Service Account (IAM)
upload-image@submission-mgce-ade.iam.gserviceaccount.com
owner
create key : json

Grant Access Reviewer
reviewer_googlecloud@dicoding.com = viewer


TODO
Back-End:
serviceaccountkey.json (service account untuk upload image ke Cloud Storage). Untuk bagian ini, silakan buat service account baru dengan hak akses yang memungkinkan aplikasi mengunggah gambar ke Cloud Storage bucket, lalu buat key baru untuk service account tersebut, kemudian copy paste isi file-nya ke serviceaccountkey.json (timpa isi file sebelumnya). 
modules -> imgUpload.js (Cloud Storage). 
routes -> record.js (Cloud SQL). 
create_table.sql (skema tabel). Gunakan isi dari file ini untuk membuat tabel dan skema di Cloud SQL instance.

Deploy Backend
gcloud app deploy (hapus service: backend)
https://submission-mgce-ade.et.r.appspot.com

Front-End:
application -> config -> config.php (base URL dari Front-End).
http://frontend.submission-mgce-ade.et.r.appspot.com
application -> models -> Record_model.php (base URL dari Back-End). 
https://submission-mgce-ade.et.r.appspot.com

Deploy Frontend
Deploy = gcloud app deploy
http://frontend.submission-mgce-ade.et.r.appspot.com

notes: setelah deploy backend, copy <base url backend> ke Record_model.php (frontend). Setelah itu deploy frontend untuk mendapatkan <base url frontend>. Seteleh itu copy <base url frontend> pada config.php. Kemudian Deploy frontend kembali

Enable API
Buka APIs & Services
Pada list pilih Cloud SQL Admin API
ENABLE

Buat SQL Database
gcloud sql connect <nama instance MySQL nya> --user=root –quiet
use <nama_database>;
copy isi create_table.sql (backend).

Lunch Application

Pengiriman Submission
URL		: http://frontend.submission-mgce-ade.et.r.appspot.com/
Project ID	: submission-mgce-ade



