# GCP Private Key Uploader

This folder contains a script to conduct the following tasks, as mentioned in [this blog post]():
- Create a keypair.
- Generate an X509 certificate and upload it with a specified service account.
- Sign the private key for decryption in a given instance's vTPM.

Ideally, this script provides inspiration for an App Engine instance which would 
create the key and associate it with a particular instance and service account. 
One can trigger this with the following command:

```
go run main.go --instanceName $INSTANCENAME --projectID $PROJECTID 
--zone $INSTANCEZONE --serviceAccount projects/$PROJECTID/serviceAccounts/$SERVICEACCOUNT --outputFile $OUTPUTFILE
```

A user should then SCP this file onto the target compute instance and decrypt the encrypted key.
