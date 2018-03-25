# LUNEX
Shell script to install a [Lunex Masternode](https://www.lunexcrypto.com/) on a Linux server running Ubuntu 16.04. Use it on your own risk.

***
## Installation:
```
wget -q https://raw.githubusercontent.com/zoldur/Lunex/master/lunex_install.sh
bash lunex_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open **Lunex Core Wallet**.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **1000** **LUNEX** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is un
12. Select your MN and click **Start Alias** to start it.
***

## Usage:
```
lunex-cli mnsync status
lunex-cli getinfo
lunex-cli masternode status #This command will show your masternode status
```

Also, if you want to check/start/stop **Lunex** , run one of the following commands as **root**:

```
systemctl status Lunex #To check the service is running.
systemctl start Lunex #To start Lunex service.
systemctl stop Lunex #To stop Lunex service.
systemctl is-enabled lunex #To check whetether Lunex service is enabled on boot or not.
```
***

## Issues:
If your Lunex Core Wallet doesn't sync, go to **Tools -> Open Wallet Configuration File** and add the following entries:
```
addnode=172.104.138.4
addnode=199.247.20.49
addnode=50.116.31.144
```

## Donations:  

Any donation is highly appreciated.  

**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x26B9dDa0616FE0759273D651e77Fe7dd7751E01E  
**LTC**: LeZmPXHuQEhkd8iZY7a2zVAwF7DCWir2FF

