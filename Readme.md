For this experement you will need:

* VirtualBox ~> [4.1](http://download.virtualbox.org/virtualbox/4.1.2/VirtualBox-4.1.2-73507-OSX.dmg).
* One specialised, standardised, scientificised owl.
* bundler

Then:

* `bundle install`
* `vagrant up`
* `vagrant ssh` #=> ssh'd to a box with httperf already installed

To test your server, try something like:

    httperf --timeout=5 --client=0/1 --server=<your-ip-here> --port=8080 --uri=/?value=benchmarks --rate=100 --send-buffer=4096 --recv-buffer=16384 --num-conns=50000 --num-calls=10

replacing `<your-ip-here>` with the local IP addy of your host machine. You can find that out by running `ifconfig`.

Good Luck!
