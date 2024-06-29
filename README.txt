Notes:
table Creation

CREATE TABLE Singers (
    SingerId INT64 NOT NULL,
    FirstName STRING(1024),
    LastName STRING(1024),
    SingerInfo BYTES(MAX),
) PRIMARY KEY (SingerId);
CREATE TABLE Albums (
    SingerId INT64 NOT NULL,
    AlbumId INT64 NOT NULL,
    AlbumTitle STRING(MAX)
) PRIMARY KEY (SingerId, AlbumId),
INTERLEAVE IN PARENT Singers ON DELETE CASCADE;

Cloud Shell
-----------
git clone https://github.com/googleapis/python-spanner.git

virtualenv env
source  env/bin/activate

python-spanner/samples/samples

pip install -r requirements.txt 

python snippets.py spannerlab --database-id demodb insert_with_dml
python snippets.py spannerlab --database-id demodb insert_data

python snippets.py spannerlab --database-id demodb add_column
