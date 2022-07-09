# ipmi event logs

# clear event logs from ilo panel
```text
"ID","Severity","Last Update","Initial Update","Count","Description",
"9816","Informational","07/09/2022 11:31","07/09/2022 11:31","1","Event log cleared by: administrator.",
```

# server is off - press power on from server
```text
9826		07/09/2022 11:38	07/09/2022 11:38	1	Server power restored.
9825		07/09/2022 11:38	07/09/2022 11:38	1	Server reset.
```

# server is on - press power once
```text
9828		07/09/2022 11:44	07/09/2022 11:44	1	Server power removed.
9827		07/09/2022 11:43	07/09/2022 11:43	1	Embedded Flash/SD-CARD: Restarted.
```

# server is off - press power once
```text
9831		07/09/2022 11:45	07/09/2022 11:45	1	Server power restored.
9830		07/09/2022 11:45	07/09/2022 11:45	1	Server reset.
```

# server is on - hold power until server shut
```text
9832		07/09/2022 11:47	07/09/2022 11:47	1	Server power removed.
```
# server is off - hold power
```text
9835		07/09/2022 11:49	07/09/2022 11:49	1	Server power restored.
9834		07/09/2022 11:49	07/09/2022 11:49	1	Server reset.
```

# take power supply 2 out and put back in
- no event log

# take out only power server has and shut whole server including ilo after put power back in
```text
9842		[NOT SET] 	[NOT SET] 	1	Browser login: administrator - 10.0.10.200(DNS name not found).
9841		[NOT SET] 	[NOT SET] 	1	APO: Last power state restored.
9840		[NOT SET] 	[NOT SET] 	1	Server power restored.
9839		[NOT SET] 	[NOT SET] 	1	Server reset.
9838		[NOT SET] 	[NOT SET] 	1	iLO network link up at 1000 Mbps.
9837		[NOT SET] 	[NOT SET] 	1	Power restored to iLO.
```

# ilo dedicate port taking out and put back in
```text
9846		07/09/2022 12:00	07/09/2022 12:00	1	iLO network link up at 1000 Mbps.
9845		07/09/2022 12:00	07/09/2022 12:00	1	iLO network link down.
```

# server is on - press momentary press on ilo
```text
9849		07/09/2022 12:03	07/09/2022 12:03	1	Embedded Flash/SD-CARD: Restarted.
9848		07/09/2022 12:03	07/09/2022 12:03	1	Power-Off signal sent to host server by: administrator.
```

# server is off - press momentary press on ilo
```text
9854		07/09/2022 12:04	07/09/2022 12:04	1	Server power restored.
9853		07/09/2022 12:04	07/09/2022 12:04	1	Server reset.
9852		07/09/2022 12:04	07/09/2022 12:04	1	Power-On signal sent to host server by: administrator.
```

# server is on - press and hold from ilo panel
```text
9858		07/09/2022 12:26	07/09/2022 12:26	1	Server power removed.
9857		07/09/2022 12:26	07/09/2022 12:26	1	Embedded Flash/SD-CARD: Restarted.
9856		07/09/2022 12:26	07/09/2022 12:26	1	Power-Off signal sent to host server by: administrator.
```

# server is on - cold boot from ilo panel
```text
9868		07/09/2022 12:29	07/09/2022 12:29	1	Server power restored.
9867		07/09/2022 12:29	07/09/2022 12:29	1	Server reset.
9866		07/09/2022 12:29	07/09/2022 12:29	1	Server power removed.
9865		07/09/2022 12:29	07/09/2022 12:29	1	Power on request received by: Automatic Power Recovery.
9864		07/09/2022 12:29	07/09/2022 12:29	1	Host server reset by: administrator.
```

# server is on - reset from ilo panel
```text
9872		07/09/2022 12:30	07/09/2022 12:30	1	Server power restored.
9871		07/09/2022 12:30	07/09/2022 12:30	1	Server reset.
9870		07/09/2022 12:30	07/09/2022 12:30	1	Host server reset by: administrator.
```