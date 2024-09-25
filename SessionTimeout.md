# Session Timeout Settings

Specifies the amount of time that a connection between the Business Central Web client and the Business Central Server can remain idle before the session is stopped.

<br>

- Time span format: `[dd.]hh:mm:ss[.ff]`
    +  `dd`: days
    +  `hh`: hours
    +  `mm`: minutes
    +  `ss`: seconds
    +  `ff`: fractions of a second

<br>

By default, the `ClientServicesIdleClientTimeout` setting is set to `MaxValue`, which means no time limit, and the `SessionTimeout` setting is `00:20:00` (20 minutes). This means that when client connection is inactive, a session will close after 20 minutes.

<br>

Set new session timout
```PowerShell
Set-NAVWebServerInstanceConfiguration -WebServerInstance <ServerInstanceName> -KeyName SessionTimeout -KeyValue <timeout>
```