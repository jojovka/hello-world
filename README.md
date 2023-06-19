# hello-world
Just my first repository


{
  "jsonrpc": "2.0",
  "result": {
    "23236": {
      "triggerid": "23236",
      "expression": "min(/zbx-app01-lp1/system.cpu.load[all,avg1],5m)/last(/zbx-app01-lp1/system.cpu.num)>{$LOAD_AVG_PER_CPU.MAX.WARN}\r\nand last(/zbx-app01-lp1/system.cpu.load[all,avg5])>0\r\nand last(/zbx-app01-lp1/system.cpu.load[all,avg15])>0",
      "description": "Load average is too high",
      "url": "",
      "status": "0",
      "value": "1",
      "priority": "3",
      "lastchange": "1686652254",
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
          "lastvalue": "10.96"
        },
        {
          "itemid": "45594",
          "name": "Load average (1m avg)",
          "key_": "system.cpu.load[all,avg1]",
          "lastvalue": "12.01"
        },
        {
          "itemid": "45595",
          "name": "Load average (5m avg)",
          "key_": "system.cpu.load[all,avg5]",
          "lastvalue": "10.92"
        },
        {
          "itemid": "45600",
          "name": "Number of CPUs",
          "key_": "system.cpu.num",
          "lastvalue": "4"
        }
      ]
    },
    "32914": {
      "triggerid": "32914",
      "expression": "last(/grf-app01-lp1/system.sw.os,#1)<>last(/grf-app01-lp1/system.sw.os,#2) and length(last(/grf-app01-lp1/system.sw.os))>0",
      "description": "Operating system description has changed",
      "url": "",
      "status": "0",
      "value": "0",
      "priority": "1",
      "lastchange": "1686609098",
      "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
      "error": "",
      "templateid": "22373",
      "type": "0",
      "state": "0",
      "flags": "0",
      "recovery_mode": "0",
      "recovery_expression": "",
      "correlation_mode": "0",
      "correlation_tag": "",
      "manual_close": "1",
      "opdata": "",
      "event_name": "",
      "uuid": "",
      "groups": [
        {
          "groupid": "48",
          "name": "DC_NAURYZBAY_PROD"
        }
      ],
      "hosts": [
        {
          "hostid": "10612",
          "name": "grf-app01-lp1",
          "host": "grf-app01-lp1",
          "maintenance_status": "0",
          "proxy_hostid": "10559",
          "description": ""
        }
      ],
      "items": [
        {
          "itemid": "70298",
          "name": "Operating system",
          "key_": "system.sw.os",
          "lastvalue": "Linux version 4.18.0-477.13.1.el8_8.x86_64 (mockbuild@x86-vm-08.build.eng.bos.redhat.com) (gcc version 8.5.0 20210514 (Red Hat 8.5.0-18) (GCC)) #1 SMP Thu May 18 10:27:05 EDT 2023"
        }
      ]
    },
    "33033": {
      "triggerid": "33033",
      "expression": "last(/grf-app02-lp2/system.sw.os,#1)<>last(/grf-app02-lp2/system.sw.os,#2) and length(last(/grf-app02-lp2/system.sw.os))>0",
      "description": "Operating system description has changed",
      "url": "",
      "status": "0",
      "value": "0",
      "priority": "1",
      "lastchange": "1686627298",
      "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
      "error": "",
      "templateid": "22373",
      "type": "0",
      "state": "0",
      "flags": "0",
      "recovery_mode": "0",
      "recovery_expression": "",
      "correlation_mode": "0",
      "correlation_tag": "",
      "manual_close": "1",
      "opdata": "",
      "event_name": "",
      "uuid": "",
      "groups": [
        {
          "groupid": "49",
          "name": "DC_KUNAEVA_PROD"
        }
      ],
      "hosts": [
        {
          "hostid": "10613",
          "name": "grf-app02-lp2",
          "host": "grf-app02-lp2",
          "maintenance_status": "0",
          "proxy_hostid": "10560",
          "description": ""
        }
      ],
      "items": [
        {
          "itemid": "70498",
          "name": "Operating system",
          "key_": "system.sw.os",
          "lastvalue": "Linux version 4.18.0-477.13.1.el8_8.x86_64 (mockbuild@x86-vm-08.build.eng.bos.redhat.com) (gcc version 8.5.0 20210514 (Red Hat 8.5.0-18) (GCC)) #1 SMP Thu May 18 10:27:05 EDT 2023"
        }
      ]
    },
    "61675": {
      "triggerid": "61675",
      "expression": "last(/kzlappdynest02/system.sw.os,#1)<>last(/kzlappdynest02/system.sw.os,#2) and length(last(/kzlappdynest02/system.sw.os))>0",
      "description": "Operating system description has changed",
      "url": "",
      "status": "0",
      "value": "0",
      "priority": "1",
      "lastchange": "1686610330",
      "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
      "error": "",
      "templateid": "53477",
      "type": "0",
      "state": "0",
      "flags": "0",
      "recovery_mode": "0",
      "recovery_expression": "",
      "correlation_mode": "0",
      "correlation_tag": "",
      "manual_close": "1",
      "opdata": "",
      "event_name": "",
      "uuid": "",
      "groups": [
        {
          "groupid": "52",
          "name": "DC_NAURYZBAY_DEV_TEST"
        }
      ],
      "hosts": [
        {
          "hostid": "10606",
          "name": "kzlappdynest02",
          "host": "kzlappdynest02",
          "maintenance_status": "0",
          "proxy_hostid": "10565",
          "description": ""
        }
      ],
      "items": [
        {
          "itemid": "136330",
          "name": "Operating system",
          "key_": "system.sw.os",
          "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023"
        }
      ]
    }
},
  "id": 2968739688375807000
}


public void triggerGet(String auth) throws URISyntaxException, KeyStoreException, NoSuchAlgorithmException, KeyManagementException {
        Random random = new Random();
        Long id = random.nextLong();
        while (id == Long.MIN_VALUE) {
            id = random.nextLong();
        }
        id = Math.abs(id);

        RestTemplate restTemplate = restTemplate();

        URI uri = new URI("https://zabbixapp.eub.kz/api_jsonrpc.php");

        HttpHeaders headers = new HttpHeaders();
        headers.set("Content-Type", "application/json-rpc");

        JSONObject body = new JSONObject();
        body.put("jsonrpc", "2.0");
        body.put("method", "trigger.get");

        JSONObject params = new JSONObject();
        params.put("output", "extend");

        List<String> triggerIdList = Arrays.asList("121082", "73303", "96874", "96878", "96877", "96876",
                "96875", "96873", "96872", "96871", "96870", "96869", "96924", "96923", "96913", "96912", "96911",
                "96910", "96909", "96908", "96907", "96906", "96905", "96904", "96903", "96902", "96901", "96900",
                "96899", "96898", "96897", "96896", "96895", "96894", "96893", "96892", "96891", "96890", "96889",
                "96888", "96887", "96886", "96885", "96884", "96883", "96882", "96881", "96880", "96879", "96754",
                "96922", "96921", "96920", "96919", "96918", "96917", "96963", "96916", "96915", "96914", "126961",
                "23236", "71594", "83401", "66315", "128157", "93302", "77804", "86980", "81915", "80473", "84849",
                "69336", "69334", "33033", "127777", "117490", "81925", "96520", "119452", "62963", "62940", "62848",
                "63929", "61675");
        JSONArray triggerIds = new JSONArray();
        triggerIds.addAll(triggerIdList);

        params.put("triggerids", triggerIds);
        params.put("expandDescription", true);
        params.put("expandData", true);
        params.put("expandComment", true);
        params.put("expandExpression", true);
        params.put("monitored", true);
        params.put("skipDependent", true);

        List<String> selectGroupList = Arrays.asList("name", "groupid");
        JSONArray selectGroups = new JSONArray();
        selectGroups.addAll(selectGroupList);

        params.put("selectGroups", selectGroups);

        List<String> selectHostList = Arrays.asList("hostid", "name", "host", "maintenance_status", "proxy_hostid", "description");
        JSONArray selectHosts = new JSONArray();
        selectHosts.addAll(selectHostList);

        params.put("selectHosts", selectHosts);

        List<String> selectItemList = Arrays.asList("itemid", "name", "key_", "lastvalue");
        JSONArray selectItems = new JSONArray();
        selectItems.addAll(selectItemList);

        params.put("selectItems", selectItems);

        params.put("preservekeys", "1");

        body.put("params", params);
        body.put("id", id);
        body.put("auth", auth);

        HttpEntity<String> entity = new HttpEntity<>(body.toString(), headers);

        ResponseEntity<String> response = restTemplate.exchange(uri, HttpMethod.POST, entity, String.class);

        String responseBody = response.getBody();
        System.out.println(responseBody);
    }

