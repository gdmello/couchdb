# Couchdb 1.6.1

# Delete a replication job
## Get replication id
```
$ curl http://<user>:<password>@couchdb-aws-1.hostname.com:5984/_active_tasks
[{"pid":"<0.2375.0>","checkpoint_interval":5000,"checkpointed_source_seq":255463,"continuous":true,"doc_id":null,"doc_write_failures":0,"docs_read":246784,"docs_written":246784,"missing_revisions_found":246784,"progress":3,"replication_id":"0dfdc7d9ae354b93aeb927b566f0b580+continuous+create_target","revisions_checked":246784,"source":"http://<user>:*****@source-couchdb3.hostname.com:5984/my_db/","source_seq":6970688,"started_on":1474661894,"target":"my_db","type":"replication","updated_on":1474689855}]
```

## Cancel Replication JOb
```
$ curl -x POST http://admin:password@couchdb-aws-1.hostname.com:5984/_replicate -H 'Content-Type: application/json' -d '{"replication_id": "0dfdc7d9ae354b93aeb927b566f0b580+continuous+create_target", "cancel": True}'
$ {"ok":true,"_local_id":"0dfdc7d9ae354b93aeb927b566f0b580+continuous+create_target"}
```
