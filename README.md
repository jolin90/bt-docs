# bt-docs
Documents for bluetooth


FAQ

1. I'm trying to build a bluetooh service through bluez on Linux.
According to that tutorial [http://people.csail.mit.edu/albert/bluez-intro/x604.html],
it is necessary to connect to the local SDP server in order to register the service.
But "sdp_connect( BDADDR_ANY, BDADDR_LOCAL, SDP_RETRY_IF_BUSY)" is returning NULL here
and all the services related to bluetooth are running without any problem on my Fedora,
apparently. Whenever I try to get information about the SDP local server through the
command "sdptool browse local", I get the following message: "Failed to connect to SDP
server on FF:FF:FF:00:00:00: Connection refused". Some users say it is necessary to get
sdpd running in order to use sdp_connect and here there is no package with binary called
sdpd, but I think sdpd is now part of bluetoothd on Fedora, so a sdp server was supposed
to be running when sdp_connect tried to connect. Why sdp_connect is not working?

You have to start bluetoothd with --compat flag.
I don't know if this is the "Fedora way" of doing it, but I edited
/usr/lib/systemd/system/bluetooth.service and included the flag in the ExecStart option.
ExecStart=/usr/libexec/bluetooth/bluetoothd --compat
Then
$ systemctl daemon-reload
$ systemctl restart bluetooth.service

This workaround works also on ubuntu 16.04. Need to edit
/lib/systemd/system/bluetooth.service and do
sudo systemctl daemon-reload && sudo service bluetooth restart

----------------------------------------------------------------------------------------------
