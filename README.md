# hello-world
Just my first repository


[
  {
    "triggerid": "23236",
    "expression": "min(/zbx-app01-lp1/system.cpu.load[all,avg1],5m)/last(/zbx-app01-lp1/system.cpu.num)>{$LOAD_AVG_PER_CPU.MAX.WARN}\r\nand last(/zbx-app01-lp1/system.cpu.load[all,avg5])>0\r\nand last(/zbx-app01-lp1/system.cpu.load[all,avg15])>0",
    "description": "Load average is too high",
    "url": "",
    "status": "0",
    "value": "0",
    "priority": "3",
    "lastchange": "1687162794",
    "comments": "Per CPU load average is too high. Your system may be slow to respond.",
    "error": "",
    "templateid": "22381",
    "type": "0",
    "state": "0",
    "flags": "0",
    "recovery_mode": "0",
    "recovery_expression": "",
    "correlation_mode": "0",
    "correlation_tag": "",
    "manual_close": "0",
    "opdata": "Load averages(1m 5m 15m): ({ITEM.LASTVALUE1} {ITEM.LASTVALUE3} {ITEM.LASTVALUE4}), # of CPUs: {ITEM.LASTVALUE2}",
    "event_name": "Load average is too high (per CPU load over {$LOAD_AVG_PER_CPU.MAX.WARN} for 5m)",
    "uuid": "",
    "groups": [
      {
        "groupid": "48",
        "name": "DC_NAURYZBAY_PROD"
      }
    ],
    "hosts": [
      {
        "hostid": "10570",
        "name": "zbx-app01-lp1",
        "host": "zbx-app01-lp1",
        "maintenance_status": "0",
        "proxy_hostid": "0",
        "description": ""
      }
    ],
    "items": [
      {
        "itemid": "45593",
        "name": "Load average (15m avg)",
        "key_": "system.cpu.load[all,avg15]",
        "lastvalue": "3.25"
      },
      {
        "itemid": "45594",
        "name": "Load average (1m avg)",
        "key_": "system.cpu.load[all,avg1]",
        "lastvalue": "2.49"
      },
      {
        "itemid": "45595",
        "name": "Load average (5m avg)",
        "key_": "system.cpu.load[all,avg5]",
        "lastvalue": "2.9"
      },
      {
        "itemid": "45600",
        "name": "Number of CPUs",
        "key_": "system.cpu.num",
        "lastvalue": "4"
      }
    ]
  },
  {
    "triggerid": "63174",
    "expression": "max(/kzlapib05/zabbix[host,agent,available],{$AGENT.TIMEOUT})=0",
    "description": "Zabbix agent is not available",
    "url": "",
    "status": "0",
    "value": "1",
    "priority": "3",
    "lastchange": "1683497075",
    "comments": "For passive only agents, host availability is used with {$AGENT.TIMEOUT} as time threshold.",
    "error": "",
    "templateid": "53481",
    "type": "0",
    "state": "0",
    "flags": "0",
    "recovery_mode": "0",
    "recovery_expression": "",
    "correlation_mode": "0",
    "correlation_tag": "",
    "manual_close": "1",
    "opdata": "",
    "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
    "uuid": "",
    "groups": [
      {
        "groupid": "52",
        "name": "DC_NAURYZBAY_DEV_TEST"
      }
    ],
    "hosts": [
      {
        "hostid": "10890",
        "name": "kzlapib05",
        "host": "kzlapib05",
        "maintenance_status": "0",
        "proxy_hostid": "10565",
        "description": ""
      }
    ],
    "items": [
      {
        "itemid": "141155",
        "name": "Zabbix agent availability",
        "key_": "zabbix[host,agent,available]",
        "lastvalue": "0"
      }
    ]
  },
  {
    "triggerid": "63357",
    "expression": "min(/kzlappbpm12ct.eub.kz/vm.memory.utilization,5m)>{$MEMORY.UTIL.MAX}",
    "description": "High memory utilization",
    "url": "",
    "status": "0",
    "value": "1",
    "priority": "3",
    "lastchange": "1686686923",
    "comments": "The system is running out of free memory.",
    "error": "",
    "templateid": "53480",
    "type": "0",
    "state": "0",
    "flags": "0",
    "recovery_mode": "0",
    "recovery_expression": "",
    "correlation_mode": "0",
    "correlation_tag": "",
    "manual_close": "0",
    "opdata": "",
    "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
    "uuid": "",
    "groups": [
      {
        "groupid": "52",
        "name": "DC_NAURYZBAY_DEV_TEST"
      }
    ],
    "hosts": [
      {
        "hostid": "10888",
        "name": "kzlappbpm12ct.eub.kz",
        "host": "kzlappbpm12ct.eub.kz",
        "maintenance_status": "0",
        "proxy_hostid": "10565",
        "description": ""
      }
    ],
    "items": [
      {
        "itemid": "141750",
        "name": "Memory utilization",
        "key_": "vm.memory.utilization",
        "lastvalue": "99.256999"
      }
    ]
  }
]



