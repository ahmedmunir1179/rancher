847  mvn install:install-file   -Dfile=asm=9.7.jar   -DgroupId=asm   -DartifactId=asm   -Dversion=9.7   -Dpackaging=jar
  848  mvn install:install-file   -Dfile=asm-9.7.jar   -DgroupId=asm   -DartifactId=asm   -Dversion=9.7   -Dpackaging=jar
  965  mvn clarn -o
  966  mvn clan -o
  967  mvn clean -o
  970  mvn compile -o
  973  mvn package -o
  977  mvn dependency:resolve
  978  mvn dependency:resolve-plugins
  982  mvn -version
  985  mvn -v
  988  mvn -v
  992  mvn package
  993  mvn package -o
  994  mvn build -o
  995  mvn clean -o
  996  history | grep mvn
  997  mvn compile-o
  998  mvn compile -o
 1003  mvn clean -o
 1004  mvn clean -o -X
 1015  mvn clean -o 
 1016  history | grep mvn
 1017  mvn package -o
 1031  mvn dependency:go-offline
 1032  mvn clean package -Dmaven.test.skip=true -o
 1034  mvn -o clean package
 1035  mvn clean package -o
 1036  mvn dependency:list
 1037  mvn dependency:tree
 1038  mvn help:evaluate -Dexpression=settings.localRepository -q -DforceStdout
 1040  history | grep mvn
 1041  mvn install:install-file   -Dfile=asm=9.7.jar   -DgroupId=asm   -DartifactId=asm   -Dversion=9.7   -Dpackaging=jar -o
 1042  mvn install:install-file   -Dfile=asm-9.7.jar   -DgroupId=asm   -DartifactId=asm   -Dversion=9.7   -Dpackaging=jar -o
 1043  mvn dependency:tree
 1044  mvn dependency:list
 1051  mvn -v





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





