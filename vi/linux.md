

at currentl directory find gz file but exclude path "*deprecated/*" and "./*saf*/*" which contains P.0421285.1.01
find . -name "*.gz" ! -path "*deprecated/*"   ! -path "./*saf*/*" |xargs zgrep -l P.0421285.1.01


[ywang@VSDEDC001APESB2 deploy]$  find . -name "*.gz" ! -path "*deprecated/*"   ! -path "./*saf*/*" |xargs zgrep -l P.0421285.1.01
./work-project/log/2021-07-21.gz
./work-project-rest/log/2021-07-21.gz
./work-project-db-mssql-horlemann2/log/2021-07-21.gz
./work-project-db-mssql-baan/log/2021-07-21.gz
./work-project-sap-hcp100/log/out.log.2021-07-21.0.gz
./work-project-sap-hcp200/log/out.log.2021-07-23.0.gz
./work-project-sap-hcp400/log/out.log.2021-07-23.0.gz
./work-project-sap-hcp600/log/out.log.2021-07-21.0.gz
./work-project-sap-hcp500/log/out.log.2021-07-21.0.gz
[ywang@VSDEDC001APESB2 deploy]$


zgrep -H P.0421285.1.01 ./work-project-sap-hcp100/log/out.log.2021-07-21.0.gz

Search in gz files:

zgrep could search string from gz files from directory as example shown below

find <DIR>  -name “*.gz” |xargs zgrep -H “<SEARCH_PATTERN>”

If you wanted only the list of matching files, use -l:

find <DIR>  -name “*.gz” |xargs zgrep -l “<SEARCH_PATTERN>”
