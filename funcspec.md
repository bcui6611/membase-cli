1. Enable/Disable bucket flush
Extend option for bucket-create / bucket-edit with --enable-flush

couchbase-cli bucket-create --enable-flush=1   where 1 means to enable flush and 0 means disable flush. Default is 0.

2. Bucket flush command
Flush all data under a bucket when flush option is enabled.

couchbase-cli bucket-flush
/pools/default/buckets/default/controller/doFlush

Success:  Bucket flushing is successful
Fail :  You have to use bucket-edit to enable flush option first before running flush request.

3. Enable bucket replicaIndex
Extend option for bucket-create with --enable-replicaIndex

couchbase-cli bucket-create --enable-replicaIndex 
By default, replicaIndex is set to false. You can enable it to add option --enable-replicaIndex
Note, this option won't be changed after the bucket is created. So you won't see it on bucket-edit options.

4. Bucket compact command
Compact all bucket data including datdabase and view index

couchbase-cli bucket-compact --bucket
/pools/default/buckets/default/controller/compactBucket

Compact bucket database data only --bucket --database-only
/pools/default/buckets/default/controller/compactDatabases
 
5. Cancel compact operation for a bucket
couchbase-cli bucket-cancel-compact
/pools/default/buckets/default/controller/cancelBucketCompaction

6. Set index-path for node
Extend node-init option with --node-init-index-path

couchbase-cli node-init --node-init-index-path

7. Enable/disable auto failover
Extend cluster-init option with --cluster-init-enable-autofailover

couchbase-cli cluster-init --cluster-init-enable-autofailover
By default, it is false, i.e. --cluster-init-enable-autofailover is not specified

8. XDCR create / edit
Create/Edit remote cluster connection
couchbase-cli xdcr-create / xdcr-edit
--xdcr-cluster-name
--xdcr-hostname
--xdcr-username
--xdcr-password

POST  /pools/default/remoteClusters?name=<>&hostname=<>&username=<>&password=<>
PUT /pools/default/remoteClusters?name=<>&hostname=<>&username=<>&password=<>

10 XDCR delete
cochbase-cli xdcr-delete 
--xdcr-delete


11. XDCR create replicate
couchbase-cli xdcr-replicate-init
--xdcr-replicate-from-bucket
--xdcr-replicate-to-cluster
--xdcr-replicate-to-bucket
--xdcr-replicate-type = "continuous"

12. XDCR cancel replicate
couchbase-cli xdcr-replicate-cancel

