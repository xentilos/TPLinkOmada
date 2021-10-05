# Manually change port in Omada Controller(linux)

If you switch portal ports to something that is in use please fallow below to fix it

- do backup of DB /opt/tplink/EAPController/data/db/
- start mongodb
`sudo mongod --noauth --port=27217 --dbpath /opt/tplink/EAPController/data/db/ --bind_ip_all`
- connect to mongoDB with external tool like NoSQLBooster
- in omada/globalsetting change ports
- commit the changes
- close mongodb 
- change file owner and group for all files in `/opt/tplink/EAPController/data/db/` and ` /opt/tplink/EAPController/data/db/journal/` to
`omada:omada`
- start omada `sudo tpeap start`
