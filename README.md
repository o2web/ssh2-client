# Ssh2-client
--

This pacakge has been forked from https://github.com/ideaconnect/idct-sftp-client

Library that provides wrapper methods around SSH2, SCP and SFTP to simplify file download/upload over SSH/SCP/SFTP.


## Warning
=======
I am still thinking about unification of download / upload methods by passing a paramter which would define the connection type therefore method names may change.

## Example


````php
use O2Web\Networking\Ssh2\Client;
use O2Web\Networking\Ssh2\Credentials;

$client = new Client();

$username = 'YOUR_USER_NAME';
$password = 'YOUR_PASSWORD';
$host = 'HOST_NAME';

$credentials = Credentials::withPassword($username, $password);

$client->setCredentials($credentials);
$client->connect($host);

$client->download(ENTER_REMOTE_FILE_NAME);
$client->download(ENTER_REMOTE_FILE_NAME, ENTER_LOCAL_FILE_NAME);

$client->scpDownload(ENTER_REMOTE_FILE_NAME);

$client->scpUpload(ENTER_LOCAL_FILE_NAME,ENTER_REMOTE_FILE_NAME);

$client->close();
````
