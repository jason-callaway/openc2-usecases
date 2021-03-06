Reporting and Monitoring
========================

In Cyberphysical systems (CPS), there is always a blending of data and physical
activity and physically adjacent systems. In a trivial example, a pedestrian
stepping in front of an autonomous car may be a data event the sets an alarm and
a trigger. How fast the car can brake is a physical activity that is always
finite in duration, but that may be different on a wet road or an icy one. In
any case, stopping faster than the car behind can do may also result in
cataclysmic failure.

On a power transmission grid, blocking the software that operates a substation
with a DDOS Attack may be indistinguishable in effect from simply shooting a
transformer with a rifle. CPS cybersecurity must always consider the blending of
cyber and physical.

A CPS system, whether a microgrid or factory floor or a wet utility or a swarm
of drones, likely consists of multiple autonomous or semiautonomous systems.
Cybersecurity monitoring of such systems may include monitoring the “other”
systems, the services they provide, or the net effect of all of the systems
working together.

This leads to a requirement for what I call a reporting function. A report may
be immediate (what is going on now), delayed (report back at 3:00 or in two
hours), triggered (report if this ever happens). It may be rate driven (report
if this happens more then 5 times an hour or 5 times a minute). It may track
longer term monitoring, and the monitoring could be event based (count each time
you see this) or episodic (record the flow rate every five minutes). The
monitoring period could be fixed (watch this and report back at 5:00) or polled
(watch this and I will come back later to get a report). The polled monitoring
could be perpetual AND time limited (watch this and I will come back later to
get a report of the last 4 hours).

Patterns for this have been previously described in other OASIS specifications
for CPS. The Energy Interoperation specification defines a report service to
specify and retrieve a report on power grid status and power flows.

<http://docs.oasis-open.org/energyinterop/ei/v1.0/os/energyinterop-v1.0-os.html#_Toc388604017>

The Energy Interoperation (EI) report service can define a report on the fly, or can
reference a standard well-known report. It also supports the notion of a CPS
knowing its baseline, and being able to report variance from that baseline.

EI Reports are simple Streams (as defined in WS-Calendar) with some metadata identifying the report and a
collection of Intervals containing the Payloads for each [measurement]. Reports
can be of the past, the present, or the future. A Report appears as a series of
[measurements] in the past. A Snap is a Report made as of a single moment. A
Projection is in the same form as a report, but it includes projections of what
will be in the future, including a confidence level in the payload.

EI Reported values can be Actual, Summed (across several sources), Derived based on
remote system knowledge) Mean (over a specified period), Peak, or Projected.

The OBIX specification, used to interact with many CPS in critical facilities,
defines a “Watch Service” in both Client Polled and Server Pushed variants. (In
OBIX, the “server” is the gateway device that communicates using OBIX)

<http://docs.oasis-open.org/obix/obix/v1.1/cs01/obix-v1.1-cs01.html#_Toc430940025>

Each of these describes useful patterns for establishing remote monitoring and
reporting of remote CPS.
