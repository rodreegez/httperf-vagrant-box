For this experement you will need:

* VirtualBox ~> [4.1](http://download.virtualbox.org/virtualbox/4.1.2/VirtualBox-4.1.2-73507-OSX.dmg).
    "If you have no choice but to use an earlier version of VirtualBox, 
    you can use earlier versions of Vagrant which work with them. For 
    VirtualBox 4.0, this is the 0.7.x line, and for VirtualBox 3.2.x, 
    this is the 0.6.x line." - Do this at yr own risk.
* One specialised, standardised, scientificised owl.
* bundler

Then:

* `bundle install`
* `vagrant up`
* `vagrant ssh` #=> ssh'd to a box with httperf already installed

To test your server, try something like:

    httperf --timeout=5 --client=0/1 --server=<your-ip-here> --port=8040 --uri=/?value=benchmarks --rate=100 --send-buffer=4096 --recv-buffer=16384 --num-conns=50000 --num-calls=10

replacing `<your-ip-here>` with the local IP addy of your host machine. You can find that out by running `ifconfig`.

## Workflow

* spin up your server on the host machine on port 8040
* run `ifconfig` and make a note of your IP address (something like `192.168.0.103`)
* in a new tab/split run `vagrant ssh` to access the vagrant box
* run the command above, subbing the IP address as directed

Good Luck!
