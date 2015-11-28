## Explanations

* `event`
    * `id`: Event type
    * `service`: Event source service name
    * `type`: Monitored service type
    * `state`: Monitored service state
    * `action`: Description of the event action
    * `message`: Message describing the event

### Event Type

See also: https://github.com/bolasblack/monit/blob/feature/webhook/src/event.h#L31

### Service Type

See also: https://github.com/bolasblack/monit/blob/feature/webhook/src/monit.h#L253

### State Type

* 0: Successed
    * process start running
    * space free test succeeded
    * checksum is valid
    * etc ...
* 1: Failed
* 2: Changed
    * timestamp changed
    * scheduled action was performed
    * checksum was changed
    * etc ...
* 3: ChangedNot

### Action Type

* 1: Alert
* 2: Restart
* 3: Stop
* 4: Exec
* 5: Unmonitor
* 6: Start
* 7: Monitor

## Example

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<monit id="961596757191da129caf6ec937c423ef" incarnation="1440342614" version="5.14">
  <server>
    <uptime>6</uptime>
    <poll>30</poll>
    <startdelay>0</startdelay>
    <localhostname>vagrant-ubuntu-trusty-64</localhostname>
    <controlfile>/etc/monitrc</controlfile>
    <httpd>
      <address>127.0.0.1</address>
      <port>12346</port>
      <ssl>0</ssl>
    </httpd>
  </server>
  <platform>
    <name>Linux</name>
    <release>3.13.0-52-generic</release>
    <version>#86-Ubuntu SMP Mon May 4 04:32:59 UTC 2015</version>
    <machine>x86_64</machine>
    <cpu>1</cpu>
    <memory>501756</memory>
    <swap>0</swap>
  </platform>
  <services>
    <service name="hello.pid">
      <type>2</type>
      <collected_sec>1440342614</collected_sec>
      <collected_usec>554697</collected_usec>
      <status>512</status>
      <status_hint>0</status_hint>
      <monitor>1</monitor>
      <monitormode>0</monitormode>
      <pendingaction>0</pendingaction>
    </service>
    <service name="vagrant-ubuntu-trusty-64">
      <type>5</type>
      <collected_sec>1440342614</collected_sec>
      <collected_usec>555189</collected_usec>
      <status>0</status>
      <status_hint>0</status_hint>
      <monitor>1</monitor>
      <monitormode>0</monitormode>
      <pendingaction>0</pendingaction>
    </service>
  </services>
  <servicegroups>
  </servicegroups>
  <event>
    <collected_sec>1440342620</collected_sec>
    <collected_usec>555715</collected_usec>
    <service>Monit</service>
    <type>5</type>
    <id>65536</id>
    <state>2</state>
    <action>3</action>
    <message>
      <![CDATA[Monit 5.14 stopped]]>
    </message>
  </event>
</monit>
```