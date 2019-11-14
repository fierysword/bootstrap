***Bootstrap 13-nov-2019*** [download](https://github.com/XVictus-project/bootstrap/releases/download/bootstrap/bootstrap.zip)
 
____
# :grey_question: HOW TO

:arrow_right: <a href="#linux">for Linux</a>

This is an archive with blockchain folders for quick synchronization.<br>
In square brackets you will see the date of creation of the archive.

You need to close the wallet and from the folder `%appdata%\XVIC` delete the folders of the same name, which are in the archive.<br>
Then unzip the folders from the archive to the `%appdata%\XVIC` folder and start the wallet.

***Tools***:<br>
[7-ZIP](https://www.7-zip.org/) is a file archiver.
____
 :one: Wait for the wallet to complete.

![](https://i.imgur.com/x3uBi0o.png)

:two: Open any folder. In the address bar, type `%appdata%\XVIC` and press <kbd>ENTER</kbd><br>

![](https://i.imgur.com/ggQRaVB.png)

:three: Select the files as in the screenshot and press the <kbd>DELETE</kbd> key. Confirm that you want to delete the folders.<br>

![](https://i.imgur.com/2NlI8n5.png)

:four: Download the archive.<br>

:five: Open archive. Select all files inside the archive. And drag these files with the mouse to the desired folder `%appdata%\XVIC`<br>

![](https://i.imgur.com/bfgAT0W.png)

:six: Wait for the copy to finish.<br>
:seven: Open your wallet.
____
# For Linux
<a name="linux"></a>
Type the following commands sequentially if XVIC is configured as a **service**:<br>
`systemctl stop xvic`<br>
`rm -rf .xvic/blocks/ .xvic/chainstate/ .xvic/sporks/ .xvic/zerocoin/`<br>
`wget https://github.com/XVictus-project/bootstrap/releases/download/bootstrap/bootstrap.zip`<br>
`unzip bootstrap.zip -d .xvic/`<br>
`systemctl start xvic`<br>
`rm -rf bootstrap.zip`

***OR***

Type the following commands sequentially if XVIC is configured as a **daemon**:<br>
`./xvicd stop`<br>
`rm -rf .xvic/blocks/ .xvic/chainstate/ .xvic/sporks/ .xvic/zerocoin/`<br>
`wget https://github.com/XVictus-project/bootstrap/releases/download/bootstrap/bootstrap.zip`<br>
`unzip bootstrap.zip -d .xvic/`<br>
`./xvicd -daemon`<br>
`rm -rf bootstrap.zip`

:exclamation: Wait for full synchronization:<br>
Type `xvic-cli getblockcount`<br>
Compare the resulting number with the block number in the [Explorer](https://explorer.xvictus.com/). If the blocks match - synchronization is complete. If not match - wait a bit and re-enter the `xvic-cli getblockcount` command.
