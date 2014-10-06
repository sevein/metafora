metafora etcd client
====================

Testing
-------

Testing the metafora etcd client requires that a new etcd instance be running.
The etcd instances should be reachable via the connection described by the 
connection string `localhost:5001,localhost:5002,localhost:5003` or a similar 
connection string should be exported as an environment variable `ETCDCTL_PEERS`.
The environemnt variable `ETCDTESTS` must also be set to `true`, otherwise
the tests will be skipped.

An example of running the integration tests is given in the command line below:

    PUBLIC_IP=`hostname --ip-address` IntegrationTests=true ETCDTESTS=true ETCDCTL_PEERS="${PUBLIC_IP}:5001,${PUBLIC_IP}:5002,${PUBLIC_IP}:5003" go test -v

    