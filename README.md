# ghostats
Go runtime and other stats over TCP

### Overview

Ghostats is a simple package that exposes runtime memory stats in additional to general service stats. There will be much more, including Graphite output.

But seriously. Don't rely on this yet since it will change quite a bit.

### Usage

Importing / starting Ghostats:
<pre>
package main

import "github.com/jamiealquiza/ghostats"

func main() {
	ghostats.Start("localhost", "8080", nil)
}
</pre>

Query Ghostats:
<pre>
% echo stats | nc localhost 8080
{
  "runtime-meminfo": {
    "Alloc": 57752,
    "BuckHashSys": 1440192,
    "Frees": 43,
    "GCSys": 71260,
    "HeapAlloc": 57752,
    "HeapIdle": 548864,
    "HeapInuse": 270336,
    "HeapObjects": 209,
    "HeapReleased": 0,
    "HeapSys": 819200,
    "LastGC": 1423257081166764688,
    "Lookups": 7,
    "MCacheInuse": 1200,
    "MCacheSys": 16384,
    "MSpanInuse": 3328,
    "MSpanSys": 16384,
    "Mallocs": 252,
    "NextGC": 53440,
    "NumGC": 2,
    "OtherSys": 293084,
    "PauseTotalNs": 106822,
    "StackInuse": 229376,
    "StackSys": 229376,
    "Sys": 2885880,
    "TotalAlloc": 67040
  },
  "service": {
    "start-time": "2015-02-06T14:11:21-07:00",
    "uptime-seconds": 5
  }
}
</pre>
