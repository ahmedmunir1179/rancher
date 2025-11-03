split -b 15M myfolder.tar myfolder.tar.part-


cat myfolder.tar.part-* > myfolder.tar

tar -xvf myfolder.tar

tar -cvf - myfolder/ | split -b 15M - myfolder.tar.part-

===============================
python 

A. Thin mode (default)

No Oracle Client required
Pure Python implementation — no need to install Oracle Instant Client or full Oracle client.
Works for most applications: queries, DML, PL/SQL, etc
Connects directly using a TCP connection to the database.
You can use connection strings like:

import oracledb
conn = oracledb.connect(user="scott", password="tiger", dsn="dbhost:1521/orclpdb")


B. Thick mode

Requires Oracle Client (Instant Client or full client).
Needed if you require:
Advanced features (e.g. FAN, DRCP, or older DB versions < 12c)
Certain authentication methods (like Kerberos)
Some advanced data types or configurations not supported in thin mode.
To enable it:

import oracledb
oracledb.init_oracle_client(lib_dir="/path/to/instant_client")

-----------------
import oracledb

conn = oracledb.connect(
    user="scott",
    password="tiger",
    dsn="dbhost:1521/orclpdb"
)

print("Connected to:", conn.version)

============================
check mode

import oracledb
print("Running in", "Thick" if oracledb.is_thick_mode() else "Thin", "mode")





