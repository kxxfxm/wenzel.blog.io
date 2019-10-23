# Connecting Oracle Cloud DB with Navicat via Wallet and TNS name

## Using OCI (Oracle Cloud Infrastructure)

#### Download Oracle Instant Client
- [Download](https://www.oracle.com/database/technologies/instant-client/downloads.html), choose the corresponding version.
- Unzip and copy to directory under your navicat

#### Set navicat environment
Open Navicat, go to `Tools->Setting->Environment`, set OCI library (oci.dill), the value is the the `oci.dill` file under the directory we create in the previews step, which is possibly called `instantclient_19_3`.
Restart Navicat and the setting should work now.

#### Download the Wallet
Download the Wallet from your autonomous DB.
Unzip it and copy to a safety location.
Set system environment, add a variable called `TNS_ADMIN`, which is the , and the value is the location of location of the Wallet.

your Wallet.
Edit the file called `sqlnet.ora` in the Wallet, replcae `“?/network/admin”` to the value of `TNS_ADMIN`, which is the location of the Wallet.

#### Build connection
Open Navicat, build a connection, choose TNS and enter the TNS name shown in your autonomous DB, the user name maybe `ADMIN`, and password is the one you entered when building the autonomous DB.

Good luck!
