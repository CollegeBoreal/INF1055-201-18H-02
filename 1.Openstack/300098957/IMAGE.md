http://cloud-images.ubuntu.com/precise/current/precise-server-cloudimg-amd64-disk1.img

Ubuntu 16.04 Image

```
$ wget http://cloud-images.ubuntu.com/xenial/current/xenial-server-cloudimg-amd64-disk1.img
```

```
$ glance --os-username=admin --os-password devstack \
         --os-tenant-name=admin \
         --os-auth-url=http://10.0.2.32:5000/v2.0 \
         image-create \
         --name="Ubuntu-16.04" \
         --is-public=true \
         --disk-format=qcow2 \
         --container-format=bare \
         --file xenial-server-cloudimg-amd64-disk1.img
```

--

```
$ cd /run/shm  
$ wget https://cloud-images.ubuntu.com/precise/current/precise-server-cloudimg-amd64-disk1.img
$ glance image-create \
         --name "Ubuntu-14.04" \
         --disk-format qcow2 \
         --container-format bare \
          --is-public True \
          --progress \
         --file precise-server-cloudimg-amd64-disk1.img
$ nova boot --flavor m1.tiny --image Ubuntu-14.04 --nic net-id=<NET_ID> --key-name <KEY_PAIR> instancetest1
$ ssh -i <KEY_PAIR> ubuntu@<INSTANCE_FLOATING_IP>
```

```
$  glance image-delete "Ubuntu-16.04"
```


```
$ cd /run/shm  
$ wget http://download.cirros-cloud.net/0.3.4/cirros-0.3.4-x86_64-disk.img
$ glance image-create \
         --name "cirros-0.3.4" \
         --disk-format qcow2 \
         --container-format bare \
          --is-public True \
          --progress \
         --file cirros-0.3.4-x86_64-disk.img
$ nova boot --flavor m1.tiny --image Ubuntu-14.04 --nic net-id=<NET_ID> --key-name <KEY_PAIR> instancetest1
$ ssh -i <KEY_PAIR> ubuntu@<INSTANCE_FLOATING_IP>
```
