First install rethinkdb: https://rethinkdb.com/docs/install/

Start in root directory of repository:

```
sudo apt-get install libffi-dev build-essential python3 python3-pip # or equivalent for your distro
sudo pip3 install virtualenv # if you dont have it
virtualenv env
source env/bin/activate
pip install flask==0.11.1 bigchaindb python-gnupg
cd src/data
rethinkdb &>/dev/null &
bigchaindb -y configure
bigchaindb start &>/dev/null &
cd ..
env FLASK_APP=main.py flask initdb
python3 main.py
```
now visit http://localhost:5000/
