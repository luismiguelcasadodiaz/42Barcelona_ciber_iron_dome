# Detect anomalous activity monitoring different OS parameters

The aim is to understand the weak points of a computer regarding malware

Create irondome.py

It will execute only if launched by root.
It is a daemon or a service
Monitors a critical zone in perpetuity.

Parameters:
a path to the zone to watch
a set of file extension to monitor

Detect:
a)disk read abuse
    psutil.disk_io_counters(perdisk=False, nowrap=True)
    
b)Intense criptography activity

● Devices begin to run suspiciously slower than usual since cryptojacking drains its computational resources.
● Processors or graphics cards get damaged without any apparent reason, or the device is overheating than usual.
● A high and consistent CPU usage percentage could indicate the presence of a crypto malware. Users can check the CPU usage via Task Manager (Windows) or Activity Monitor (macOS). The CPU usage should generally stay below 20-30%, but it exhibiting unexpected spikes can be the result of a crypto malware running in the background.
● Unexpected increase in electricity costs.

c)changes in the files entropy

Restrictions
log the alerts in /var/log/irondome/irondome.log
irondome execution should never exceec 100 MB of memory

BONUS
Create a backup folder in the user's HOME directory
Make incremental Backups at configurable intervals


[Online entropy calculator] (https://onlinetexttools.com/calculate-text-entropy)

the algorithm first counts the frequency of each symbol in the text.
calculate the probability of each symbol appearing in the text
applies Shannon's entropy formula:
> H = -Σp(x)log2p(x),
> p(x) is the probability that character x will appear in the text
> log2 is the base 2 logarithm

I need to calculate the entorpy of each file in the zone to wathc.