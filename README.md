# VAULT
![VAULT](screenshots/banner.png?raw=true "VAULT")

##What is VAULT?
VAULT is a fast command line utility for securely storing and retrieving user account information.

No more searching through that disorganized word doc with all your usernames and passwords in plaintext! (You know who you are...) Retrieving passworks is now as simple as:
```
$ vault github
    MASTER PASSWORD --> supersecretpassword!   #Enter your master password
   
    github                                     #Get you account information!
    USERNAME --> jkerman 
    PASSWORD --> munorbust!
```

###How do I set this up?
Linux/MacOS
  1. Install Python 3.6 and "pycrypto" package
  2. Download the files in this repository to your computer (ie. ~/GitHub/vault)
  3. Add vault shell script to ~/.bin
  4. Add -->  export PATH=$PATH":$HOME/.bin"  <-- to .bash_profile or .bash_rc file
  5. In vault.py update "path" variable to point at passwords.json

Windows
  1. Instructions coming soon!

###How do I use this?
After getting setup - type "vault" into a terminal window. This will return the following:
```
-a will add a new account 
-r will remove an existing account 
-u will update information of an existing account 
-g will get information for an existing account 
-l will list information for all accounts 
-h displays this help dialog
```
I've included example account information in passwords.json for playing around with VAULT and seeing how it works. I recommend removing existing entries with "-remove" before adding any new account information. 

NOTE using more than one "Master Password" will work for all functions except "-list" but is not recommended.

For example to add and account enter:
![add](screenshots/screenshot2.png?raw=true "add")

For faster access to account info enter "vault accountName".
![get](screenshots/screenshot1.png?raw=true "get")

###Can I sync my passwords across computers?
Sure! Do you have a folder backed up by Google Drive, OneDrive, Dropbox or another cloud storage service? Add passwords.json to this folder and edit the path in vault.py to point to this new location. When you make edits Google Drive, Dropbox, etc. will sync the latest version across your connected devices and back it up to the cloud.

###Is this safe?
Passwords are encrypted using an AES cipher and 32 character key that's generated on-the-fly. This means the key is not stored anywhere, it's generated from user input upon encrypt/decrypt actions - then forgotten. Anything BUT the correct master password will generate the wrong key and encrypt/decrypt will throw errors or return gibberish.

For more information on the AES cipher https://en.wikipedia.org/wiki/Advanced_Encryption_Standard

### Author
* **Joe Samela** - *Initial work* - [ForYourBrain.net](http://www.foryourbrain.net)
