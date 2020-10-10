# Fixing "NO PUBKEY" in Parrot security OS.

Incase your parrot security OS is not updating while you try updating it through:
```bash
sudo apt update
```

Go to /etc/apt/sources.list.d/parrot.list:
```bash
sudo nano /etc/apt/sources.list.d/parrot.list
```

Update the contents to the ones below as written in https://parrot.org/docs:
```
# parrot repository
# this file was automatically generated by parrot-mirror-selector
deb https://deb.parrot.sh/parrot/ rolling main contrib non-free
#deb-src https://deb.parrot.sh/parrot/ rolling main contrib non-free
deb https://deb.parrot.sh/parrot/ rolling-security main contrib non-free
#deb-src https://deb.parrot.sh/parrot/ rolling-security main contrib non-free
```

Then try updating the pc again using:
```bash
sudo apt update
```

It will result to an error saying *NO PUBKEY B56FFA946EB1660A* or possibly give you another pubkey other than *B56FFA946EB1660A* .
TO add this key,do this:
```bash
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys B56FFA946EB1660A
```

keyserver.ubuntu.com is the server you will be using.
Now you can run:
```bash
sudo apt update
```
or
```bash
sudo parrot-upgrade
```

It will now update your packages and repos.

Great day ahead!
