# runstats
Go runtime and other stats over TCP

### Overview

Runstats exposes runtime memory stats in addition to general service stats.

### Usage

Importing / starting Runstats:
```go
package main

import "github.com/jamiealquiza/runstats"

func main() {
	runstats.Start("localhost", "8080", nil)
}
```

Query Runstats:
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
