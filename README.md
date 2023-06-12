# hello-world
Just my first repository


public void zabbixAuth() throws URISyntaxException, KeyStoreException, NoSuchAlgorithmException, KeyManagementException {
        Random random = new Random();
        Long id = random.nextLong();
        while (id == Long.MIN_VALUE){
            id = random.nextLong();
        }
        id = Math.abs(id);

        RestTemplate restTemplate = restTemplate();

        URI uri = new URI("https://zabbixapp.eub.kz/api_jsonrpc.php");

        HttpHeaders headers = new HttpHeaders();
        headers.set("Content-Type", "application/json-rpc");

        JSONObject body = new JSONObject();
        body.put("jsonrpc", "2.0");
        body.put("method", "user.login");

        JSONObject params = new JSONObject();
        params.put("user", "s-jmix-hq");
        params.put("password", "MR9ME79TAOx97ycW8JnB5h5V");

        body.put("params", params);
        body.put("id", id);
        body.put("auth", null);

        HttpEntity<String> entity = new HttpEntity<>(body.toString(), headers);

        ResponseEntity<String> response = restTemplate.exchange(uri, HttpMethod.POST, entity, String.class);

        String responseBody = response.getBody();
        JsonObject jsonObject = JsonParser.parseString(responseBody).getAsJsonObject();
        auth = jsonObject.get("result").getAsString();
    }


{
  "request": {
    "url": "api/datasources/13/resources/zabbix-api",
    "method": "POST",
    "hideFromInspector": false,
    "data": {
      "datasourceId": 13,
      "method": "trigger.get",
      "params": {
        "output": "extend",
        "triggerids": [
          "121082",
          "73303",
          "96874",
          "96878",
          "96877",
          "96876",
          "96875",
          "96873",
          "96872",
          "96871",
          "96870",
          "96869",
          "96924",
          "96923",
          "96913",
          "96912",
          "96911",
          "96910",
          "96909",
          "96908",
          "96907",
          "96906",
          "96905",
          "96904",
          "96903",
          "96902",
          "96901",
          "96900",
          "96899",
          "96898",
          "96897",
          "96896",
          "96895",
          "96894",
          "96893",
          "96892",
          "96891",
          "96890",
          "96889",
          "96888",
          "96887",
          "96886",
          "96885",
          "96884",
          "96883",
          "96882",
          "96881",
          "96880",
          "96879",
          "96754",
          "96922",
          "96921",
          "96920",
          "96919",
          "96918",
          "96917",
          "96963",
          "96916",
          "96915",
          "96914",
          "126961",
          "23236",
          "71594",
          "83401",
          "66315",
          "128157",
          "93302",
          "77804",
          "86980",
          "81915",
          "80473",
          "84849",
          "69336",
          "69334",
          "33033",
          "127777",
          "117490",
          "81925",
          "96520",
          "119452",
          "62963",
          "62940",
          "62848",
          "63929",
          "61675",
          "63538",
          "32914",
          "113322",
          "113276",
          "63331",
          "63308",
          "63285",
          "63239",
          "119679",
          "63216",
          "113092",
          "119656",
          "119633",
          "64274",
          "63147",
          "64251",
          "119587",
          "63124",
          "63101",
          "114884",
          "63078",
          "114861",
          "125953",
          "61905",
          "63009",
          "61859",
          "99946",
          "97761",
          "71595",
          "96239",
          "96430",
          "96240",
          "124410",
          "71569",
          "71596",
          "128996",
          "86783",
          "116351",
          "116350",
          "129428",
          "129205",
          "69468",
          "127312",
          "127308",
          "127092",
          "129795",
          "129208",
          "129201",
          "129181",
          "128976",
          "128974",
          "127879",
          "127872",
          "127871",
          "89477",
          "90506",
          "125991",
          "77848",
          "96571",
          "71562",
          "80299",
          "97289",
          "75215",
          "86114",
          "125147",
          "125107",
          "98812",
          "99082",
          "116181",
          "90918",
          "98777",
          "81393",
          "81392",
          "124785",
          "81391",
          "81415",
          "122218",
          "121405",
          "121650",
          "121350",
          "121214",
          "123970",
          "122270",
          "124115",
          "118227",
          "118020",
          "81928",
          "116821",
          "116191",
          "116190",
          "112376",
          "112537",
          "112283",
          "101727",
          "100014",
          "108738",
          "110266",
          "110215",
          "108552",
          "108551",
          "108545",
          "108544",
          "108543",
          "108580",
          "108579",
          "108578",
          "108279",
          "104233",
          "96316",
          "102640",
          "102641",
          "102584",
          "102590",
          "101716",
          "101717",
          "88477",
          "101570",
          "101433",
          "101198",
          "93273",
          "73627",
          "93230",
          "100827",
          "100828",
          "100817",
          "100818",
          "100812",
          "100811",
          "100801",
          "100802",
          "100799",
          "100800",
          "100795",
          "100796",
          "40956",
          "100532",
          "99360",
          "99220",
          "100080",
          "99174",
          "99828",
          "99268",
          "99140",
          "99794",
          "100058",
          "99568",
          "99734",
          "98916",
          "76361",
          "98622",
          "63357",
          "88631",
          "86660",
          "98122",
          "98121",
          "97303",
          "97311",
          "96748",
          "96100",
          "96572",
          "96196",
          "90627",
          "90972",
          "90966",
          "90893",
          "86981",
          "41323",
          "77648",
          "78443",
          "85223",
          "37261",
          "37294",
          "63174",
          "89036",
          "82785",
          "82873",
          "36751",
          "78896",
          "74292",
          "69421",
          "69157",
          "69311",
          "67987",
          "40955",
          "41287",
          "41263",
          "30467",
          "31564",
          "30165",
          "30619",
          "30941",
          "30620"
        ],
        "expandDescription": true,
        "expandData": true,
        "expandComment": true,
        "expandExpression": true,
        "monitored": true,
        "skipDependent": true,
        "selectGroups": [
          "name",
          "groupid"
        ],
        "selectHosts": [
          "hostid",
          "name",
          "host",
          "maintenance_status",
          "proxy_hostid",
          "description"
        ],
        "selectItems": [
          "itemid",
          "name",
          "key_",
          "lastvalue"
        ],
        "preservekeys": "1"
      }
    }
  },
  "response": {
    "result": {
      "23236": {
        "comments": "Per CPU load average is too high. Your system may be slow to respond.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Load average is too high",
        "error": "",
        "event_name": "Load average is too high (per CPU load over {$LOAD_AVG_PER_CPU.MAX.WARN} for 5m)",
        "expression": "min(/zbx-app01-lp1/system.cpu.load[all,avg1],5m)/last(/zbx-app01-lp1/system.cpu.num)>1.5\r\nand last(/zbx-app01-lp1/system.cpu.load[all,avg5])>0\r\nand last(/zbx-app01-lp1/system.cpu.load[all,avg15])>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "4",
            "name": "Zabbix servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "zbx-app01-lp1",
            "hostid": "10570",
            "maintenance_status": "0",
            "name": "zbx-app01-lp1",
            "proxy_hostid": "0"
          }
        ],
        "items": [
          {
            "itemid": "45593",
            "key_": "system.cpu.load[all,avg15]",
            "lastvalue": "8.57",
            "name": "Load average (15m avg)"
          },
          {
            "itemid": "45594",
            "key_": "system.cpu.load[all,avg1]",
            "lastvalue": "9.27",
            "name": "Load average (1m avg)"
          },
          {
            "itemid": "45595",
            "key_": "system.cpu.load[all,avg5]",
            "lastvalue": "9.84",
            "name": "Load average (5m avg)"
          },
          {
            "itemid": "45600",
            "key_": "system.cpu.num",
            "lastvalue": "4",
            "name": "Number of CPUs"
          }
        ],
        "lastchange": "1686561715",
        "manual_close": "0",
        "opdata": "Load averages(1m 5m 15m): ({ITEM.LASTVALUE1} {ITEM.LASTVALUE3} {ITEM.LASTVALUE4}), # of CPUs: {ITEM.LASTVALUE2}",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22381",
        "triggerid": "23236",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "32914": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/grf-app01-lp1/system.sw.os,#1)<>last(/grf-app01-lp1/system.sw.os,#2) and length(last(/grf-app01-lp1/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "grf-app01-lp1",
            "hostid": "10612",
            "maintenance_status": "0",
            "name": "grf-app01-lp1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "70298",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 4.18.0-477.13.1.el8_8.x86_64 (mockbuild@x86-vm-08.build.eng.bos.redhat.com) (gcc version 8.5.0 20210514 (Red Hat 8.5.0-18) (GCC)) #1 SMP Thu May 18 10:27:05 EDT 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686522698",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22373",
        "triggerid": "32914",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "33033": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/grf-app02-lp2/system.sw.os,#1)<>last(/grf-app02-lp2/system.sw.os,#2) and length(last(/grf-app02-lp2/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "grf-app02-lp2",
            "hostid": "10613",
            "maintenance_status": "0",
            "name": "grf-app02-lp2",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "70498",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 4.18.0-477.13.1.el8_8.x86_64 (mockbuild@x86-vm-08.build.eng.bos.redhat.com) (gcc version 8.5.0 20210514 (Red Hat 8.5.0-18) (GCC)) #1 SMP Thu May 18 10:27:05 EDT 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686540898",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22373",
        "triggerid": "33033",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "36751": {
        "comments": "SNMP is not available for polling. Please check device connectivity and SNMP settings.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "No SNMP data collection",
        "error": "",
        "event_name": "",
        "expression": "max(/UPS_FILIAL_24_SEMEY/zabbix[host,snmp,available],5m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "47",
            "name": "FILIAL_24_Semey"
          },
          {
            "groupid": "60",
            "name": "DEVICES_UPS_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "Newave UPS System Conceptpower",
            "host": "UPS_FILIAL_24_SEMEY",
            "hostid": "10682",
            "maintenance_status": "0",
            "name": "UPS_FILIAL_24_SEMEY",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "77480",
            "key_": "zabbix[host,snmp,available]",
            "lastvalue": "0",
            "name": "SNMP agent availability"
          }
        ],
        "lastchange": "1683134720",
        "manual_close": "0",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "18496",
        "triggerid": "36751",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "40956": {
        "comments": "",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Sensor NB:1 19 :: Temperature > Max Threshold",
        "error": "",
        "event_name": "",
        "expression": "(last(/SENSOR_FILIAL_7_KOSTANAY/apc.enviro.sensor.module.temperature.value.[\"0.1\"])>=last(/SENSOR_FILIAL_7_KOSTANAY/apc.enviro.sensor.module.temperature.threshold.max.[\"0.1\"]))",
        "flags": "4",
        "groups": [
          {
            "groupid": "33",
            "name": "FILIAL_07_Kostanay"
          },
          {
            "groupid": "64",
            "name": "DEVICES_SENSOR_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "APC NetBotz Rack Monitor 250",
            "host": "SENSOR_FILIAL_7_KOSTANAY",
            "hostid": "10664",
            "maintenance_status": "0",
            "name": "SENSOR_FILIAL_7_KOSTANAY",
            "proxy_hostid": "11046",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "87801",
            "key_": "apc.enviro.sensor.module.temperature.value.[\"0.1\"]",
            "lastvalue": "19",
            "name": "Sensor NB:1 Temperature"
          },
          {
            "itemid": "87803",
            "key_": "apc.enviro.sensor.module.temperature.threshold.hysteresis.[\"0.1\"]",
            "lastvalue": "5",
            "name": "Sensor NB:1 Temperature: Threshold - Hysteresis"
          },
          {
            "itemid": "87809",
            "key_": "apc.enviro.sensor.module.temperature.threshold.max.[\"0.1\"]",
            "lastvalue": "22",
            "name": "Sensor NB:1 Temperature: Threshold - Max"
          }
        ],
        "lastchange": "1685776159",
        "manual_close": "1",
        "opdata": "",
        "priority": "5",
        "recovery_expression": "(last(/SENSOR_FILIAL_7_KOSTANAY/apc.enviro.sensor.module.temperature.value.[\"0.1\"])<=(last(/SENSOR_FILIAL_7_KOSTANAY/apc.enviro.sensor.module.temperature.threshold.max.[\"0.1\"])-last(/SENSOR_FILIAL_7_KOSTANAY/apc.enviro.sensor.module.temperature.threshold.hysteresis.[\"0.1\"])))",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "40956",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "41323": {
        "comments": "Last value: Down (0).\r\nLast three attempts returned timeout.  Please check device connectivity.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Unavailable by ICMP ping",
        "error": "",
        "event_name": "",
        "expression": "max(/UPS_FILIAL_24_SEMEY/icmpping,#3)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "47",
            "name": "FILIAL_24_Semey"
          },
          {
            "groupid": "60",
            "name": "DEVICES_UPS_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "Newave UPS System Conceptpower",
            "host": "UPS_FILIAL_24_SEMEY",
            "hostid": "10682",
            "maintenance_status": "0",
            "name": "UPS_FILIAL_24_SEMEY",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "88536",
            "key_": "icmpping",
            "lastvalue": "0",
            "name": "ICMP ping"
          }
        ],
        "lastchange": "1683892027",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "14251",
        "triggerid": "41323",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "61675": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlappdynest02/system.sw.os,#1)<>last(/kzlappdynest02/system.sw.os,#2) and length(last(/kzlappdynest02/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappdynest02",
            "hostid": "10606",
            "maintenance_status": "0",
            "name": "kzlappdynest02",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "136330",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686523930",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "61675",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "61859": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlappnsdt01/system.sw.os,#1)<>last(/kzlappnsdt01/system.sw.os,#2) and length(last(/kzlappnsdt01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "53",
            "name": "DC_KUNAEV_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappnsdt01",
            "hostid": "10928",
            "maintenance_status": "0",
            "name": "kzlappnsdt01",
            "proxy_hostid": "10566",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "136922",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686520922",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "61859",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "61905": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlavcallt01/system.sw.os,#1)<>last(/kzlavcallt01/system.sw.os,#2) and length(last(/kzlavcallt01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "23",
            "name": "Telephony"
          },
          {
            "groupid": "53",
            "name": "DC_KUNAEV_DEV_TEST"
          },
          {
            "groupid": "107",
            "name": "SYSTEM_CRM"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlavcallt01",
            "hostid": "10931",
            "maintenance_status": "0",
            "name": "kzlavcallt01",
            "proxy_hostid": "10566",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "137070",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521070",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "61905",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "62848": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/KZLRUBILIXT01/system.sw.os,#1)<>last(/KZLRUBILIXT01/system.sw.os,#2) and length(last(/KZLRUBILIXT01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZLRUBILIXT01",
            "hostid": "10863",
            "maintenance_status": "0",
            "name": "KZLRUBILIXT01",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "140104",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686524104",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "62848",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "62940": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlapcorrt01/system.sw.os,#1)<>last(/kzlapcorrt01/system.sw.os,#2) and length(last(/kzlapcorrt01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlapcorrt01",
            "hostid": "10875",
            "maintenance_status": "0",
            "name": "kzlapcorrt01",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "140400",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686524400",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "62940",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "62963": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlappextcasht01/system.sw.os,#1)<>last(/kzlappextcasht01/system.sw.os,#2) and length(last(/kzlappextcasht01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappextcasht01",
            "hostid": "10876",
            "maintenance_status": "0",
            "name": "kzlappextcasht01",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "140474",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686524474",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "62963",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63009": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlappfisd02/system.sw.os,#1)<>last(/kzlappfisd02/system.sw.os,#2) and length(last(/kzlappfisd02/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappfisd02",
            "hostid": "10881",
            "maintenance_status": "0",
            "name": "kzlappfisd02",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "140622",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 4.18.0-477.13.1.el8_8.x86_64 (mockbuild@x86-vm-08.build.eng.bos.redhat.com) (gcc version 8.5.0 20210514 (Red Hat 8.5.0-18) (GCC)) #1 SMP Thu May 18 10:27:05 EDT 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521022",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "63009",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63078": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlappsoftcolfpd02/system.sw.os,#1)<>last(/kzlappsoftcolfpd02/system.sw.os,#2) and length(last(/kzlappsoftcolfpd02/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappsoftcolfpd02",
            "hostid": "10892",
            "maintenance_status": "0",
            "name": "kzlappsoftcolfpd02",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "140844",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521244",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "63078",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63101": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlappsasminert01/system.sw.os,#1)<>last(/kzlappsasminert01/system.sw.os,#2) and length(last(/kzlappsasminert01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappsasminert01",
            "hostid": "10882",
            "maintenance_status": "0",
            "name": "kzlappsasminert01",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "140918",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521318",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "63101",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63124": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlsasct01/system.sw.os,#1)<>last(/kzlsasct01/system.sw.os,#2) and length(last(/kzlsasct01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlsasct01",
            "hostid": "10889",
            "maintenance_status": "0",
            "name": "kzlsasct01",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "140992",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521392",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "63124",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63147": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlappsasrtdmt01/system.sw.os,#1)<>last(/kzlappsasrtdmt01/system.sw.os,#2) and length(last(/kzlappsasrtdmt01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappsasrtdmt01",
            "hostid": "10895",
            "maintenance_status": "0",
            "name": "kzlappsasrtdmt01",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "141066",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 4.18.0-477.13.1.el8_8.x86_64 (mockbuild@x86-vm-08.build.eng.bos.redhat.com) (gcc version 8.5.0 20210514 (Red Hat 8.5.0-18) (GCC)) #1 SMP Thu May 18 10:27:05 EDT 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521466",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "63147",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63174": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/kzlapib05/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlapib05",
            "hostid": "10890",
            "maintenance_status": "0",
            "name": "kzlapib05",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "141155",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1683497075",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53481",
        "triggerid": "63174",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63216": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlappsoftcolfpd01/system.sw.os,#1)<>last(/kzlappsoftcolfpd01/system.sw.os,#2) and length(last(/kzlappsoftcolfpd01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappsoftcolfpd01",
            "hostid": "10891",
            "maintenance_status": "0",
            "name": "kzlappsoftcolfpd01",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "141288",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521688",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "63216",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63239": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlappsoftcolt01/system.sw.os,#1)<>last(/kzlappsoftcolt01/system.sw.os,#2) and length(last(/kzlappsoftcolt01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappsoftcolt01",
            "hostid": "10883",
            "maintenance_status": "0",
            "name": "kzlappsoftcolt01",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "141362",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521762",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "63239",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63285": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlapib06/system.sw.os,#1)<>last(/kzlapib06/system.sw.os,#2) and length(last(/kzlapib06/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlapib06",
            "hostid": "10885",
            "maintenance_status": "0",
            "name": "kzlapib06",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "141510",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521910",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "63285",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63308": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlappbpmd01/system.sw.os,#1)<>last(/kzlappbpmd01/system.sw.os,#2) and length(last(/kzlappbpmd01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappbpmd01",
            "hostid": "10886",
            "maintenance_status": "0",
            "name": "kzlappbpmd01",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "141584",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521984",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "63308",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63331": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/omlab-dev.eub.kz/system.sw.os,#1)<>last(/omlab-dev.eub.kz/system.sw.os,#2) and length(last(/omlab-dev.eub.kz/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "omlab-dev.eub.kz",
            "hostid": "10887",
            "maintenance_status": "0",
            "name": "omlab-dev.eub.kz",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "141658",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686522058",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "63331",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63357": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/kzlappbpm12ct.eub.kz/vm.memory.utilization,5m)>98",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappbpm12ct.eub.kz",
            "hostid": "10888",
            "maintenance_status": "0",
            "name": "kzlappbpm12ct.eub.kz",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "141750",
            "key_": "vm.memory.utilization",
            "lastvalue": "99.567686",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1685444443",
        "manual_close": "0",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53480",
        "triggerid": "63357",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63538": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlsasmmt01/system.sw.os,#1)<>last(/kzlsasmmt01/system.sw.os,#2) and length(last(/kzlsasmmt01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlsasmmt01",
            "hostid": "10955",
            "maintenance_status": "0",
            "name": "kzlsasmmt01",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "142324",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686522724",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "63538",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "63929": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/sbs-app02-lt2/system.sw.os,#1)<>last(/sbs-app02-lt2/system.sw.os,#2) and length(last(/sbs-app02-lt2/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "53",
            "name": "DC_KUNAEV_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "sbs-app02-lt2",
            "hostid": "10936",
            "maintenance_status": "0",
            "name": "sbs-app02-lt2",
            "proxy_hostid": "10566",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "143590",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 4.18.0-477.13.1.el8_8.x86_64 (mockbuild@x86-vm-08.build.eng.bos.redhat.com) (gcc version 8.5.0 20210514 (Red Hat 8.5.0-18) (GCC)) #1 SMP Thu May 18 10:27:05 EDT 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686523990",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "63929",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "64251": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/sbs-app01-lt1/system.sw.os,#1)<>last(/sbs-app01-lt1/system.sw.os,#2) and length(last(/sbs-app01-lt1/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "sbs-app01-lt1",
            "hostid": "10894",
            "maintenance_status": "0",
            "name": "sbs-app01-lt1",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "144626",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 4.18.0-477.13.1.el8_8.x86_64 (mockbuild@x86-vm-08.build.eng.bos.redhat.com) (gcc version 8.5.0 20210514 (Red Hat 8.5.0-18) (GCC)) #1 SMP Thu May 18 10:27:05 EDT 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521426",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "64251",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "64274": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/sbs-web01-lt1/system.sw.os,#1)<>last(/sbs-web01-lt1/system.sw.os,#2) and length(last(/sbs-web01-lt1/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "sbs-web01-lt1",
            "hostid": "10896",
            "maintenance_status": "0",
            "name": "sbs-web01-lt1",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "144700",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 4.18.0-477.13.1.el8_8.x86_64 (mockbuild@x86-vm-08.build.eng.bos.redhat.com) (gcc version 8.5.0 20210514 (Red Hat 8.5.0-18) (GCC)) #1 SMP Thu May 18 10:27:05 EDT 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521500",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53477",
        "triggerid": "64274",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "66315": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/TMP-APP04-WE2/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "5",
            "name": "Discovered hosts"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "53",
            "name": "DC_KUNAEV_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "TMP-APP04-WE2",
            "hostid": "10961",
            "maintenance_status": "0",
            "name": "TMP-APP04-WE2",
            "proxy_hostid": "10566",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "154418",
            "key_": "vm.memory.util",
            "lastvalue": "93.95034622154141",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686561038",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "66315",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "67987": {
        "comments": "Please check the fan unit",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Fan  1: Fan is in critical state",
        "error": "",
        "event_name": "",
        "expression": "count(/GATEWAY_FILIAL_3_AKTOBE/sensor.fan.status[ciscoEnvMonFanState.1],#1,\"eq\",\"3\")=1 or count(/GATEWAY_FILIAL_3_AKTOBE/sensor.fan.status[ciscoEnvMonFanState.1],#1,\"eq\",\"4\")=1",
        "flags": "4",
        "groups": [
          {
            "groupid": "29",
            "name": "FILIAL_03_Aktobe"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_3_AKTOBE",
            "hostid": "10989",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_3_AKTOBE",
            "proxy_hostid": "10963",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "159930",
            "key_": "sensor.fan.status[ciscoEnvMonFanState.1]",
            "lastvalue": "4",
            "name": "Fan  1: Fan status"
          }
        ],
        "lastchange": "1682677499",
        "manual_close": "0",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "67987",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "69334": {
        "comments": "The device uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Host has been restarted",
        "error": "",
        "event_name": "Host has been restarted (uptime < 10m)",
        "expression": "last(/KZF04WCHECKIN03/system.uptime)<10m",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "30",
            "name": "FILIAL_04_Karaganda"
          },
          {
            "groupid": "72",
            "name": "DEVICES_SUO_CHECKIN_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF04WCHECKIN03",
            "hostid": "11008",
            "maintenance_status": "0",
            "name": "KZF04WCHECKIN03",
            "proxy_hostid": "10993",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "163554",
            "key_": "system.uptime",
            "lastvalue": "529",
            "name": "Uptime"
          }
        ],
        "lastchange": "1686546843",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23208",
        "triggerid": "69334",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "69336": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/KZF04WCHECKIN03/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "30",
            "name": "FILIAL_04_Karaganda"
          },
          {
            "groupid": "72",
            "name": "DEVICES_SUO_CHECKIN_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF04WCHECKIN03",
            "hostid": "11008",
            "maintenance_status": "0",
            "name": "KZF04WCHECKIN03",
            "proxy_hostid": "10993",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "163558",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686547558",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23210",
        "triggerid": "69336",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "69468": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/KZF04WSUO0416/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "30",
            "name": "FILIAL_04_Karaganda"
          },
          {
            "groupid": "73",
            "name": "DEVICES_SUO_LOCALSERVER_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF04WSUO0416",
            "hostid": "11018",
            "maintenance_status": "0",
            "name": "KZF04WSUO0416",
            "proxy_hostid": "10993",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "163948",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686319168",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23210",
        "triggerid": "69468",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "71562": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu105122(Astana to RKO-512 (STB)): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.71])=2 and (last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.71],#1)<>last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.71],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "31",
            "name": "FILIAL_05_Astana"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_5_ASTANA",
            "hostid": "11042",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_5_ASTANA",
            "proxy_hostid": "11021",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "169437",
            "key_": "net.if.status[ifOperStatus.71]",
            "lastvalue": "2",
            "name": "Interface Tu105122(Astana to RKO-512 (STB)): Operational status"
          }
        ],
        "lastchange": "1686267290",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.71])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "71562",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "71569": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu20551(Astana to ATM-05023): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.93])=2 and (last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.93],#1)<>last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.93],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "31",
            "name": "FILIAL_05_Astana"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_5_ASTANA",
            "hostid": "11042",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_5_ASTANA",
            "proxy_hostid": "11021",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "169444",
            "key_": "net.if.status[ifOperStatus.93]",
            "lastvalue": "2",
            "name": "Interface Tu20551(Astana to ATM-05023): Operational status"
          }
        ],
        "lastchange": "1686408350",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.93])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "71569",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "71594": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu50504(Astana to RKO-504 (STB)): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.124])=2 and (last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.124],#1)<>last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.124],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "31",
            "name": "FILIAL_05_Astana"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_5_ASTANA",
            "hostid": "11042",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_5_ASTANA",
            "proxy_hostid": "11021",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "169469",
            "key_": "net.if.status[ifOperStatus.124]",
            "lastvalue": "2",
            "name": "Interface Tu50504(Astana to RKO-504 (STB)): Operational status"
          }
        ],
        "lastchange": "1686561650",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.124])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "71594",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "71595": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu50505(Astana to RKO-505 (STB)): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.125])=2 and (last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.125],#1)<>last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.125],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "31",
            "name": "FILIAL_05_Astana"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_5_ASTANA",
            "hostid": "11042",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_5_ASTANA",
            "proxy_hostid": "11021",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "169470",
            "key_": "net.if.status[ifOperStatus.125]",
            "lastvalue": "2",
            "name": "Interface Tu50505(Astana to RKO-505 (STB)): Operational status"
          }
        ],
        "lastchange": "1686497030",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.125])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "71595",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "71596": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu50506(Astana to RKO-506 (STB)): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.126])=2 and (last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.126],#1)<>last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.126],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "31",
            "name": "FILIAL_05_Astana"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_5_ASTANA",
            "hostid": "11042",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_5_ASTANA",
            "proxy_hostid": "11021",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "169471",
            "key_": "net.if.status[ifOperStatus.126]",
            "lastvalue": "2",
            "name": "Interface Tu50506(Astana to RKO-506 (STB)): Operational status"
          }
        ],
        "lastchange": "1686378230",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_5_ASTANA/net.if.status[ifOperStatus.126])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "71596",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "73303": {
        "comments": "The device uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Host has been restarted",
        "error": "",
        "event_name": "Host has been restarted (uptime < 10m)",
        "expression": "last(/KZF02WCHECKIN13/system.uptime)<10m",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "33",
            "name": "FILIAL_07_Kostanay"
          },
          {
            "groupid": "72",
            "name": "DEVICES_SUO_CHECKIN_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF02WCHECKIN13",
            "hostid": "11079",
            "maintenance_status": "0",
            "name": "KZF02WCHECKIN13",
            "proxy_hostid": "11046",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "174566",
            "key_": "system.uptime",
            "lastvalue": "126",
            "name": "Uptime"
          }
        ],
        "lastchange": "1686562376",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23208",
        "triggerid": "73303",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "74292": {
        "comments": "Please check the fan unit",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Fan  1: Fan is in critical state",
        "error": "",
        "event_name": "",
        "expression": "count(/GATEWAY_FILIAL_7_RUDNYI/sensor.fan.status[ciscoEnvMonFanState.1],#1,\"eq\",\"3\")=1 or count(/GATEWAY_FILIAL_7_RUDNYI/sensor.fan.status[ciscoEnvMonFanState.1],#1,\"eq\",\"4\")=1",
        "flags": "4",
        "groups": [
          {
            "groupid": "33",
            "name": "FILIAL_07_Kostanay"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_7_RUDNYI",
            "hostid": "11082",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_7_RUDNYI",
            "proxy_hostid": "11046",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "177064",
            "key_": "sensor.fan.status[ciscoEnvMonFanState.1]",
            "lastvalue": "4",
            "name": "Fan  1: Fan status"
          }
        ],
        "lastchange": "1683023549",
        "manual_close": "0",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "74292",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "75215": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu20401(Karaganda to ATM-04006): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_4_KARAGANDA/net.if.status[ifOperStatus.54])=2 and (last(/GATEWAY_FILIAL_4_KARAGANDA/net.if.status[ifOperStatus.54],#1)<>last(/GATEWAY_FILIAL_4_KARAGANDA/net.if.status[ifOperStatus.54],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "30",
            "name": "FILIAL_04_Karaganda"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_4_KARAGANDA",
            "hostid": "11086",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_4_KARAGANDA",
            "proxy_hostid": "10993",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "178866",
            "key_": "net.if.status[ifOperStatus.54]",
            "lastvalue": "2",
            "name": "Interface Tu20401(Karaganda to ATM-04006): Operational status"
          }
        ],
        "lastchange": "1686228333",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_4_KARAGANDA/net.if.status[ifOperStatus.54])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "75215",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "76361": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1\\\"}=1 - user can redefine Context macro to value - 0. That marks this interface as not important.\r\n    No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status is different from Connected(2).\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Intel(R) 82574L Gigabit Network Connection(eth0): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/KZF08WFS6/net.if.status[\"{0E7F1954-192B-4503-9381-505068F7C347}\"])<>2 and (last(/KZF08WFS6/net.if.status[\"{0E7F1954-192B-4503-9381-505068F7C347}\"],#1)<>last(/KZF08WFS6/net.if.status[\"{0E7F1954-192B-4503-9381-505068F7C347}\"],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "34",
            "name": "FILIAL_08_Atyrau"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF08WFS6",
            "hostid": "11104",
            "maintenance_status": "0",
            "name": "KZF08WFS6",
            "proxy_hostid": "11087",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "182151",
            "key_": "net.if.status[\"{0E7F1954-192B-4503-9381-505068F7C347}\"]",
            "lastvalue": "7",
            "name": "Interface Intel(R) 82574L Gigabit Network Connection(eth0): Operational status"
          }
        ],
        "lastchange": "1685642114",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/KZF08WFS6/net.if.status[\"{0E7F1954-192B-4503-9381-505068F7C347}\"])=2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "76361",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "77648": {
        "comments": "The device uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Host has been restarted",
        "error": "Cannot evaluate function last(/KZF09WSUO0904/system.uptime): item is not supported.",
        "event_name": "Host has been restarted (uptime < 10m)",
        "expression": "last(/KZF09WSUO0904/system.uptime)<10m",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "73",
            "name": "DEVICES_SUO_LOCALSERVER_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF09WSUO0904",
            "hostid": "11111",
            "maintenance_status": "0",
            "name": "KZF09WSUO0904",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "185605",
            "key_": "system.uptime",
            "lastvalue": "0",
            "name": "Uptime"
          }
        ],
        "lastchange": "1683863845",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "1",
        "status": "0",
        "templateid": "23208",
        "triggerid": "77648",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "77804": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/KZF09WSUO0908/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "73",
            "name": "DEVICES_SUO_LOCALSERVER_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF09WSUO0908",
            "hostid": "11131",
            "maintenance_status": "0",
            "name": "KZF09WSUO0908",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "186064",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686559024",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23210",
        "triggerid": "77804",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "77848": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/FL09-L-SUO0910/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "73",
            "name": "DEVICES_SUO_LOCALSERVER_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "FL09-L-SUO0910",
            "hostid": "11137",
            "maintenance_status": "0",
            "name": "FL09-L-SUO0910",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "186194",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686288014",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23210",
        "triggerid": "77848",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "78443": {
        "comments": "This trigger might indicate disk 0 C: saturation.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "0 C:: Disk read request responses are too high",
        "error": "Cannot evaluate function min(/KZF09WSUO0904/perf_counter_en[\"\\PhysicalDisk(0 C:)\\Avg. Disk sec/Read\",60],15m): item is not supported.",
        "event_name": "0 C:: Disk read request responses are too high (read > {$VFS.DEV.READ.AWAIT.WARN:\"0 C:\"}s for 15m",
        "expression": "min(/KZF09WSUO0904/perf_counter_en[\"\\PhysicalDisk(0 C:)\\Avg. Disk sec/Read\",60],15m) > 0.02",
        "flags": "4",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "73",
            "name": "DEVICES_SUO_LOCALSERVER_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF09WSUO0904",
            "hostid": "11111",
            "maintenance_status": "0",
            "name": "KZF09WSUO0904",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "187788",
            "key_": "perf_counter_en[\"\\PhysicalDisk(0 C:)\\Avg. Disk sec/Read\",60]",
            "lastvalue": "0",
            "name": "0 C:: Disk read request avg waiting time"
          }
        ],
        "lastchange": "1683861693",
        "manual_close": "0",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "1",
        "status": "0",
        "templateid": "0",
        "triggerid": "78443",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "78896": {
        "comments": "Please check the fan unit",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Fan  1: Fan is in critical state",
        "error": "",
        "event_name": "",
        "expression": "count(/GATEWAY_FILIAL_24_SEMEY/sensor.fan.status[ciscoEnvMonFanState.1],#1,\"eq\",\"3\")=1 or count(/GATEWAY_FILIAL_24_SEMEY/sensor.fan.status[ciscoEnvMonFanState.1],#1,\"eq\",\"4\")=1",
        "flags": "4",
        "groups": [
          {
            "groupid": "47",
            "name": "FILIAL_24_Semey"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_24_SEMEY",
            "hostid": "11140",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_24_SEMEY",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "188733",
            "key_": "sensor.fan.status[ciscoEnvMonFanState.1]",
            "lastvalue": "4",
            "name": "Fan  1: Fan status"
          }
        ],
        "lastchange": "1683116665",
        "manual_close": "0",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "78896",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "80299": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Data1(D:): Disk space is low",
        "error": "",
        "event_name": "Data1(D:): Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"D:\"}%)",
        "expression": "last(/KZF10WFS1/vfs.fs.size[D:,pused])>80 and\r\n((last(/KZF10WFS1/vfs.fs.size[D:,total])-last(/KZF10WFS1/vfs.fs.size[D:,used]))<10G or timeleft(/KZF10WFS1/vfs.fs.size[D:,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "36",
            "name": "FILIAL_10_Taraz"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF10WFS1",
            "hostid": "11144",
            "maintenance_status": "0",
            "name": "KZF10WFS1",
            "proxy_hostid": "11141",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "192435",
            "key_": "vfs.fs.size[D:,pused]",
            "lastvalue": "98.87439",
            "name": "Data1(D:): Space utilization"
          },
          {
            "itemid": "192438",
            "key_": "vfs.fs.size[D:,total]",
            "lastvalue": "513160507392",
            "name": "Data1(D:): Total space"
          },
          {
            "itemid": "192441",
            "key_": "vfs.fs.size[D:,used]",
            "lastvalue": "507384320000",
            "name": "Data1(D:): Used space"
          }
        ],
        "lastchange": "1686257418",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "80299",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "80473": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu21006(Taraz to ATM-10006): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_10_TARAZ/net.if.status[ifOperStatus.26])=2 and (last(/GATEWAY_FILIAL_10_TARAZ/net.if.status[ifOperStatus.26],#1)<>last(/GATEWAY_FILIAL_10_TARAZ/net.if.status[ifOperStatus.26],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "36",
            "name": "FILIAL_10_Taraz"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_10_TARAZ",
            "hostid": "11162",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_10_TARAZ",
            "proxy_hostid": "11141",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "192748",
            "key_": "net.if.status[ifOperStatus.26]",
            "lastvalue": "2",
            "name": "Interface Tu21006(Taraz to ATM-10006): Operational status"
          }
        ],
        "lastchange": "1686554806",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_10_TARAZ/net.if.status[ifOperStatus.26])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "80473",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "81391": {
        "comments": "The device uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Host has been restarted",
        "error": "",
        "event_name": "Host has been restarted (uptime < 10m)",
        "expression": "last(/KZF11WCHECKIN05/system.uptime)<10m",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "37",
            "name": "FILIAL_11_Aktau"
          },
          {
            "groupid": "72",
            "name": "DEVICES_SUO_CHECKIN_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF11WCHECKIN05",
            "hostid": "11170",
            "maintenance_status": "0",
            "name": "KZF11WCHECKIN05",
            "proxy_hostid": "11164",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "195449",
            "key_": "system.uptime",
            "lastvalue": "0",
            "name": "Uptime"
          }
        ],
        "lastchange": "1686133473",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23208",
        "triggerid": "81391",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "81392": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/KZF11WCHECKIN05/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "37",
            "name": "FILIAL_11_Aktau"
          },
          {
            "groupid": "72",
            "name": "DEVICES_SUO_CHECKIN_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF11WCHECKIN05",
            "hostid": "11170",
            "maintenance_status": "0",
            "name": "KZF11WCHECKIN05",
            "proxy_hostid": "11164",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "195433",
            "key_": "vm.memory.util",
            "lastvalue": "90.13076921609073",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686133933",
        "manual_close": "0",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23209",
        "triggerid": "81392",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "81393": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/KZF11WCHECKIN05/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "37",
            "name": "FILIAL_11_Aktau"
          },
          {
            "groupid": "72",
            "name": "DEVICES_SUO_CHECKIN_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF11WCHECKIN05",
            "hostid": "11170",
            "maintenance_status": "0",
            "name": "KZF11WCHECKIN05",
            "proxy_hostid": "11164",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "195453",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686134013",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23210",
        "triggerid": "81393",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "81415": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/KZF11WCHECKIN01/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "37",
            "name": "FILIAL_11_Aktau"
          },
          {
            "groupid": "72",
            "name": "DEVICES_SUO_CHECKIN_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF11WCHECKIN01",
            "hostid": "11174",
            "maintenance_status": "0",
            "name": "KZF11WCHECKIN01",
            "proxy_hostid": "11164",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "195518",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686132518",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23210",
        "triggerid": "81415",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "81915": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu31102(Aktau to IPT-110000E02): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_11_AKTAU/net.if.status[ifOperStatus.46])=2 and (last(/GATEWAY_FILIAL_11_AKTAU/net.if.status[ifOperStatus.46],#1)<>last(/GATEWAY_FILIAL_11_AKTAU/net.if.status[ifOperStatus.46],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "37",
            "name": "FILIAL_11_Aktau"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_11_AKTAU",
            "hostid": "11187",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_11_AKTAU",
            "proxy_hostid": "11164",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "196727",
            "key_": "net.if.status[ifOperStatus.46]",
            "lastvalue": "2",
            "name": "Interface Tu31102(Aktau to IPT-110000E02): Operational status"
          }
        ],
        "lastchange": "1686555736",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_11_AKTAU/net.if.status[ifOperStatus.46])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "81915",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "81925": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu51108(Aktau to RKO-1108 (STB)): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_11_AKTAU/net.if.status[ifOperStatus.57])=2 and (last(/GATEWAY_FILIAL_11_AKTAU/net.if.status[ifOperStatus.57],#1)<>last(/GATEWAY_FILIAL_11_AKTAU/net.if.status[ifOperStatus.57],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "37",
            "name": "FILIAL_11_Aktau"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_11_AKTAU",
            "hostid": "11187",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_11_AKTAU",
            "proxy_hostid": "11164",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "196737",
            "key_": "net.if.status[ifOperStatus.57]",
            "lastvalue": "2",
            "name": "Interface Tu51108(Aktau to RKO-1108 (STB)): Operational status"
          }
        ],
        "lastchange": "1686537730",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_11_AKTAU/net.if.status[ifOperStatus.57])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "81925",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "81928": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu51107(Aktau to RKO-1107 (STB)): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_11_AKTAU/net.if.status[ifOperStatus.60])=2 and (last(/GATEWAY_FILIAL_11_AKTAU/net.if.status[ifOperStatus.60],#1)<>last(/GATEWAY_FILIAL_11_AKTAU/net.if.status[ifOperStatus.60],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "37",
            "name": "FILIAL_11_Aktau"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_11_AKTAU",
            "hostid": "11187",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_11_AKTAU",
            "proxy_hostid": "11164",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "196740",
            "key_": "net.if.status[ifOperStatus.60]",
            "lastvalue": "2",
            "name": "Interface Tu51107(Aktau to RKO-1107 (STB)): Operational status"
          }
        ],
        "lastchange": "1686122530",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_11_AKTAU/net.if.status[ifOperStatus.60])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "81928",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "83401": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu18(Pavlodar to ATM-12018): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_12_PAVLODAR/net.if.status[ifOperStatus.16])=2 and (last(/GATEWAY_FILIAL_12_PAVLODAR/net.if.status[ifOperStatus.16],#1)<>last(/GATEWAY_FILIAL_12_PAVLODAR/net.if.status[ifOperStatus.16],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "38",
            "name": "FILIAL_12_Pavlodar"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_12_PAVLODAR",
            "hostid": "11211",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_12_PAVLODAR",
            "proxy_hostid": "11188",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "200986",
            "key_": "net.if.status[ifOperStatus.16]",
            "lastvalue": "2",
            "name": "Interface Tu18(Pavlodar to ATM-12018): Operational status"
          }
        ],
        "lastchange": "1686561153",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_12_PAVLODAR/net.if.status[ifOperStatus.16])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "83401",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "84849": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu21304(Uralsk to ATM-13004): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_13_URALSK/net.if.status[ifOperStatus.23])=2 and (last(/GATEWAY_FILIAL_13_URALSK/net.if.status[ifOperStatus.23],#1)<>last(/GATEWAY_FILIAL_13_URALSK/net.if.status[ifOperStatus.23],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "39",
            "name": "FILIAL_13_Uralsk"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_13_URALSK",
            "hostid": "11231",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_13_URALSK",
            "proxy_hostid": "11215",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "204875",
            "key_": "net.if.status[ifOperStatus.23]",
            "lastvalue": "2",
            "name": "Interface Tu21304(Uralsk to ATM-13004): Operational status"
          }
        ],
        "lastchange": "1686553612",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_13_URALSK/net.if.status[ifOperStatus.23])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "84849",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "86114": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/FL22-W-SUO0022/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "45",
            "name": "FILIAL_22_Turkestan"
          },
          {
            "groupid": "73",
            "name": "DEVICES_SUO_LOCALSERVER_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "FL22-W-SUO0022",
            "hostid": "11265",
            "maintenance_status": "0",
            "name": "FL22-W-SUO0022",
            "proxy_hostid": "11248",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "208475",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686221975",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23210",
        "triggerid": "86114",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "86660": {
        "comments": "This Ethernet connection has transitioned down from its known maximum speed. This might be a sign of autonegotiation issues. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Gi0/1/2(Link_to_URA-BRANCH-SW-3): Ethernet has changed to lower speed than it was before",
        "error": "",
        "event_name": "",
        "expression": "change(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.speed[ifHighSpeed.6])<0 and last(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.speed[ifHighSpeed.6])>0\r\nand (\r\nlast(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.type[ifType.6])=6 or\r\nlast(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.type[ifType.6])=7 or\r\nlast(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.type[ifType.6])=11 or\r\nlast(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.type[ifType.6])=62 or\r\nlast(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.type[ifType.6])=69 or\r\nlast(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.type[ifType.6])=117\r\n)\r\nand\r\n(last(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.status[ifOperStatus.6])<>2)",
        "flags": "4",
        "groups": [
          {
            "groupid": "40",
            "name": "FILIAL_14_Petropavlovsk"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_14_PETROPAVLOVSK",
            "hostid": "11247",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_14_PETROPAVLOVSK",
            "proxy_hostid": "11232",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "210100",
            "key_": "net.if.type[ifType.6]",
            "lastvalue": "6",
            "name": "Interface Gi0/1/2(Link_to_URA-BRANCH-SW-3): Interface type"
          },
          {
            "itemid": "210151",
            "key_": "net.if.status[ifOperStatus.6]",
            "lastvalue": "1",
            "name": "Interface Gi0/1/2(Link_to_URA-BRANCH-SW-3): Operational status"
          },
          {
            "itemid": "210304",
            "key_": "net.if.speed[ifHighSpeed.6]",
            "lastvalue": "100000000",
            "name": "Interface Gi0/1/2(Link_to_URA-BRANCH-SW-3): Speed"
          }
        ],
        "lastchange": "1685436098",
        "manual_close": "1",
        "opdata": "Current reported speed: {ITEM.LASTVALUE1}",
        "priority": "1",
        "recovery_expression": "(change(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.speed[ifHighSpeed.6])>0 and last(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.speed[ifHighSpeed.6],#2)>0) or\r\n(last(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.status[ifOperStatus.6])=2)",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "86660",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "86783": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu21414(tunnel to ATM-14012): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.status[ifOperStatus.34])=2 and (last(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.status[ifOperStatus.34],#1)<>last(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.status[ifOperStatus.34],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "40",
            "name": "FILIAL_14_Petropavlovsk"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_14_PETROPAVLOVSK",
            "hostid": "11247",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_14_PETROPAVLOVSK",
            "proxy_hostid": "11232",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "210172",
            "key_": "net.if.status[ifOperStatus.34]",
            "lastvalue": "2",
            "name": "Interface Tu21414(tunnel to ATM-14012): Operational status"
          }
        ],
        "lastchange": "1686351487",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_14_PETROPAVLOVSK/net.if.status[ifOperStatus.34])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "86783",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "86980": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu41503(Shymkent to RKO-1503 (STB)): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_15_SHYMKENT/net.if.status[ifOperStatus.55])=2 and (last(/GATEWAY_FILIAL_15_SHYMKENT/net.if.status[ifOperStatus.55],#1)<>last(/GATEWAY_FILIAL_15_SHYMKENT/net.if.status[ifOperStatus.55],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "41",
            "name": "FILIAL_15_Shymkent"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_15_SHYMKENT",
            "hostid": "11274",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_15_SHYMKENT",
            "proxy_hostid": "11248",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "210706",
            "key_": "net.if.status[ifOperStatus.55]",
            "lastvalue": "2",
            "name": "Interface Tu41503(Shymkent to RKO-1503 (STB)): Operational status"
          }
        ],
        "lastchange": "1686558393",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_15_SHYMKENT/net.if.status[ifOperStatus.55])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "86980",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "86981": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu41508(Shymkent to RKO-1508 (DKP)): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_15_SHYMKENT/net.if.status[ifOperStatus.57])=2 and (last(/GATEWAY_FILIAL_15_SHYMKENT/net.if.status[ifOperStatus.57],#1)<>last(/GATEWAY_FILIAL_15_SHYMKENT/net.if.status[ifOperStatus.57],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "41",
            "name": "FILIAL_15_Shymkent"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_15_SHYMKENT",
            "hostid": "11274",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_15_SHYMKENT",
            "proxy_hostid": "11248",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "210707",
            "key_": "net.if.status[ifOperStatus.57]",
            "lastvalue": "2",
            "name": "Interface Tu41508(Shymkent to RKO-1508 (DKP)): Operational status"
          }
        ],
        "lastchange": "1684157133",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_15_SHYMKENT/net.if.status[ifOperStatus.57])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "86981",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "88477": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/FL19-W-SUO1905/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "43",
            "name": "FILIAL_19_Taldykorgan"
          },
          {
            "groupid": "73",
            "name": "DEVICES_SUO_LOCALSERVER_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "FL19-W-SUO1905",
            "hostid": "11302",
            "maintenance_status": "0",
            "name": "FL19-W-SUO1905",
            "proxy_hostid": "11276",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "215099",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1685950679",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23210",
        "triggerid": "88477",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "88631": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/FL19-W-CHECKIN6/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "43",
            "name": "FILIAL_19_Taldykorgan"
          },
          {
            "groupid": "72",
            "name": "DEVICES_SUO_CHECKIN_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "FL19-W-CHECKIN6",
            "hostid": "11295",
            "maintenance_status": "0",
            "name": "FL19-W-CHECKIN6",
            "proxy_hostid": "11276",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "215554",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1685442574",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23210",
        "triggerid": "88631",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "89036": {
        "comments": "Please check the power supply unit for errors",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Power Supply  1: Power supply is in critical state",
        "error": "",
        "event_name": "",
        "expression": "count(/GATEWAY_FILIAL_17_KOKSHETAU/sensor.psu.status[ciscoEnvMonSupplyState.1],#1,\"eq\",\"3\")=1 or count(/GATEWAY_FILIAL_17_KOKSHETAU/sensor.psu.status[ciscoEnvMonSupplyState.1],#1,\"eq\",\"4\")=1",
        "flags": "4",
        "groups": [
          {
            "groupid": "42",
            "name": "FILIAL_17_Kokshetau"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_17_KOKSHETAU",
            "hostid": "11315",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_17_KOKSHETAU",
            "proxy_hostid": "11275",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "216498",
            "key_": "sensor.psu.status[ciscoEnvMonSupplyState.1]",
            "lastvalue": "3",
            "name": "Power Supply  1: Power supply status"
          }
        ],
        "lastchange": "1683289632",
        "manual_close": "0",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "89036",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "89477": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu21930(Taldykorgan to ATM-19023): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_19_TALDYKORGAN/net.if.status[ifOperStatus.41])=2 and (last(/GATEWAY_FILIAL_19_TALDYKORGAN/net.if.status[ifOperStatus.41],#1)<>last(/GATEWAY_FILIAL_19_TALDYKORGAN/net.if.status[ifOperStatus.41],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "43",
            "name": "FILIAL_19_Taldykorgan"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_19_TALDYKORGAN",
            "hostid": "11317",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_19_TALDYKORGAN",
            "proxy_hostid": "11276",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "217481",
            "key_": "net.if.status[ifOperStatus.41]",
            "lastvalue": "2",
            "name": "Interface Tu21930(Taldykorgan to ATM-19023): Operational status"
          }
        ],
        "lastchange": "1686302654",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_19_TALDYKORGAN/net.if.status[ifOperStatus.41])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "89477",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "90506": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/FL19-W-SUO1910/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "43",
            "name": "FILIAL_19_Taldykorgan"
          },
          {
            "groupid": "73",
            "name": "DEVICES_SUO_LOCALSERVER_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "FL19-W-SUO1910",
            "hostid": "11332",
            "maintenance_status": "0",
            "name": "FL19-W-SUO1910",
            "proxy_hostid": "11276",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "220581",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686300981",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23210",
        "triggerid": "90506",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "90627": {
        "comments": "The device uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Host has been restarted",
        "error": "Cannot evaluate function last(/KZF10WCHECKIN01/system.uptime): item is not supported.",
        "event_name": "Host has been restarted (uptime < 10m)",
        "expression": "last(/KZF10WCHECKIN01/system.uptime)<10m",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "36",
            "name": "FILIAL_10_Taraz"
          },
          {
            "groupid": "72",
            "name": "DEVICES_SUO_CHECKIN_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF10WCHECKIN01",
            "hostid": "11333",
            "maintenance_status": "0",
            "name": "KZF10WCHECKIN01",
            "proxy_hostid": "11141",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "220970",
            "key_": "system.uptime",
            "lastvalue": "0",
            "name": "Uptime"
          }
        ],
        "lastchange": "1684985613",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "1",
        "status": "0",
        "templateid": "22464",
        "triggerid": "90627",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "90918": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/KZF11WSUO1101/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "28",
            "name": "Windows PC"
          },
          {
            "groupid": "37",
            "name": "FILIAL_11_Aktau"
          },
          {
            "groupid": "73",
            "name": "DEVICES_SUO_LOCALSERVER_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF11WSUO1101",
            "hostid": "11339",
            "maintenance_status": "0",
            "name": "KZF11WSUO1101",
            "proxy_hostid": "11164",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "221950",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686153550",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "23210",
        "triggerid": "90918",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "90966": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu30801(Atyrau to RKO-801 Beeline (STB)): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_8_ATYRAU/net.if.status[ifOperStatus.52])=2 and (last(/GATEWAY_FILIAL_8_ATYRAU/net.if.status[ifOperStatus.52],#1)<>last(/GATEWAY_FILIAL_8_ATYRAU/net.if.status[ifOperStatus.52],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "34",
            "name": "FILIAL_08_Atyrau"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_8_ATYRAU",
            "hostid": "11106",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_8_ATYRAU",
            "proxy_hostid": "11087",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "222117",
            "key_": "net.if.status[ifOperStatus.52]",
            "lastvalue": "2",
            "name": "Interface Tu30801(Atyrau to RKO-801 Beeline (STB)): Operational status"
          }
        ],
        "lastchange": "1684823092",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_8_ATYRAU/net.if.status[ifOperStatus.52])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "90966",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "90972": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Tu30807(Atyrau to RKO-807 (STB) Beeline): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/GATEWAY_FILIAL_8_ATYRAU/net.if.status[ifOperStatus.54])=2 and (last(/GATEWAY_FILIAL_8_ATYRAU/net.if.status[ifOperStatus.54],#1)<>last(/GATEWAY_FILIAL_8_ATYRAU/net.if.status[ifOperStatus.54],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "34",
            "name": "FILIAL_08_Atyrau"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_FILIAL_8_ATYRAU",
            "hostid": "11106",
            "maintenance_status": "0",
            "name": "GATEWAY_FILIAL_8_ATYRAU",
            "proxy_hostid": "11087",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "222135",
            "key_": "net.if.status[ifOperStatus.54]",
            "lastvalue": "2",
            "name": "Interface Tu30807(Atyrau to RKO-807 (STB) Beeline): Operational status"
          }
        ],
        "lastchange": "1684928752",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/GATEWAY_FILIAL_8_ATYRAU/net.if.status[ifOperStatus.54])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "90972",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "93302": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/1C-TRM02-WP2/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "80",
            "name": "SYSTEM_1C"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "1C-TRM02-WP2",
            "hostid": "11444",
            "maintenance_status": "0",
            "name": "1C-TRM02-WP2",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "229465",
            "key_": "vm.memory.util",
            "lastvalue": "94.42277843608959",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686559645",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "93302",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96100": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "System(C:): Disk space is low",
        "error": "",
        "event_name": "System(C:): Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"C:\"}%)",
        "expression": "last(/KZWDMAVA01/vfs.fs.size[C:,pused])>80 and\r\n((last(/KZWDMAVA01/vfs.fs.size[C:,total])-last(/KZWDMAVA01/vfs.fs.size[C:,used]))<10G or timeleft(/KZWDMAVA01/vfs.fs.size[C:,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "105",
            "name": "SYSTEM_UVRK"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWDMAVA01",
            "hostid": "11489",
            "maintenance_status": "0",
            "name": "KZWDMAVA01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "237817",
            "key_": "vfs.fs.size[C:,pused]",
            "lastvalue": "88.120799",
            "name": "System(C:): Space utilization"
          },
          {
            "itemid": "237818",
            "key_": "vfs.fs.size[C:,total]",
            "lastvalue": "63868760064",
            "name": "System(C:): Total space"
          },
          {
            "itemid": "237819",
            "key_": "vfs.fs.size[C:,used]",
            "lastvalue": "56281653248",
            "name": "System(C:): Used space"
          }
        ],
        "lastchange": "1684992579",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96100",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96196": {
        "comments": "Two conditions should match: First, space utilization should be above 90.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 5G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Data(D:): Disk space is critically low",
        "error": "",
        "event_name": "Data(D:): Disk space is critically low (used > {$VFS.FS.PUSED.MAX.CRIT:\"D:\"}%)",
        "expression": "last(/KZWDLP05/vfs.fs.size[D:,pused])>90 and\r\n((last(/KZWDLP05/vfs.fs.size[D:,total])-last(/KZWDLP05/vfs.fs.size[D:,used]))<5G or timeleft(/KZWDLP05/vfs.fs.size[D:,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "82",
            "name": "SITB"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWDLP05",
            "hostid": "11442",
            "maintenance_status": "0",
            "name": "KZWDLP05",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "238346",
            "key_": "vfs.fs.size[D:,pused]",
            "lastvalue": "100",
            "name": "Data(D:): Space utilization"
          },
          {
            "itemid": "238348",
            "key_": "vfs.fs.size[D:,total]",
            "lastvalue": "214642454528",
            "name": "Data(D:): Total space"
          },
          {
            "itemid": "238350",
            "key_": "vfs.fs.size[D:,used]",
            "lastvalue": "214642454528",
            "name": "Data(D:): Used space"
          }
        ],
        "lastchange": "1684991366",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96196",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96239": {
        "comments": "Two conditions should match: First, space utilization should be above 90.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 5G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "OS(C:): Disk space is critically low",
        "error": "",
        "event_name": "OS(C:): Disk space is critically low (used > {$VFS.FS.PUSED.MAX.CRIT:\"C:\"}%)",
        "expression": "last(/KZWSCSP02/vfs.fs.size[C:,pused])>90 and\r\n((last(/KZWSCSP02/vfs.fs.size[C:,total])-last(/KZWSCSP02/vfs.fs.size[C:,used]))<5G or timeleft(/KZWSCSP02/vfs.fs.size[C:,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "82",
            "name": "SITB"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSCSP02",
            "hostid": "11502",
            "maintenance_status": "0",
            "name": "KZWSCSP02",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "238579",
            "key_": "vfs.fs.size[C:,pused]",
            "lastvalue": "100",
            "name": "OS(C:): Space utilization"
          },
          {
            "itemid": "238580",
            "key_": "vfs.fs.size[C:,total]",
            "lastvalue": "321475571712",
            "name": "OS(C:): Total space"
          },
          {
            "itemid": "238581",
            "key_": "vfs.fs.size[C:,used]",
            "lastvalue": "321475571712",
            "name": "OS(C:): Used space"
          }
        ],
        "lastchange": "1686483740",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96239",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96316": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "System(C:): Disk space is low",
        "error": "",
        "event_name": "System(C:): Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"C:\"}%)",
        "expression": "last(/KZWAPPBNKS01/vfs.fs.size[C:,pused])>80 and\r\n((last(/KZWAPPBNKS01/vfs.fs.size[C:,total])-last(/KZWAPPBNKS01/vfs.fs.size[C:,used]))<10G or timeleft(/KZWAPPBNKS01/vfs.fs.size[C:,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPPBNKS01",
            "hostid": "11509",
            "maintenance_status": "0",
            "name": "KZWAPPBNKS01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "239005",
            "key_": "vfs.fs.size[C:,pused]",
            "lastvalue": "90.001912",
            "name": "System(C:): Space utilization"
          },
          {
            "itemid": "239006",
            "key_": "vfs.fs.size[C:,total]",
            "lastvalue": "85303750656",
            "name": "System(C:): Total space"
          },
          {
            "itemid": "239007",
            "key_": "vfs.fs.size[C:,used]",
            "lastvalue": "76775092224",
            "name": "System(C:): Used space"
          }
        ],
        "lastchange": "1686033447",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96316",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96430": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Data(E:): Disk space is low",
        "error": "",
        "event_name": "Data(E:): Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"E:\"}%)",
        "expression": "last(/KZWAPYU02/vfs.fs.size[E:,pused])>80 and\r\n((last(/KZWAPYU02/vfs.fs.size[E:,total])-last(/KZWAPYU02/vfs.fs.size[E:,used]))<10G or timeleft(/KZWAPYU02/vfs.fs.size[E:,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "101",
            "name": "SYSTEM_PARAGRAPH"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPYU02",
            "hostid": "11463",
            "maintenance_status": "0",
            "name": "KZWAPYU02",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "239630",
            "key_": "vfs.fs.size[E:,pused]",
            "lastvalue": "95.002793",
            "name": "Data(E:): Space utilization"
          },
          {
            "itemid": "239632",
            "key_": "vfs.fs.size[E:,total]",
            "lastvalue": "214610997248",
            "name": "Data(E:): Total space"
          },
          {
            "itemid": "239634",
            "key_": "vfs.fs.size[E:,used]",
            "lastvalue": "203886440448",
            "name": "Data(E:): Used space"
          }
        ],
        "lastchange": "1686481674",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96430",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96520": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "OS(C:): Disk space is low",
        "error": "",
        "event_name": "OS(C:): Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"C:\"}%)",
        "expression": "last(/KZWSHPO02/vfs.fs.size[C:,pused])>80 and\r\n((last(/KZWSHPO02/vfs.fs.size[C:,total])-last(/KZWSHPO02/vfs.fs.size[C:,used]))<10G or timeleft(/KZWSHPO02/vfs.fs.size[C:,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "82",
            "name": "SITB"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSHPO02",
            "hostid": "11471",
            "maintenance_status": "0",
            "name": "KZWSHPO02",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "240375",
            "key_": "vfs.fs.size[C:,pused]",
            "lastvalue": "91.741476",
            "name": "OS(C:): Space utilization"
          },
          {
            "itemid": "240376",
            "key_": "vfs.fs.size[C:,total]",
            "lastvalue": "128478867456",
            "name": "OS(C:): Total space"
          },
          {
            "itemid": "240377",
            "key_": "vfs.fs.size[C:,used]",
            "lastvalue": "117868412928",
            "name": "OS(C:): Used space"
          }
        ],
        "lastchange": "1686535457",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96520",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96571": {
        "comments": "Two conditions should match: First, space utilization should be above 90.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 5G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "System(C:): Disk space is critically low",
        "error": "",
        "event_name": "System(C:): Disk space is critically low (used > {$VFS.FS.PUSED.MAX.CRIT:\"C:\"}%)",
        "expression": "last(/KZWRSTK04/vfs.fs.size[C:,pused])>90 and\r\n((last(/KZWRSTK04/vfs.fs.size[C:,total])-last(/KZWRSTK04/vfs.fs.size[C:,used]))<5G or timeleft(/KZWRSTK04/vfs.fs.size[C:,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "92",
            "name": "SYSTEM_RS-BANK"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWRSTK04",
            "hostid": "11534",
            "maintenance_status": "0",
            "name": "KZWRSTK04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "240725",
            "key_": "vfs.fs.size[C:,pused]",
            "lastvalue": "94.465459",
            "name": "System(C:): Space utilization"
          },
          {
            "itemid": "240726",
            "key_": "vfs.fs.size[C:,total]",
            "lastvalue": "84793638912",
            "name": "System(C:): Total space"
          },
          {
            "itemid": "240727",
            "key_": "vfs.fs.size[C:,used]",
            "lastvalue": "80100700160",
            "name": "System(C:): Used space"
          }
        ],
        "lastchange": "1686268867",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96571",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96748": {
        "comments": "Windows Process Activation Service (WAS) is not in the running state. IIS cannot start.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Windows process Activation Service (WAS) is not running",
        "error": "",
        "event_name": "",
        "expression": "last(/KZWAPBIZT06/service.info[WAS])<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT06",
            "hostid": "11354",
            "maintenance_status": "0",
            "name": "KZWAPBIZT06",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241455",
            "key_": "service.info[WAS]",
            "lastvalue": "255",
            "name": "IIS: Windows Process Activation Service (WAS) state"
          }
        ],
        "lastchange": "1685028555",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "16905",
        "triggerid": "96748",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96754": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: has been restarted",
        "error": "",
        "event_name": "IIS: has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\Web Service(_Total)\\Service Uptime\"])<10m",
        "flags": "0",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241494",
            "key_": "perf_counter_en[\"\\Web Service(_Total)\\Service Uptime\"]",
            "lastvalue": "209",
            "name": "IIS: Uptime"
          }
        ],
        "lastchange": "1686562201",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "16903",
        "triggerid": "96754",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96869": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: DefaultAppPool has been restarted",
        "error": "",
        "event_name": "IIS: DefaultAppPool has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(DefaultAppPool)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241852",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(DefaultAppPool)\\Current Application Pool Uptime\"]",
            "lastvalue": "208.170475",
            "name": "IIS: DefaultAppPool Uptime"
          }
        ],
        "lastchange": "1686562252",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96869",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96870": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: .NET v4.5 Classic has been restarted",
        "error": "",
        "event_name": "IIS: .NET v4.5 Classic has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(.NET v4.5 Classic)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241853",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(.NET v4.5 Classic)\\Current Application Pool Uptime\"]",
            "lastvalue": "208.170475",
            "name": "IIS: .NET v4.5 Classic Uptime"
          }
        ],
        "lastchange": "1686562253",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96870",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96871": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: .NET v4.5 has been restarted",
        "error": "",
        "event_name": "IIS: .NET v4.5 has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(.NET v4.5)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241854",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(.NET v4.5)\\Current Application Pool Uptime\"]",
            "lastvalue": "210.192388",
            "name": "IIS: .NET v4.5 Uptime"
          }
        ],
        "lastchange": "1686562254",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96871",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96872": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: BisAppPool has been restarted",
        "error": "",
        "event_name": "IIS: BisAppPool has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(BisAppPool)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241855",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(BisAppPool)\\Current Application Pool Uptime\"]",
            "lastvalue": "211.208017",
            "name": "IIS: BisAppPool Uptime"
          }
        ],
        "lastchange": "1686562255",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96872",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96873": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: USSD has been restarted",
        "error": "",
        "event_name": "IIS: USSD has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(USSD)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241856",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(USSD)\\Current Application Pool Uptime\"]",
            "lastvalue": "212.223645",
            "name": "IIS: USSD Uptime"
          }
        ],
        "lastchange": "1686562256",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96873",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96874": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: OTPC has been restarted",
        "error": "",
        "event_name": "IIS: OTPC has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(OTPC)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241857",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(OTPC)\\Current Application Pool Uptime\"]",
            "lastvalue": "212.223645",
            "name": "IIS: OTPC Uptime"
          }
        ],
        "lastchange": "1686562328",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96874",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96875": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: BisAppPool_32 has been restarted",
        "error": "",
        "event_name": "IIS: BisAppPool_32 has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(BisAppPool_32)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241858",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(BisAppPool_32)\\Current Application Pool Uptime\"]",
            "lastvalue": "213.239269",
            "name": "IIS: BisAppPool_32 Uptime"
          }
        ],
        "lastchange": "1686562258",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96875",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96876": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: RSBankTK has been restarted",
        "error": "",
        "event_name": "IIS: RSBankTK has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(RSBankTK)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241859",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(RSBankTK)\\Current Application Pool Uptime\"]",
            "lastvalue": "215.270526",
            "name": "IIS: RSBankTK Uptime"
          }
        ],
        "lastchange": "1686562259",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96876",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96877": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: BisAgentService has been restarted",
        "error": "",
        "event_name": "IIS: BisAgentService has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(BisAgentService)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241860",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(BisAgentService)\\Current Application Pool Uptime\"]",
            "lastvalue": "216.288469",
            "name": "IIS: BisAgentService Uptime"
          }
        ],
        "lastchange": "1686562260",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96877",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96878": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: BisExternalService has been restarted",
        "error": "",
        "event_name": "IIS: BisExternalService has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(BisExternalService)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241861",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(BisExternalService)\\Current Application Pool Uptime\"]",
            "lastvalue": "156.361185",
            "name": "IIS: BisExternalService Uptime"
          }
        ],
        "lastchange": "1686562261",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96878",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96879": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: BisServices has been restarted",
        "error": "",
        "event_name": "IIS: BisServices has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(BisServices)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241862",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(BisServices)\\Current Application Pool Uptime\"]",
            "lastvalue": "157.376776",
            "name": "IIS: BisServices Uptime"
          }
        ],
        "lastchange": "1686562202",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96879",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96880": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: BisCascadeService has been restarted",
        "error": "",
        "event_name": "IIS: BisCascadeService has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(BisCascadeService)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241863",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(BisCascadeService)\\Current Application Pool Uptime\"]",
            "lastvalue": "158.392398",
            "name": "IIS: BisCascadeService Uptime"
          }
        ],
        "lastchange": "1686562203",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96880",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96881": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: BisRouteServices has been restarted",
        "error": "",
        "event_name": "IIS: BisRouteServices has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(BisRouteServices)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241864",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(BisRouteServices)\\Current Application Pool Uptime\"]",
            "lastvalue": "159.408025",
            "name": "IIS: BisRouteServices Uptime"
          }
        ],
        "lastchange": "1686562204",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96881",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96882": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: BisPaymentTerminal has been restarted",
        "error": "",
        "event_name": "IIS: BisPaymentTerminal has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(BisPaymentTerminal)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241865",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(BisPaymentTerminal)\\Current Application Pool Uptime\"]",
            "lastvalue": "160.423655",
            "name": "IIS: BisPaymentTerminal Uptime"
          }
        ],
        "lastchange": "1686562205",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96882",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96883": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Pgeg has been restarted",
        "error": "",
        "event_name": "IIS: Pgeg has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Pgeg)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241866",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Pgeg)\\Current Application Pool Uptime\"]",
            "lastvalue": "161.44127",
            "name": "IIS: Pgeg Uptime"
          }
        ],
        "lastchange": "1686562206",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96883",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96884": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Pgeg.GatewayService has been restarted",
        "error": "",
        "event_name": "IIS: Pgeg.GatewayService has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Pgeg.GatewayService)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241867",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Pgeg.GatewayService)\\Current Application Pool Uptime\"]",
            "lastvalue": "162.456896",
            "name": "IIS: Pgeg.GatewayService Uptime"
          }
        ],
        "lastchange": "1686562207",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96884",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96885": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Pgeg.AgentService has been restarted",
        "error": "",
        "event_name": "IIS: Pgeg.AgentService has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Pgeg.AgentService)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241868",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Pgeg.AgentService)\\Current Application Pool Uptime\"]",
            "lastvalue": "163.472522",
            "name": "IIS: Pgeg.AgentService Uptime"
          }
        ],
        "lastchange": "1686562208",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96885",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96886": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Pgeg.BankGateway has been restarted",
        "error": "",
        "event_name": "IIS: Pgeg.BankGateway has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Pgeg.BankGateway)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241869",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Pgeg.BankGateway)\\Current Application Pool Uptime\"]",
            "lastvalue": "164.488153",
            "name": "IIS: Pgeg.BankGateway Uptime"
          }
        ],
        "lastchange": "1686562209",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96886",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96887": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Pgeg.OpenAccountWeb has been restarted",
        "error": "",
        "event_name": "IIS: Pgeg.OpenAccountWeb has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Pgeg.OpenAccountWeb)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241870",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Pgeg.OpenAccountWeb)\\Current Application Pool Uptime\"]",
            "lastvalue": "165.503774",
            "name": "IIS: Pgeg.OpenAccountWeb Uptime"
          }
        ],
        "lastchange": "1686562210",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96887",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96888": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Bis.SupportConsole has been restarted",
        "error": "",
        "event_name": "IIS: Bis.SupportConsole has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Bis.SupportConsole)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241871",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Bis.SupportConsole)\\Current Application Pool Uptime\"]",
            "lastvalue": "166.519406",
            "name": "IIS: Bis.SupportConsole Uptime"
          }
        ],
        "lastchange": "1686562211",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96888",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96889": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: SMS has been restarted",
        "error": "",
        "event_name": "IIS: SMS has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(SMS)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241872",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(SMS)\\Current Application Pool Uptime\"]",
            "lastvalue": "167.535031",
            "name": "IIS: SMS Uptime"
          }
        ],
        "lastchange": "1686562212",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96889",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96890": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: KazpostApi has been restarted",
        "error": "",
        "event_name": "IIS: KazpostApi has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(KazpostApi)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241873",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(KazpostApi)\\Current Application Pool Uptime\"]",
            "lastvalue": "168.550662",
            "name": "IIS: KazpostApi Uptime"
          }
        ],
        "lastchange": "1686562213",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96890",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96891": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Korona has been restarted",
        "error": "",
        "event_name": "IIS: Korona has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Korona)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241874",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Korona)\\Current Application Pool Uptime\"]",
            "lastvalue": "169.566283",
            "name": "IIS: Korona Uptime"
          }
        ],
        "lastchange": "1686562214",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96891",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96892": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Bis.Risks has been restarted",
        "error": "",
        "event_name": "IIS: Bis.Risks has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Bis.Risks)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241875",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Bis.Risks)\\Current Application Pool Uptime\"]",
            "lastvalue": "170.572526",
            "name": "IIS: Bis.Risks Uptime"
          }
        ],
        "lastchange": "1686562215",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96892",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96893": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Kisc.InstantPaymentSystem.Terminal has been restarted",
        "error": "",
        "event_name": "IIS: Kisc.InstantPaymentSystem.Terminal has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Kisc.InstantPaymentSystem.Terminal)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241876",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Kisc.InstantPaymentSystem.Terminal)\\Current Application Pool Uptime\"]",
            "lastvalue": "171.58817",
            "name": "IIS: Kisc.InstantPaymentSystem.Terminal Uptime"
          }
        ],
        "lastchange": "1686562216",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96893",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96894": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Pgeg.VATControlAccount has been restarted",
        "error": "",
        "event_name": "IIS: Pgeg.VATControlAccount has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Pgeg.VATControlAccount)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241877",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Pgeg.VATControlAccount)\\Current Application Pool Uptime\"]",
            "lastvalue": "232.53851",
            "name": "IIS: Pgeg.VATControlAccount Uptime"
          }
        ],
        "lastchange": "1686562217",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96894",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96895": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Bis.FcbTerminal has been restarted",
        "error": "",
        "event_name": "IIS: Bis.FcbTerminal has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Bis.FcbTerminal)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241878",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Bis.FcbTerminal)\\Current Application Pool Uptime\"]",
            "lastvalue": "233.554137",
            "name": "IIS: Bis.FcbTerminal Uptime"
          }
        ],
        "lastchange": "1686562218",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96895",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96896": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Bis.P2P has been restarted",
        "error": "",
        "event_name": "IIS: Bis.P2P has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Bis.P2P)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241879",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Bis.P2P)\\Current Application Pool Uptime\"]",
            "lastvalue": "234.569759",
            "name": "IIS: Bis.P2P Uptime"
          }
        ],
        "lastchange": "1686562219",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96896",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96897": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: AwayaHandler has been restarted",
        "error": "",
        "event_name": "IIS: AwayaHandler has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(AwayaHandler)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241880",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(AwayaHandler)\\Current Application Pool Uptime\"]",
            "lastvalue": "235.585391",
            "name": "IIS: AwayaHandler Uptime"
          }
        ],
        "lastchange": "1686562220",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96897",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96898": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: ElasticaHandler has been restarted",
        "error": "",
        "event_name": "IIS: ElasticaHandler has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(ElasticaHandler)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241881",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(ElasticaHandler)\\Current Application Pool Uptime\"]",
            "lastvalue": "236.601022",
            "name": "IIS: ElasticaHandler Uptime"
          }
        ],
        "lastchange": "1686562221",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96898",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96899": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Bis.SettlementSheets has been restarted",
        "error": "",
        "event_name": "IIS: Bis.SettlementSheets has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Bis.SettlementSheets)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241882",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Bis.SettlementSheets)\\Current Application Pool Uptime\"]",
            "lastvalue": "237.610021",
            "name": "IIS: Bis.SettlementSheets Uptime"
          }
        ],
        "lastchange": "1686562222",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96899",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96900": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Eubank.IdentityServer has been restarted",
        "error": "",
        "event_name": "IIS: Eubank.IdentityServer has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Eubank.IdentityServer)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241883",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Eubank.IdentityServer)\\Current Application Pool Uptime\"]",
            "lastvalue": "238.625654",
            "name": "IIS: Eubank.IdentityServer Uptime"
          }
        ],
        "lastchange": "1686562223",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96900",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96901": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Eubank.IdentityServer.AdminApi has been restarted",
        "error": "",
        "event_name": "IIS: Eubank.IdentityServer.AdminApi has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Eubank.IdentityServer.AdminApi)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241884",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Eubank.IdentityServer.AdminApi)\\Current Application Pool Uptime\"]",
            "lastvalue": "239.656905",
            "name": "IIS: Eubank.IdentityServer.AdminApi Uptime"
          }
        ],
        "lastchange": "1686562224",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96901",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96902": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: FIS.ESB.Host has been restarted",
        "error": "",
        "event_name": "IIS: FIS.ESB.Host has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(FIS.ESB.Host)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241885",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(FIS.ESB.Host)\\Current Application Pool Uptime\"]",
            "lastvalue": "240.67253",
            "name": "IIS: FIS.ESB.Host Uptime"
          }
        ],
        "lastchange": "1686562225",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96902",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96903": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: 1CB-KDN has been restarted",
        "error": "",
        "event_name": "IIS: 1CB-KDN has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(1CB-KDN)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241886",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(1CB-KDN)\\Current Application Pool Uptime\"]",
            "lastvalue": "241.70378",
            "name": "IIS: 1CB-KDN Uptime"
          }
        ],
        "lastchange": "1686562226",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96903",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96904": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: BSPH has been restarted",
        "error": "",
        "event_name": "IIS: BSPH has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(BSPH)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241887",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(BSPH)\\Current Application Pool Uptime\"]",
            "lastvalue": "242.719411",
            "name": "IIS: BSPH Uptime"
          }
        ],
        "lastchange": "1686562227",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96904",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96905": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Gateway.Aml has been restarted",
        "error": "",
        "event_name": "IIS: Gateway.Aml has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Gateway.Aml)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241888",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Gateway.Aml)\\Current Application Pool Uptime\"]",
            "lastvalue": "243.735047",
            "name": "IIS: Gateway.Aml Uptime"
          }
        ],
        "lastchange": "1686562228",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96905",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96906": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Gateway.Credilogic has been restarted",
        "error": "",
        "event_name": "IIS: Gateway.Credilogic has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Gateway.Credilogic)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241889",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Gateway.Credilogic)\\Current Application Pool Uptime\"]",
            "lastvalue": "244.750666",
            "name": "IIS: Gateway.Credilogic Uptime"
          }
        ],
        "lastchange": "1686562229",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96906",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96907": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Gateway.RsLoans has been restarted",
        "error": "",
        "event_name": "IIS: Gateway.RsLoans has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Gateway.RsLoans)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241890",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Gateway.RsLoans)\\Current Application Pool Uptime\"]",
            "lastvalue": "244.750666",
            "name": "IIS: Gateway.RsLoans Uptime"
          }
        ],
        "lastchange": "1686562230",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96907",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96908": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Gateway.RsRetail has been restarted",
        "error": "",
        "event_name": "IIS: Gateway.RsRetail has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Gateway.RsRetail)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241891",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Gateway.RsRetail)\\Current Application Pool Uptime\"]",
            "lastvalue": "67.00283",
            "name": "IIS: Gateway.RsRetail Uptime"
          }
        ],
        "lastchange": "1686562231",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96908",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96909": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Kisc.IDPC has been restarted",
        "error": "",
        "event_name": "IIS: Kisc.IDPC has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Kisc.IDPC)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241892",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Kisc.IDPC)\\Current Application Pool Uptime\"]",
            "lastvalue": "246.781924",
            "name": "IIS: Kisc.IDPC Uptime"
          }
        ],
        "lastchange": "1686562232",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96909",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96910": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Bis.StatGov has been restarted",
        "error": "",
        "event_name": "IIS: Bis.StatGov has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Bis.StatGov)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241893",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Bis.StatGov)\\Current Application Pool Uptime\"]",
            "lastvalue": "247.797545",
            "name": "IIS: Bis.StatGov Uptime"
          }
        ],
        "lastchange": "1686562233",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96910",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96911": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Gateway.RsLoans.Customer has been restarted",
        "error": "",
        "event_name": "IIS: Gateway.RsLoans.Customer has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Gateway.RsLoans.Customer)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241894",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Gateway.RsLoans.Customer)\\Current Application Pool Uptime\"]",
            "lastvalue": "248.813175",
            "name": "IIS: Gateway.RsLoans.Customer Uptime"
          }
        ],
        "lastchange": "1686562234",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96911",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96912": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Gateway.Provider.Mir has been restarted",
        "error": "",
        "event_name": "IIS: Gateway.Provider.Mir has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Gateway.Provider.Mir)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241895",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Gateway.Provider.Mir)\\Current Application Pool Uptime\"]",
            "lastvalue": "249.8288",
            "name": "IIS: Gateway.Provider.Mir Uptime"
          }
        ],
        "lastchange": "1686562235",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96912",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96913": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Gateway.Refinitiv has been restarted",
        "error": "",
        "event_name": "IIS: Gateway.Refinitiv has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Gateway.Refinitiv)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241896",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Gateway.Refinitiv)\\Current Application Pool Uptime\"]",
            "lastvalue": "250.844433",
            "name": "IIS: Gateway.Refinitiv Uptime"
          }
        ],
        "lastchange": "1686562236",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96913",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96914": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Gateway.Ashyq has been restarted",
        "error": "",
        "event_name": "IIS: Gateway.Ashyq has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Gateway.Ashyq)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241897",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Gateway.Ashyq)\\Current Application Pool Uptime\"]",
            "lastvalue": "251.864967",
            "name": "IIS: Gateway.Ashyq Uptime"
          }
        ],
        "lastchange": "1686562177",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96914",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96915": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Btsd.Client has been restarted",
        "error": "",
        "event_name": "IIS: Btsd.Client has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Btsd.Client)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241898",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Btsd.Client)\\Current Application Pool Uptime\"]",
            "lastvalue": "252.880593",
            "name": "IIS: Btsd.Client Uptime"
          }
        ],
        "lastchange": "1686562178",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96915",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96916": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Btsd.Server has been restarted",
        "error": "",
        "event_name": "IIS: Btsd.Server has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Btsd.Server)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241899",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Btsd.Server)\\Current Application Pool Uptime\"]",
            "lastvalue": "194.9647",
            "name": "IIS: Btsd.Server Uptime"
          }
        ],
        "lastchange": "1686562179",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96916",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96917": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Mediator has been restarted",
        "error": "",
        "event_name": "IIS: Mediator has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Mediator)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241900",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Mediator)\\Current Application Pool Uptime\"]",
            "lastvalue": "195.982946",
            "name": "IIS: Mediator Uptime"
          }
        ],
        "lastchange": "1686562180",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96917",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96918": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Kacd has been restarted",
        "error": "",
        "event_name": "IIS: Kacd has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Kacd)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241901",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Kacd)\\Current Application Pool Uptime\"]",
            "lastvalue": "196.998573",
            "name": "IIS: Kacd Uptime"
          }
        ],
        "lastchange": "1686562181",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96918",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96919": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: ReportConsumer has been restarted",
        "error": "",
        "event_name": "IIS: ReportConsumer has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(ReportConsumer)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241902",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(ReportConsumer)\\Current Application Pool Uptime\"]",
            "lastvalue": "198.014203",
            "name": "IIS: ReportConsumer Uptime"
          }
        ],
        "lastchange": "1686562182",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96919",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96920": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Gateway.Pgeg has been restarted",
        "error": "",
        "event_name": "IIS: Gateway.Pgeg has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Gateway.Pgeg)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241903",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Gateway.Pgeg)\\Current Application Pool Uptime\"]",
            "lastvalue": "199.029831",
            "name": "IIS: Gateway.Pgeg Uptime"
          }
        ],
        "lastchange": "1686562183",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96920",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96921": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: CardManager has been restarted",
        "error": "",
        "event_name": "IIS: CardManager has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(CardManager)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241904",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(CardManager)\\Current Application Pool Uptime\"]",
            "lastvalue": "200.045459",
            "name": "IIS: CardManager Uptime"
          }
        ],
        "lastchange": "1686562184",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96921",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96922": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Bloomberg.Api has been restarted",
        "error": "",
        "event_name": "IIS: Bloomberg.Api has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Bloomberg.Api)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241905",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Bloomberg.Api)\\Current Application Pool Uptime\"]",
            "lastvalue": "201.061088",
            "name": "IIS: Bloomberg.Api Uptime"
          }
        ],
        "lastchange": "1686562185",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96922",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96923": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Kompra.ApiGateway has been restarted",
        "error": "",
        "event_name": "IIS: Kompra.ApiGateway has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Kompra.ApiGateway)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241906",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Kompra.ApiGateway)\\Current Application Pool Uptime\"]",
            "lastvalue": "202.076713",
            "name": "IIS: Kompra.ApiGateway Uptime"
          }
        ],
        "lastchange": "1686562246",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96923",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96924": {
        "comments": "Uptime is less than 10 minutes.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: BankingServiceInfoHub has been restarted",
        "error": "",
        "event_name": "IIS: BankingServiceInfoHub has been restarted (uptime < 10m)",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(BankingServiceInfoHub)\\Current Application Pool Uptime\"])<10m",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241907",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(BankingServiceInfoHub)\\Current Application Pool Uptime\"]",
            "lastvalue": "203.092344",
            "name": "IIS: BankingServiceInfoHub Uptime"
          }
        ],
        "lastchange": "1686562247",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96924",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "96963": {
        "comments": "",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Application pool Gateway.RsLoans has been recycled",
        "error": "",
        "event_name": "",
        "expression": "last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Gateway.RsLoans)\\Total Application Pool Recycles\"],#1)<>last(/KZWAPBIZT04/perf_counter_en[\"\\APP_POOL_WAS(Gateway.RsLoans)\\Total Application Pool Recycles\"],#2) and 1=1",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPBIZT04",
            "hostid": "11495",
            "maintenance_status": "0",
            "name": "KZWAPBIZT04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "241778",
            "key_": "perf_counter_en[\"\\APP_POOL_WAS(Gateway.RsLoans)\\Total Application Pool Recycles\"]",
            "lastvalue": "0",
            "name": "IIS: AppPool Gateway.RsLoans recycles"
          }
        ],
        "lastchange": "1686562178",
        "manual_close": "0",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "96963",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "97289": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/IPT-DB01-WP1/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "50",
            "name": "DC_NAURYZBAY_PROCESSING"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "79",
            "name": "IPTADMIN"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "IPT-DB01-WP1",
            "hostid": "11542",
            "maintenance_status": "0",
            "name": "IPT-DB01-WP1",
            "proxy_hostid": "10567",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "242204",
            "key_": "vm.memory.util",
            "lastvalue": "92.056863922161",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686238904",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "97289",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "97311": {
        "comments": "",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Port {$IIS.PORT} is down",
        "error": "",
        "event_name": "",
        "expression": "last(/KZWAPPT01/net.tcp.service[http,,80])=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "51",
            "name": "DC_KUNAEVA_PROCESSING"
          },
          {
            "groupid": "79",
            "name": "IPTADMIN"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPPT01",
            "hostid": "11541",
            "maintenance_status": "0",
            "name": "KZWAPPT01",
            "proxy_hostid": "10568",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "242259",
            "key_": "net.tcp.service[{$IIS.SERVICE_HTTP},,{$IIS.PORT_80}]",
            "lastvalue": "0",
            "name": "IIS: {$IIS.PORT_80} port ping"
          }
        ],
        "lastchange": "1685031369",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "16902",
        "triggerid": "97311",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "97761": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/KZWAPVER1/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPVER1",
            "hostid": "11555",
            "maintenance_status": "0",
            "name": "KZWAPVER1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "243711",
            "key_": "vm.memory.util",
            "lastvalue": "91.92459592698599",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686509271",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "97761",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "98122": {
        "comments": "",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "IIS: Port 443 is down",
        "error": "",
        "event_name": "",
        "expression": "last(/KZWAPPT01/net.tcp.service[https,,443])=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "51",
            "name": "DC_KUNAEVA_PROCESSING"
          },
          {
            "groupid": "79",
            "name": "IPTADMIN"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWAPPT01",
            "hostid": "11541",
            "maintenance_status": "0",
            "name": "KZWAPPT01",
            "proxy_hostid": "10568",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "244952",
            "key_": "net.tcp.service[{$IIS.SERVICE_HTTPS},,{$IIS.PORT_443}]",
            "lastvalue": "0",
            "name": "IIS: {$IIS.PORT_443} port ping"
          }
        ],
        "lastchange": "1685334602",
        "manual_close": "1",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98117",
        "triggerid": "98122",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "98622": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "System(C:): Disk space is low",
        "error": "",
        "event_name": "System(C:): Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"C:\"}%)",
        "expression": "last(/KZWRSCHD03/vfs.fs.size[C:,pused])>80 and\r\n((last(/KZWRSCHD03/vfs.fs.size[C:,total])-last(/KZWRSCHD03/vfs.fs.size[C:,used]))<10G or timeleft(/KZWRSCHD03/vfs.fs.size[C:,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWRSCHD03",
            "hostid": "10773",
            "maintenance_status": "0",
            "name": "KZWRSCHD03",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "246466",
            "key_": "vfs.fs.size[C:,pused]",
            "lastvalue": "88.218877",
            "name": "System(C:): Space utilization"
          },
          {
            "itemid": "246467",
            "key_": "vfs.fs.size[C:,total]",
            "lastvalue": "84927856640",
            "name": "System(C:): Total space"
          },
          {
            "itemid": "246468",
            "key_": "vfs.fs.size[C:,used]",
            "lastvalue": "74922401792",
            "name": "System(C:): Used space"
          }
        ],
        "lastchange": "1685547948",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "98622",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "98777": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/CMK-APP01-WT1/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "52",
            "name": "DC_NAURYZBAY_DEV_TEST"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "CMK-APP01-WT1",
            "hostid": "11578",
            "maintenance_status": "0",
            "name": "CMK-APP01-WT1",
            "proxy_hostid": "10565",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "246977",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686137717",
        "manual_close": "1",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22466",
        "triggerid": "98777",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "98812": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/KZWSQLCRMSTND/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "107",
            "name": "SYSTEM_CRM"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLCRMSTND",
            "hostid": "11579",
            "maintenance_status": "0",
            "name": "KZWSQLCRMSTND",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "247070",
            "key_": "vm.memory.util",
            "lastvalue": "95.1235356530186",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686199370",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "98812",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "98916": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/VBR-DB02-WP2/service.info[\"SQLSERVERAGENT\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "VBR-DB02-WP2",
            "hostid": "11585",
            "maintenance_status": "0",
            "name": "VBR-DB02-WP2",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "247346",
            "key_": "service.info[\"SQLSERVERAGENT\",state]",
            "lastvalue": "6",
            "name": "State of service \"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685697566",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98123",
        "triggerid": "98916",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "99082": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/KZWSQLCRMPROD/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "107",
            "name": "SYSTEM_CRM"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLCRMPROD",
            "hostid": "11593",
            "maintenance_status": "0",
            "name": "KZWSQLCRMPROD",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "247856",
            "key_": "vm.memory.util",
            "lastvalue": "96.0555710065606",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686171356",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "99082",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "99140": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/VBR-DB01-WP1/service.info[\"SQLSERVERAGENT\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "VBR-DB01-WP1",
            "hostid": "11596",
            "maintenance_status": "0",
            "name": "VBR-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "248000",
            "key_": "service.info[\"SQLSERVERAGENT\",state]",
            "lastvalue": "6",
            "name": "State of service \"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685697800",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98123",
        "triggerid": "99140",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "99174": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/SA-DB01-WP1/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "SA-DB01-WP1",
            "hostid": "11597",
            "maintenance_status": "0",
            "name": "SA-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "248120",
            "key_": "vm.memory.util",
            "lastvalue": "92.27709448962842",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1685697860",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "99174",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "99220": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/DWH-DB01-WP1/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "DWH-DB01-WP1",
            "hostid": "11599",
            "maintenance_status": "0",
            "name": "DWH-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "248252",
            "key_": "vm.memory.util",
            "lastvalue": "95.55536058107842",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1685697872",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "99220",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "99268": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/SB-DB01-WP1/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "SB-DB01-WP1",
            "hostid": "11601",
            "maintenance_status": "0",
            "name": "SB-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "248386",
            "key_": "vm.memory.util",
            "lastvalue": "98.6546332189188",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1685697826",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "99268",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "99360": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/KZWSQLCL04/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "91",
            "name": "SYSTEM_CREDILOGIC"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLCL04",
            "hostid": "11605",
            "maintenance_status": "0",
            "name": "KZWSQLCL04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "248650",
            "key_": "vm.memory.util",
            "lastvalue": "98.04838830140103",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1685697910",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "99360",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "99568": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/KZWSQLCL03/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "91",
            "name": "SYSTEM_CREDILOGIC"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLCL03",
            "hostid": "11615",
            "maintenance_status": "0",
            "name": "KZWSQLCL03",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "249245",
            "key_": "vm.memory.util",
            "lastvalue": "96.96262983643065",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1685697605",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "99568",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "99734": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/PBI-DB02-WP2/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "106",
            "name": "SYSTEM_POWERBI"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "PBI-DB02-WP2",
            "hostid": "11622",
            "maintenance_status": "0",
            "name": "PBI-DB02-WP2",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "249712",
            "key_": "vm.memory.util",
            "lastvalue": "92.74833099704975",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1685697592",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "99734",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "99794": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/CRM-DB01-WP1/service.info[\"SQLSERVERAGENT\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "107",
            "name": "SYSTEM_CRM"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "CRM-DB01-WP1",
            "hostid": "11626",
            "maintenance_status": "0",
            "name": "CRM-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "249858",
            "key_": "service.info[\"SQLSERVERAGENT\",state]",
            "lastvalue": "6",
            "name": "State of service \"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685697798",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98123",
        "triggerid": "99794",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "99828": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/SB-DB01-WS1/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "SB-DB01-WS1",
            "hostid": "11627",
            "maintenance_status": "0",
            "name": "SB-DB01-WS1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "249978",
            "key_": "vm.memory.util",
            "lastvalue": "95.29767327527033",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1685697858",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "99828",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "99946": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/RSK-DB01-WP1/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "RSK-DB01-WP1",
            "hostid": "11632",
            "maintenance_status": "0",
            "name": "RSK-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "250311",
            "key_": "vm.memory.util",
            "lastvalue": "92.68599861348883",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686517671",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "99946",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100014": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/RG-DB01-WP1/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "RG-DB01-WP1",
            "hostid": "11635",
            "maintenance_status": "0",
            "name": "RG-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "250508",
            "key_": "vm.memory.util",
            "lastvalue": "97.74015053370317",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686079748",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "100014",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100058": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/KZWSQLBIZT02/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLBIZT02",
            "hostid": "11638",
            "maintenance_status": "0",
            "name": "KZWSQLBIZT02",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "250638",
            "key_": "vm.memory.util",
            "lastvalue": "90.31210967400311",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1685697618",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "100058",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100080": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/KZWSQLBIZT01/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLBIZT01",
            "hostid": "11639",
            "maintenance_status": "0",
            "name": "KZWSQLBIZT01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "250703",
            "key_": "vm.memory.util",
            "lastvalue": "98.15619371632704",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1685697863",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "100080",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100532": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "(C:): Disk space is low",
        "error": "",
        "event_name": "(C:): Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"C:\"}%)",
        "expression": "last(/KZWSSQL01/vfs.fs.size[C:,pused])>80 and\r\n((last(/KZWSSQL01/vfs.fs.size[C:,total])-last(/KZWSSQL01/vfs.fs.size[C:,used]))<10G or timeleft(/KZWSSQL01/vfs.fs.size[C:,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "82",
            "name": "SITB"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSSQL01",
            "hostid": "11590",
            "maintenance_status": "0",
            "name": "KZWSSQL01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "252558",
            "key_": "vfs.fs.size[C:,pused]",
            "lastvalue": "88.650061",
            "name": "(C:): Space utilization"
          },
          {
            "itemid": "252560",
            "key_": "vfs.fs.size[C:,total]",
            "lastvalue": "85530243072",
            "name": "(C:): Total space"
          },
          {
            "itemid": "252562",
            "key_": "vfs.fs.size[C:,used]",
            "lastvalue": "75822612480",
            "name": "(C:): Used space"
          }
        ],
        "lastchange": "1685701402",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "100532",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100795": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQLCL03/service.info[\"SQLSERVERAGENT\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "91",
            "name": "SYSTEM_CREDILOGIC"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLCL03",
            "hostid": "11615",
            "maintenance_status": "0",
            "name": "KZWSQLCL03",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "254098",
            "key_": "service.info[\"SQLSERVERAGENT\",state]",
            "lastvalue": "255",
            "name": "State of service \"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685881198",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98123",
        "triggerid": "100795",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100796": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQLCL03/service.info[\"MSSQLSERVER\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "91",
            "name": "SYSTEM_CREDILOGIC"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLCL03",
            "hostid": "11615",
            "maintenance_status": "0",
            "name": "KZWSQLCL03",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "254097",
            "key_": "service.info[\"MSSQLSERVER\",state]",
            "lastvalue": "255",
            "name": "State of service \"MSSQLSERVER\" (SQL Server (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685881197",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98124",
        "triggerid": "100796",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100799": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQLIDM01/service.info[\"SQLSERVERAGENT\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "82",
            "name": "SITB"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLIDM01",
            "hostid": "11586",
            "maintenance_status": "0",
            "name": "KZWSQLIDM01",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "254102",
            "key_": "service.info[\"SQLSERVERAGENT\",state]",
            "lastvalue": "255",
            "name": "State of service \"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685881202",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98123",
        "triggerid": "100799",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100800": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQLIDM01/service.info[\"MSSQLSERVER\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "82",
            "name": "SITB"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLIDM01",
            "hostid": "11586",
            "maintenance_status": "0",
            "name": "KZWSQLIDM01",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "254101",
            "key_": "service.info[\"MSSQLSERVER\",state]",
            "lastvalue": "255",
            "name": "State of service \"MSSQLSERVER\" (SQL Server (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685881201",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98124",
        "triggerid": "100800",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100801": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQLIDM02/service.info[\"SQLSERVERAGENT\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "82",
            "name": "SITB"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLIDM02",
            "hostid": "11583",
            "maintenance_status": "0",
            "name": "KZWSQLIDM02",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "254104",
            "key_": "service.info[\"SQLSERVERAGENT\",state]",
            "lastvalue": "255",
            "name": "State of service \"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685881204",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98123",
        "triggerid": "100801",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100802": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQLIDM02/service.info[\"MSSQLSERVER\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "82",
            "name": "SITB"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLIDM02",
            "hostid": "11583",
            "maintenance_status": "0",
            "name": "KZWSQLIDM02",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "254103",
            "key_": "service.info[\"MSSQLSERVER\",state]",
            "lastvalue": "255",
            "name": "State of service \"MSSQLSERVER\" (SQL Server (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685881203",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98124",
        "triggerid": "100802",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100811": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQL03/service.info[\"SQLSERVERAGENT\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQL03",
            "hostid": "11628",
            "maintenance_status": "0",
            "name": "KZWSQL03",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "254114",
            "key_": "service.info[\"SQLSERVERAGENT\",state]",
            "lastvalue": "255",
            "name": "State of service \"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685885054",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98123",
        "triggerid": "100811",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100812": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQL03/service.info[\"MSSQLSERVER\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQL03",
            "hostid": "11628",
            "maintenance_status": "0",
            "name": "KZWSQL03",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "254113",
            "key_": "service.info[\"MSSQLSERVER\",state]",
            "lastvalue": "255",
            "name": "State of service \"MSSQLSERVER\" (SQL Server (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685885053",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98124",
        "triggerid": "100812",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100817": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQLCL04/service.info[\"SQLSERVERAGENT\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "91",
            "name": "SYSTEM_CREDILOGIC"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLCL04",
            "hostid": "11605",
            "maintenance_status": "0",
            "name": "KZWSQLCL04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "254120",
            "key_": "service.info[\"SQLSERVERAGENT\",state]",
            "lastvalue": "255",
            "name": "State of service \"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685885060",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98123",
        "triggerid": "100817",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100818": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQLCL04/service.info[\"MSSQLSERVER\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "91",
            "name": "SYSTEM_CREDILOGIC"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLCL04",
            "hostid": "11605",
            "maintenance_status": "0",
            "name": "KZWSQLCL04",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "254119",
            "key_": "service.info[\"MSSQLSERVER\",state]",
            "lastvalue": "255",
            "name": "State of service \"MSSQLSERVER\" (SQL Server (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685885059",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98124",
        "triggerid": "100818",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100827": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQLREP01/service.info[\"SQLSERVERAGENT\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLREP01",
            "hostid": "11582",
            "maintenance_status": "0",
            "name": "KZWSQLREP01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "254130",
            "key_": "service.info[\"SQLSERVERAGENT\",state]",
            "lastvalue": "255",
            "name": "State of service \"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685885070",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98123",
        "triggerid": "100827",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "100828": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQLREP01/service.info[\"MSSQLSERVER\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLREP01",
            "hostid": "11582",
            "maintenance_status": "0",
            "name": "KZWSQLREP01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "254129",
            "key_": "service.info[\"MSSQLSERVER\",state]",
            "lastvalue": "255",
            "name": "State of service \"MSSQLSERVER\" (SQL Server (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685885069",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98124",
        "triggerid": "100828",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "101198": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/BGB-DB02-WP2/service.info[\"SQLSERVERAGENT\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "51",
            "name": "DC_KUNAEVA_PROCESSING"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "BGB-DB02-WP2",
            "hostid": "11656",
            "maintenance_status": "0",
            "name": "BGB-DB02-WP2",
            "proxy_hostid": "10568",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "255242",
            "key_": "service.info[\"SQLSERVERAGENT\",state]",
            "lastvalue": "6",
            "name": "State of service \"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685939522",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98123",
        "triggerid": "101198",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "101433": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/WAY-APP07-WT1/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "50",
            "name": "DC_NAURYZBAY_PROCESSING"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "WAY-APP07-WT1",
            "hostid": "11653",
            "maintenance_status": "0",
            "name": "WAY-APP07-WT1",
            "proxy_hostid": "10567",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "255930",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1685940450",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "53504",
        "triggerid": "101433",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "101570": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/WAY-JOB01-WP2/vm.memory.util,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "51",
            "name": "DC_KUNAEVA_PROCESSING"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "WAY-JOB01-WP2",
            "hostid": "11665",
            "maintenance_status": "0",
            "name": "WAY-JOB01-WP2",
            "proxy_hostid": "10568",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "256411",
            "key_": "vm.memory.util",
            "lastvalue": "98.39992445995304",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1685941591",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22465",
        "triggerid": "101570",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "101716": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/CL-DB02-WT2/service.info[\"SQLSERVERAGENT\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "53",
            "name": "DC_KUNAEV_DEV_TEST"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "91",
            "name": "SYSTEM_CREDILOGIC"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "CL-DB02-WT2",
            "hostid": "11667",
            "maintenance_status": "0",
            "name": "CL-DB02-WT2",
            "proxy_hostid": "10566",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "256957",
            "key_": "service.info[\"SQLSERVERAGENT\",state]",
            "lastvalue": "0",
            "name": "State of service \"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685958637",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98123",
        "triggerid": "101716",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "101717": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/CL-DB02-WT2/service.info[\"MSSQLSERVER\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "53",
            "name": "DC_KUNAEV_DEV_TEST"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "91",
            "name": "SYSTEM_CREDILOGIC"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "CL-DB02-WT2",
            "hostid": "11667",
            "maintenance_status": "0",
            "name": "CL-DB02-WT2",
            "proxy_hostid": "10566",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "256956",
            "key_": "service.info[\"MSSQLSERVER\",state]",
            "lastvalue": "0",
            "name": "State of service \"MSSQLSERVER\" (SQL Server (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685958636",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98124",
        "triggerid": "101717",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "101727": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/CL-DB02-WT2/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "53",
            "name": "DC_KUNAEV_DEV_TEST"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "91",
            "name": "SYSTEM_CREDILOGIC"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "CL-DB02-WT2",
            "hostid": "11667",
            "maintenance_status": "0",
            "name": "CL-DB02-WT2",
            "proxy_hostid": "10566",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "257022",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686113322",
        "manual_close": "1",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22466",
        "triggerid": "101727",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "102584": {
        "comments": "Two conditions should match: First, space utilization should be above 90.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 5G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "WSUS(F:): Disk space is critically low",
        "error": "",
        "event_name": "WSUS(F:): Disk space is critically low (used > {$VFS.FS.PUSED.MAX.CRIT:\"F:\"}%)",
        "expression": "last(/KZF06WFS07/vfs.fs.size[F:,pused])>90 and\r\n((last(/KZF06WFS07/vfs.fs.size[F:,total])-last(/KZF06WFS07/vfs.fs.size[F:,used]))<5G or timeleft(/KZF06WFS07/vfs.fs.size[F:,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "32",
            "name": "FILIAL_06_Almaty"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF06WFS07",
            "hostid": "11677",
            "maintenance_status": "0",
            "name": "KZF06WFS07",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "259519",
            "key_": "vfs.fs.size[F:,pused]",
            "lastvalue": "99.943586",
            "name": "WSUS(F:): Space utilization"
          },
          {
            "itemid": "259522",
            "key_": "vfs.fs.size[F:,total]",
            "lastvalue": "599550590976",
            "name": "WSUS(F:): Total space"
          },
          {
            "itemid": "259525",
            "key_": "vfs.fs.size[F:,used]",
            "lastvalue": "599212359680",
            "name": "WSUS(F:): Used space"
          }
        ],
        "lastchange": "1685960425",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "102584",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "102590": {
        "comments": "Two conditions should match: First, space utilization should be above 90.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 5G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "WSUS(F:): Disk space is critically low",
        "error": "",
        "event_name": "WSUS(F:): Disk space is critically low (used > {$VFS.FS.PUSED.MAX.CRIT:\"F:\"}%)",
        "expression": "last(/KZF06WFS01/vfs.fs.size[F:,pused])>90 and\r\n((last(/KZF06WFS01/vfs.fs.size[F:,total])-last(/KZF06WFS01/vfs.fs.size[F:,used]))<5G or timeleft(/KZF06WFS01/vfs.fs.size[F:,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "32",
            "name": "FILIAL_06_Almaty"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZF06WFS01",
            "hostid": "11678",
            "maintenance_status": "0",
            "name": "KZF06WFS01",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "259544",
            "key_": "vfs.fs.size[F:,pused]",
            "lastvalue": "99.944007",
            "name": "WSUS(F:): Space utilization"
          },
          {
            "itemid": "259547",
            "key_": "vfs.fs.size[F:,total]",
            "lastvalue": "599550590976",
            "name": "WSUS(F:): Total space"
          },
          {
            "itemid": "259550",
            "key_": "vfs.fs.size[F:,used]",
            "lastvalue": "599214886912",
            "name": "WSUS(F:): Used space"
          }
        ],
        "lastchange": "1685960390",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "102590",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "102640": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQLSOFTCOL01/service.info[\"SQLSERVERAGENT\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "105",
            "name": "SYSTEM_UVRK"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLSOFTCOL01",
            "hostid": "11594",
            "maintenance_status": "0",
            "name": "KZWSQLSOFTCOL01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "260320",
            "key_": "service.info[\"SQLSERVERAGENT\",state]",
            "lastvalue": "255",
            "name": "State of service \"SQLSERVERAGENT\" (SQL Server Agent (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685960680",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98123",
        "triggerid": "102640",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "102641": {
        "comments": "The service has a state other than \"Running\" for the last three times.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running",
        "error": "",
        "event_name": "\"MSSQLSERVER\" (SQL Server (MSSQLSERVER)) is not running (startup type automatic)",
        "expression": "min(/KZWSQLSOFTCOL01/service.info[\"MSSQLSERVER\",state],#3)<>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "105",
            "name": "SYSTEM_UVRK"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZWSQLSOFTCOL01",
            "hostid": "11594",
            "maintenance_status": "0",
            "name": "KZWSQLSOFTCOL01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "260319",
            "key_": "service.info[\"MSSQLSERVER\",state]",
            "lastvalue": "255",
            "name": "State of service \"MSSQLSERVER\" (SQL Server (MSSQLSERVER))"
          }
        ],
        "lastchange": "1685960679",
        "manual_close": "0",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "98124",
        "triggerid": "102641",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "104233": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/home: Disk space is low",
        "error": "",
        "event_name": "/home: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/home\"}%)",
        "expression": "last(/kzlappmpi01/vfs.fs.size[/home,pused])>80 and\r\n((last(/kzlappmpi01/vfs.fs.size[/home,total])-last(/kzlappmpi01/vfs.fs.size[/home,used]))<10G or timeleft(/kzlappmpi01/vfs.fs.size[/home,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "50",
            "name": "DC_NAURYZBAY_PROCESSING"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappmpi01",
            "hostid": "11711",
            "maintenance_status": "0",
            "name": "kzlappmpi01",
            "proxy_hostid": "10567",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "265048",
            "key_": "vfs.fs.size[/home,pused]",
            "lastvalue": "86.385941",
            "name": "/home: Space utilization"
          },
          {
            "itemid": "265059",
            "key_": "vfs.fs.size[/home,total]",
            "lastvalue": "8579448832",
            "name": "/home: Total space"
          },
          {
            "itemid": "265070",
            "key_": "vfs.fs.size[/home,used]",
            "lastvalue": "7411437568",
            "name": "/home: Used space"
          }
        ],
        "lastchange": "1686048470",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "104233",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "108279": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/EXT-DNS02-WP2/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "EXT-DNS02-WP2",
            "hostid": "11811",
            "maintenance_status": "0",
            "name": "EXT-DNS02-WP2",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "274067",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686050687",
        "manual_close": "1",
        "opdata": "",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22466",
        "triggerid": "108279",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "108543": {
        "comments": "The full backup has not been executed for a long time.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "MSSQL DB 'BranchCash': Full backup is old",
        "error": "",
        "event_name": "MSSQL DB 'BranchCash': Full backup older than {$MSSQL.BACKUP_FULL.CRIT:\"BranchCash\"}",
        "expression": "last(/EKR-DB01-WP1/mssql.backup.full[\"BranchCash\"])>10d",
        "flags": "4",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "79",
            "name": "IPTADMIN"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "EKR-DB01-WP1",
            "hostid": "10622",
            "maintenance_status": "0",
            "name": "EKR-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "274476",
            "key_": "mssql.backup.full[\"BranchCash\"]",
            "lastvalue": "0",
            "name": "MSSQL DB 'BranchCash': Last full backup (time ago)"
          }
        ],
        "lastchange": "1686050905",
        "manual_close": "1",
        "opdata": "Time since last backup: {ITEM.LASTVALUE1}",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "108543",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "108544": {
        "comments": "The full backup has not been executed for a long time.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "MSSQL DB 'proteam': Full backup is old",
        "error": "",
        "event_name": "MSSQL DB 'proteam': Full backup older than {$MSSQL.BACKUP_FULL.CRIT:\"proteam\"}",
        "expression": "last(/EKR-DB01-WP1/mssql.backup.full[\"proteam\"])>10d",
        "flags": "4",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "79",
            "name": "IPTADMIN"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "EKR-DB01-WP1",
            "hostid": "10622",
            "maintenance_status": "0",
            "name": "EKR-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "274483",
            "key_": "mssql.backup.full[\"proteam\"]",
            "lastvalue": "12139881",
            "name": "MSSQL DB 'proteam': Last full backup (time ago)"
          }
        ],
        "lastchange": "1686050905",
        "manual_close": "1",
        "opdata": "Time since last backup: {ITEM.LASTVALUE1}",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "108544",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "108545": {
        "comments": "The full backup has not been executed for a long time.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "MSSQL DB 'BranchCashtest': Full backup is old",
        "error": "",
        "event_name": "MSSQL DB 'BranchCashtest': Full backup older than {$MSSQL.BACKUP_FULL.CRIT:\"BranchCashtest\"}",
        "expression": "last(/EKR-DB01-WP1/mssql.backup.full[\"BranchCashtest\"])>10d",
        "flags": "4",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "79",
            "name": "IPTADMIN"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "EKR-DB01-WP1",
            "hostid": "10622",
            "maintenance_status": "0",
            "name": "EKR-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "274490",
            "key_": "mssql.backup.full[\"BranchCashtest\"]",
            "lastvalue": "0",
            "name": "MSSQL DB 'BranchCashtest': Last full backup (time ago)"
          }
        ],
        "lastchange": "1686050905",
        "manual_close": "1",
        "opdata": "Time since last backup: {ITEM.LASTVALUE1}",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "108545",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "108551": {
        "comments": "The log backup has not been executed for a long time.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "MSSQL DB 'BranchCash': Log backup is old",
        "error": "",
        "event_name": "MSSQL DB 'BranchCash': Log backup older than {$MSSQL.BACKUP_LOG.CRIT:\"BranchCash\"}",
        "expression": "last(/EKR-DB01-WP1/mssql.backup.log[\"BranchCash\"])>8h",
        "flags": "4",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "79",
            "name": "IPTADMIN"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "EKR-DB01-WP1",
            "hostid": "10622",
            "maintenance_status": "0",
            "name": "EKR-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "274475",
            "key_": "mssql.backup.log[\"BranchCash\"]",
            "lastvalue": "0",
            "name": "MSSQL DB 'BranchCash': Last log backup"
          }
        ],
        "lastchange": "1686050905",
        "manual_close": "1",
        "opdata": "Time since last backup: {ITEM.LASTVALUE1}",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "108551",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "108552": {
        "comments": "The log backup has not been executed for a long time.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "MSSQL DB 'proteam': Log backup is old",
        "error": "",
        "event_name": "MSSQL DB 'proteam': Log backup older than {$MSSQL.BACKUP_LOG.CRIT:\"proteam\"}",
        "expression": "last(/EKR-DB01-WP1/mssql.backup.log[\"proteam\"])>8h",
        "flags": "4",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "79",
            "name": "IPTADMIN"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "EKR-DB01-WP1",
            "hostid": "10622",
            "maintenance_status": "0",
            "name": "EKR-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "274482",
            "key_": "mssql.backup.log[\"proteam\"]",
            "lastvalue": "12065300",
            "name": "MSSQL DB 'proteam': Last log backup"
          }
        ],
        "lastchange": "1686050905",
        "manual_close": "1",
        "opdata": "Time since last backup: {ITEM.LASTVALUE1}",
        "priority": "4",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "108552",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "108578": {
        "comments": "The last run of the job has failed.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "MSSQL Job 'DBA.UpdateStat': Failed to run",
        "error": "",
        "event_name": "",
        "expression": "last(/EKR-DB01-WP1/mssql.job.runstatus[\"DBA.UpdateStat\"])=0",
        "flags": "4",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "79",
            "name": "IPTADMIN"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "EKR-DB01-WP1",
            "hostid": "10622",
            "maintenance_status": "0",
            "name": "EKR-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "274583",
            "key_": "mssql.job.runstatus[\"DBA.UpdateStat\"]",
            "lastvalue": "0",
            "name": "MSSQL Job 'DBA.UpdateStat': Run status"
          }
        ],
        "lastchange": "1686050903",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "108578",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "108579": {
        "comments": "The last run of the job has failed.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "MSSQL Job 'DBA.Rebuild': Failed to run",
        "error": "",
        "event_name": "",
        "expression": "last(/EKR-DB01-WP1/mssql.job.runstatus[\"DBA.Rebuild\"])=0",
        "flags": "4",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "79",
            "name": "IPTADMIN"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "EKR-DB01-WP1",
            "hostid": "10622",
            "maintenance_status": "0",
            "name": "EKR-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "274590",
            "key_": "mssql.job.runstatus[\"DBA.Rebuild\"]",
            "lastvalue": "0",
            "name": "MSSQL Job 'DBA.Rebuild': Run status"
          }
        ],
        "lastchange": "1686050903",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "108579",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "108580": {
        "comments": "The last run of the job has failed.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "MSSQL Job 'DBA.UnusedIndexes': Failed to run",
        "error": "",
        "event_name": "",
        "expression": "last(/EKR-DB01-WP1/mssql.job.runstatus[\"DBA.UnusedIndexes\"])=0",
        "flags": "4",
        "groups": [
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "24",
            "name": "Windows servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "76",
            "name": "DATABASE_MSSQL"
          },
          {
            "groupid": "79",
            "name": "IPTADMIN"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "EKR-DB01-WP1",
            "hostid": "10622",
            "maintenance_status": "0",
            "name": "EKR-DB01-WP1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "274597",
            "key_": "mssql.job.runstatus[\"DBA.UnusedIndexes\"]",
            "lastvalue": "0",
            "name": "MSSQL Job 'DBA.UnusedIndexes': Run status"
          }
        ],
        "lastchange": "1686050903",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "108580",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "108738": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/var: Disk space is low",
        "error": "",
        "event_name": "/var: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/var\"}%)",
        "expression": "last(/tse-app01-lp2/vfs.fs.size[/var,pused])>80 and\r\n((last(/tse-app01-lp2/vfs.fs.size[/var,total])-last(/tse-app01-lp2/vfs.fs.size[/var,used]))<10G or timeleft(/tse-app01-lp2/vfs.fs.size[/var,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "51",
            "name": "DC_KUNAEVA_PROCESSING"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "tse-app01-lp2",
            "hostid": "11796",
            "maintenance_status": "0",
            "name": "tse-app01-lp2",
            "proxy_hostid": "10568",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "274870",
            "key_": "vfs.fs.size[/var,pused]",
            "lastvalue": "86.109323",
            "name": "/var: Space utilization"
          },
          {
            "itemid": "274881",
            "key_": "vfs.fs.size[/var,total]",
            "lastvalue": "8579448832",
            "name": "/var: Total space"
          },
          {
            "itemid": "274892",
            "key_": "vfs.fs.size[/var,used]",
            "lastvalue": "7387705344",
            "name": "/var: Used space"
          }
        ],
        "lastchange": "1686053192",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "108738",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "110215": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/: Disk space is low",
        "error": "",
        "event_name": "/: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/\"}%)",
        "expression": "last(/ors-app02-lp2/vfs.fs.size[/,pused])>80 and\r\n((last(/ors-app02-lp2/vfs.fs.size[/,total])-last(/ors-app02-lp2/vfs.fs.size[/,used]))<10G or timeleft(/ors-app02-lp2/vfs.fs.size[/,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "51",
            "name": "DC_KUNAEVA_PROCESSING"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "ors-app02-lp2",
            "hostid": "11778",
            "maintenance_status": "0",
            "name": "ors-app02-lp2",
            "proxy_hostid": "10568",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "277087",
            "key_": "vfs.fs.size[/,pused]",
            "lastvalue": "87.564462",
            "name": "/: Space utilization"
          },
          {
            "itemid": "277098",
            "key_": "vfs.fs.size[/,total]",
            "lastvalue": "21464350720",
            "name": "/: Total space"
          },
          {
            "itemid": "277109",
            "key_": "vfs.fs.size[/,used]",
            "lastvalue": "18795143168",
            "name": "/: Used space"
          }
        ],
        "lastchange": "1686053189",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "110215",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "110266": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/usr: Disk space is low",
        "error": "",
        "event_name": "/usr: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/usr\"}%)",
        "expression": "last(/os-log02-lp2/vfs.fs.size[/usr,pused])>80 and\r\n((last(/os-log02-lp2/vfs.fs.size[/usr,total])-last(/os-log02-lp2/vfs.fs.size[/usr,used]))<10G or timeleft(/os-log02-lp2/vfs.fs.size[/usr,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "51",
            "name": "DC_KUNAEVA_PROCESSING"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "os-log02-lp2",
            "hostid": "11779",
            "maintenance_status": "0",
            "name": "os-log02-lp2",
            "proxy_hostid": "10568",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "277159",
            "key_": "vfs.fs.size[/usr,pused]",
            "lastvalue": "83.099623",
            "name": "/usr: Space utilization"
          },
          {
            "itemid": "277170",
            "key_": "vfs.fs.size[/usr,total]",
            "lastvalue": "7111442432",
            "name": "/usr: Total space"
          },
          {
            "itemid": "277181",
            "key_": "vfs.fs.size[/usr,used]",
            "lastvalue": "5909581824",
            "name": "/usr: Used space"
          }
        ],
        "lastchange": "1686053190",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "110266",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "112283": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/kzlappdynes02/vm.memory.utilization,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappdynes02",
            "hostid": "11841",
            "maintenance_status": "0",
            "name": "kzlappdynes02",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "282705",
            "key_": "vm.memory.utilization",
            "lastvalue": "92.061039",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686118844",
        "manual_close": "0",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22376",
        "triggerid": "112283",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "112376": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/kzlappozliveadapter02/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "82",
            "name": "SITB"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappozliveadapter02",
            "hostid": "11845",
            "maintenance_status": "0",
            "name": "kzlappozliveadapter02",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "283003",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686119083",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22377",
        "triggerid": "112376",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "112537": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/kzlwebozui02/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "82",
            "name": "SITB"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlwebozui02",
            "hostid": "11852",
            "maintenance_status": "0",
            "name": "kzlwebozui02",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "283521",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686119061",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22377",
        "triggerid": "112537",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "113092": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlappapm02/system.sw.os,#1)<>last(/kzlappapm02/system.sw.os,#2) and length(last(/kzlappapm02/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappapm02",
            "hostid": "11875",
            "maintenance_status": "0",
            "name": "kzlappapm02",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "285236",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521636",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22373",
        "triggerid": "113092",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "113276": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlsftp02/system.sw.os,#1)<>last(/kzlsftp02/system.sw.os,#2) and length(last(/kzlsftp02/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlsftp02",
            "hostid": "11884",
            "maintenance_status": "0",
            "name": "kzlsftp02",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "285828",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686522228",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22373",
        "triggerid": "113276",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "113322": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlzabbix02/system.sw.os,#1)<>last(/kzlzabbix02/system.sw.os,#2) and length(last(/kzlzabbix02/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "4",
            "name": "Zabbix servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlzabbix02",
            "hostid": "11886",
            "maintenance_status": "0",
            "name": "kzlzabbix02",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "285976",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 4.18.0-477.13.1.el8_8.x86_64 (mockbuild@x86-vm-08.build.eng.bos.redhat.com) (gcc version 8.5.0 20210514 (Red Hat 8.5.0-18) (GCC)) #1 SMP Thu May 18 10:27:05 EDT 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686522376",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22373",
        "triggerid": "113322",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "114861": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzldbbnks02/system.sw.os,#1)<>last(/kzldbbnks02/system.sw.os,#2) and length(last(/kzldbbnks02/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "75",
            "name": "DATABASE_PostgreSQL"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzldbbnks02",
            "hostid": "11893",
            "maintenance_status": "0",
            "name": "kzldbbnks02",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "288403",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521203",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22373",
        "triggerid": "114861",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "114884": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlmesbrokcl02/system.sw.os,#1)<>last(/kzlmesbrokcl02/system.sw.os,#2) and length(last(/kzlmesbrokcl02/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "91",
            "name": "SYSTEM_CREDILOGIC"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlmesbrokcl02",
            "hostid": "11894",
            "maintenance_status": "0",
            "name": "kzlmesbrokcl02",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "288477",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521277",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22373",
        "triggerid": "114884",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "116181": {
        "comments": "Two conditions should match: First, space utilization should be above 90.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 5G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/home: Disk space is critically low",
        "error": "",
        "event_name": "/home: Disk space is critically low (used > {$VFS.FS.PUSED.MAX.CRIT:\"/home\"}%)",
        "expression": "last(/crd-web02-lp2/vfs.fs.size[/home,pused])>90 and\r\n((last(/crd-web02-lp2/vfs.fs.size[/home,total])-last(/crd-web02-lp2/vfs.fs.size[/home,used]))<5G or timeleft(/crd-web02-lp2/vfs.fs.size[/home,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "crd-web02-lp2",
            "hostid": "11824",
            "maintenance_status": "0",
            "name": "crd-web02-lp2",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "290440",
            "key_": "vfs.fs.size[/home,pused]",
            "lastvalue": "90.660711",
            "name": "/home: Space utilization"
          },
          {
            "itemid": "290450",
            "key_": "vfs.fs.size[/home,total]",
            "lastvalue": "8579448832",
            "name": "/home: Total space"
          },
          {
            "itemid": "290460",
            "key_": "vfs.fs.size[/home,used]",
            "lastvalue": "7778189312",
            "name": "/home: Used space"
          }
        ],
        "lastchange": "1686154300",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "116181",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "116190": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/opt: Disk space is low",
        "error": "",
        "event_name": "/opt: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/opt\"}%)",
        "expression": "last(/crd-web02-lp2/vfs.fs.size[/opt,pused])>80 and\r\n((last(/crd-web02-lp2/vfs.fs.size[/opt,total])-last(/crd-web02-lp2/vfs.fs.size[/opt,used]))<10G or timeleft(/crd-web02-lp2/vfs.fs.size[/opt,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "crd-web02-lp2",
            "hostid": "11824",
            "maintenance_status": "0",
            "name": "crd-web02-lp2",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "290439",
            "key_": "vfs.fs.size[/opt,pused]",
            "lastvalue": "83.591237",
            "name": "/opt: Space utilization"
          },
          {
            "itemid": "290449",
            "key_": "vfs.fs.size[/opt,total]",
            "lastvalue": "12874416128",
            "name": "/opt: Total space"
          },
          {
            "itemid": "290459",
            "key_": "vfs.fs.size[/opt,used]",
            "lastvalue": "10761883648",
            "name": "/opt: Used space"
          }
        ],
        "lastchange": "1686122449",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "116190",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "116350": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/data: Disk space is low",
        "error": "",
        "event_name": "/data: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/data\"}%)",
        "expression": "last(/kzlappapm01/vfs.fs.size[/data,pused])>80 and\r\n((last(/kzlappapm01/vfs.fs.size[/data,total])-last(/kzlappapm01/vfs.fs.size[/data,used]))<10G or timeleft(/kzlappapm01/vfs.fs.size[/data,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappapm01",
            "hostid": "11874",
            "maintenance_status": "0",
            "name": "kzlappapm01",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "290718",
            "key_": "vfs.fs.size[/data,pused]",
            "lastvalue": "84.841131",
            "name": "/data: Space utilization"
          },
          {
            "itemid": "290729",
            "key_": "vfs.fs.size[/data,total]",
            "lastvalue": "42139451392",
            "name": "/data: Total space"
          },
          {
            "itemid": "290740",
            "key_": "vfs.fs.size[/data,used]",
            "lastvalue": "33928744960",
            "name": "/data: Used space"
          }
        ],
        "lastchange": "1686337698",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "116350",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "116351": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/home/sftp/opt/tomcat7/logs: Disk space is low",
        "error": "",
        "event_name": "/home/sftp/opt/tomcat7/logs: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/home/sftp/opt/tomcat7/logs\"}%)",
        "expression": "last(/kzlappapm01/vfs.fs.size[/home/sftp/opt/tomcat7/logs,pused])>80 and\r\n((last(/kzlappapm01/vfs.fs.size[/home/sftp/opt/tomcat7/logs,total])-last(/kzlappapm01/vfs.fs.size[/home/sftp/opt/tomcat7/logs,used]))<10G or timeleft(/kzlappapm01/vfs.fs.size[/home/sftp/opt/tomcat7/logs,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappapm01",
            "hostid": "11874",
            "maintenance_status": "0",
            "name": "kzlappapm01",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "290719",
            "key_": "vfs.fs.size[/home/sftp/opt/tomcat7/logs,pused]",
            "lastvalue": "84.841131",
            "name": "/home/sftp/opt/tomcat7/logs: Space utilization"
          },
          {
            "itemid": "290730",
            "key_": "vfs.fs.size[/home/sftp/opt/tomcat7/logs,total]",
            "lastvalue": "42139451392",
            "name": "/home/sftp/opt/tomcat7/logs: Total space"
          },
          {
            "itemid": "290741",
            "key_": "vfs.fs.size[/home/sftp/opt/tomcat7/logs,used]",
            "lastvalue": "33928744960",
            "name": "/home/sftp/opt/tomcat7/logs: Used space"
          }
        ],
        "lastchange": "1686337699",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "116351",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "116821": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/home: Disk space is low",
        "error": "",
        "event_name": "/home: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/home\"}%)",
        "expression": "last(/kzlawx/vfs.fs.size[/home,pused])>80 and\r\n((last(/kzlawx/vfs.fs.size[/home,total])-last(/kzlawx/vfs.fs.size[/home,used]))<10G or timeleft(/kzlawx/vfs.fs.size[/home,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "49",
            "name": "DC_KUNAEVA_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlawx",
            "hostid": "11879",
            "maintenance_status": "0",
            "name": "kzlawx",
            "proxy_hostid": "10560",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "291471",
            "key_": "vfs.fs.size[/home,pused]",
            "lastvalue": "81.745466",
            "name": "/home: Space utilization"
          },
          {
            "itemid": "291481",
            "key_": "vfs.fs.size[/home,total]",
            "lastvalue": "8579448832",
            "name": "/home: Total space"
          },
          {
            "itemid": "291491",
            "key_": "vfs.fs.size[/home,used]",
            "lastvalue": "7013310464",
            "name": "/home: Used space"
          }
        ],
        "lastchange": "1686122451",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "116821",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "117490": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/crd-app01-ls1/vm.memory.utilization,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "crd-app01-ls1",
            "hostid": "11904",
            "maintenance_status": "0",
            "name": "crd-app01-ls1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "292732",
            "key_": "vm.memory.utilization",
            "lastvalue": "92.346649",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686538431",
        "manual_close": "0",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22376",
        "triggerid": "117490",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "118020": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/kzlappozapi01/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "82",
            "name": "SITB"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappozapi01",
            "hostid": "11927",
            "maintenance_status": "0",
            "name": "kzlappozapi01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "294436",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686126556",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22377",
        "triggerid": "118020",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "118227": {
        "comments": "For passive only agents, host availability is used with 3m as time threshold.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Zabbix agent is not available",
        "error": "",
        "event_name": "Zabbix agent is not available (for {$AGENT.TIMEOUT})",
        "expression": "max(/kzlwebozui01/zabbix[host,agent,available],3m)=0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "82",
            "name": "SITB"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlwebozui01",
            "hostid": "11936",
            "maintenance_status": "0",
            "name": "kzlwebozui01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "295102",
            "key_": "zabbix[host,agent,available]",
            "lastvalue": "0",
            "name": "Zabbix agent availability"
          }
        ],
        "lastchange": "1686126562",
        "manual_close": "1",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22377",
        "triggerid": "118227",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "119452": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/kzlapconfprod02/vm.memory.utilization,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlapconfprod02",
            "hostid": "11989",
            "maintenance_status": "0",
            "name": "kzlapconfprod02",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "298989",
            "key_": "vm.memory.utilization",
            "lastvalue": "93.896016",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686533228",
        "manual_close": "0",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22376",
        "triggerid": "119452",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "119587": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzldbbnks01/system.sw.os,#1)<>last(/kzldbbnks01/system.sw.os,#2) and length(last(/kzldbbnks01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "22",
            "name": "DATABASES"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "75",
            "name": "DATABASE_PostgreSQL"
          },
          {
            "groupid": "78",
            "name": "SYSTEM_Smartbank"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzldbbnks01",
            "hostid": "11995",
            "maintenance_status": "0",
            "name": "kzldbbnks01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "299407",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521407",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22373",
        "triggerid": "119587",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "119633": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlkhdetl01/system.sw.os,#1)<>last(/kzlkhdetl01/system.sw.os,#2) and length(last(/kzlkhdetl01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlkhdetl01",
            "hostid": "11997",
            "maintenance_status": "0",
            "name": "kzlkhdetl01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "299555",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521555",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22373",
        "triggerid": "119633",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "119656": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlintraportal01/system.sw.os,#1)<>last(/kzlintraportal01/system.sw.os,#2) and length(last(/kzlintraportal01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlintraportal01",
            "hostid": "11998",
            "maintenance_status": "0",
            "name": "kzlintraportal01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "299629",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521629",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22373",
        "triggerid": "119656",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "119679": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/kzlintraportal/system.sw.os,#1)<>last(/kzlintraportal/system.sw.os,#2) and length(last(/kzlintraportal/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlintraportal",
            "hostid": "11999",
            "maintenance_status": "0",
            "name": "kzlintraportal",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "299703",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521703",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22373",
        "triggerid": "119679",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "121082": {
        "comments": "Two conditions should match: First, space utilization should be above 90.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 5G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/cl_docs1: Disk space is critically low",
        "error": "",
        "event_name": "/cl_docs1: Disk space is critically low (used > {$VFS.FS.PUSED.MAX.CRIT:\"/cl_docs1\"}%)",
        "expression": "last(/kzlappcl01/vfs.fs.size[/cl_docs1,pused])>90 and\r\n((last(/kzlappcl01/vfs.fs.size[/cl_docs1,total])-last(/kzlappcl01/vfs.fs.size[/cl_docs1,used]))<5G or timeleft(/kzlappcl01/vfs.fs.size[/cl_docs1,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "91",
            "name": "SYSTEM_CREDILOGIC"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappcl01",
            "hostid": "11971",
            "maintenance_status": "0",
            "name": "kzlappcl01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "301930",
            "key_": "vfs.fs.size[/cl_docs1,pused]",
            "lastvalue": "100",
            "name": "/cl_docs1: Space utilization"
          },
          {
            "itemid": "301948",
            "key_": "vfs.fs.size[/cl_docs1,total]",
            "lastvalue": "1082046468096",
            "name": "/cl_docs1: Total space"
          },
          {
            "itemid": "301966",
            "key_": "vfs.fs.size[/cl_docs1,used]",
            "lastvalue": "1027157667840",
            "name": "/cl_docs1: Used space"
          }
        ],
        "lastchange": "1686562390",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "121082",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "121214": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/usr: Disk space is low",
        "error": "",
        "event_name": "/usr: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/usr\"}%)",
        "expression": "last(/kzlapjiraprod01.eub.kz/vfs.fs.size[/usr,pused])>80 and\r\n((last(/kzlapjiraprod01.eub.kz/vfs.fs.size[/usr,total])-last(/kzlapjiraprod01.eub.kz/vfs.fs.size[/usr,used]))<10G or timeleft(/kzlapjiraprod01.eub.kz/vfs.fs.size[/usr,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlapjiraprod01.eub.kz",
            "hostid": "11972",
            "maintenance_status": "0",
            "name": "kzlapjiraprod01.eub.kz",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "302134",
            "key_": "vfs.fs.size[/usr,pused]",
            "lastvalue": "83.937997",
            "name": "/usr: Space utilization"
          },
          {
            "itemid": "302142",
            "key_": "vfs.fs.size[/usr,total]",
            "lastvalue": "5546549248",
            "name": "/usr: Total space"
          },
          {
            "itemid": "302150",
            "key_": "vfs.fs.size[/usr,used]",
            "lastvalue": "4413448192",
            "name": "/usr: Used space"
          }
        ],
        "lastchange": "1686129950",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "121214",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "121350": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/opt/fis: Disk space is low",
        "error": "",
        "event_name": "/opt/fis: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/opt/fis\"}%)",
        "expression": "last(/kzlappfispreprod01/vfs.fs.size[/opt/fis,pused])>80 and\r\n((last(/kzlappfispreprod01/vfs.fs.size[/opt/fis,total])-last(/kzlappfispreprod01/vfs.fs.size[/opt/fis,used]))<10G or timeleft(/kzlappfispreprod01/vfs.fs.size[/opt/fis,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappfispreprod01",
            "hostid": "11925",
            "maintenance_status": "0",
            "name": "kzlappfispreprod01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "302322",
            "key_": "vfs.fs.size[/opt/fis,pused]",
            "lastvalue": "82.164918",
            "name": "/opt/fis: Space utilization"
          },
          {
            "itemid": "302333",
            "key_": "vfs.fs.size[/opt/fis,total]",
            "lastvalue": "32188141568",
            "name": "/opt/fis: Total space"
          },
          {
            "itemid": "302344",
            "key_": "vfs.fs.size[/opt/fis,used]",
            "lastvalue": "26447360000",
            "name": "/opt/fis: Used space"
          }
        ],
        "lastchange": "1686129953",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "121350",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "121405": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/var: Disk space is low",
        "error": "",
        "event_name": "/var: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/var\"}%)",
        "expression": "last(/kzlnsver/vfs.fs.size[/var,pused])>80 and\r\n((last(/kzlnsver/vfs.fs.size[/var,total])-last(/kzlnsver/vfs.fs.size[/var,used]))<10G or timeleft(/kzlnsver/vfs.fs.size[/var,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlnsver",
            "hostid": "11974",
            "maintenance_status": "0",
            "name": "kzlnsver",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "302458",
            "key_": "vfs.fs.size[/var,pused]",
            "lastvalue": "89.115302",
            "name": "/var: Space utilization"
          },
          {
            "itemid": "302465",
            "key_": "vfs.fs.size[/var,total]",
            "lastvalue": "8320901120",
            "name": "/var: Total space"
          },
          {
            "itemid": "302472",
            "key_": "vfs.fs.size[/var,used]",
            "lastvalue": "7032459264",
            "name": "/var: Used space"
          }
        ],
        "lastchange": "1686129958",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "121405",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "121650": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/usr: Disk space is low",
        "error": "",
        "event_name": "/usr: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/usr\"}%)",
        "expression": "last(/kzlsasctprod.eub.kz/vfs.fs.size[/usr,pused])>80 and\r\n((last(/kzlsasctprod.eub.kz/vfs.fs.size[/usr,total])-last(/kzlsasctprod.eub.kz/vfs.fs.size[/usr,used]))<10G or timeleft(/kzlsasctprod.eub.kz/vfs.fs.size[/usr,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "113",
            "name": "SYSTEM_SAS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlsasctprod.eub.kz",
            "hostid": "11977",
            "maintenance_status": "0",
            "name": "kzlsasctprod.eub.kz",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "302859",
            "key_": "vfs.fs.size[/usr,pused]",
            "lastvalue": "85.349088",
            "name": "/usr: Space utilization"
          },
          {
            "itemid": "302875",
            "key_": "vfs.fs.size[/usr,total]",
            "lastvalue": "5546549248",
            "name": "/usr: Total space"
          },
          {
            "itemid": "302891",
            "key_": "vfs.fs.size[/usr,used]",
            "lastvalue": "4487643136",
            "name": "/usr: Used space"
          }
        ],
        "lastchange": "1686129955",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "121650",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "122218": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/var/log: Disk space is low",
        "error": "",
        "event_name": "/var/log: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/var/log\"}%)",
        "expression": "last(/kzlsap01/vfs.fs.size[/var/log,pused])>80 and\r\n((last(/kzlsap01/vfs.fs.size[/var/log,total])-last(/kzlsap01/vfs.fs.size[/var/log,used]))<10G or timeleft(/kzlsap01/vfs.fs.size[/var/log,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlsap01",
            "hostid": "11934",
            "maintenance_status": "0",
            "name": "kzlsap01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "303598",
            "key_": "vfs.fs.size[/var/log,pused]",
            "lastvalue": "81.669401",
            "name": "/var/log: Space utilization"
          },
          {
            "itemid": "303610",
            "key_": "vfs.fs.size[/var/log,total]",
            "lastvalue": "4284481536",
            "name": "/var/log: Total space"
          },
          {
            "itemid": "303622",
            "key_": "vfs.fs.size[/var/log,used]",
            "lastvalue": "3499327488",
            "name": "/var/log: Used space"
          }
        ],
        "lastchange": "1686129958",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "122218",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "122270": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/usr: Disk space is low",
        "error": "",
        "event_name": "/usr: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/usr\"}%)",
        "expression": "last(/kzlsasmtprod.eub.kz/vfs.fs.size[/usr,pused])>80 and\r\n((last(/kzlsasmtprod.eub.kz/vfs.fs.size[/usr,total])-last(/kzlsasmtprod.eub.kz/vfs.fs.size[/usr,used]))<10G or timeleft(/kzlsasmtprod.eub.kz/vfs.fs.size[/usr,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "113",
            "name": "SYSTEM_SAS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlsasmtprod.eub.kz",
            "hostid": "11983",
            "maintenance_status": "0",
            "name": "kzlsasmtprod.eub.kz",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "303679",
            "key_": "vfs.fs.size[/usr,pused]",
            "lastvalue": "85.775438",
            "name": "/usr: Space utilization"
          },
          {
            "itemid": "303690",
            "key_": "vfs.fs.size[/usr,total]",
            "lastvalue": "5546549248",
            "name": "/usr: Total space"
          },
          {
            "itemid": "303701",
            "key_": "vfs.fs.size[/usr,used]",
            "lastvalue": "4510060544",
            "name": "/usr: Used space"
          }
        ],
        "lastchange": "1686129941",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "122270",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "123970": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/home: Disk space is low",
        "error": "",
        "event_name": "/home: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/home\"}%)",
        "expression": "last(/crm-app03-lp1/vfs.fs.size[/home,pused])>80 and\r\n((last(/crm-app03-lp1/vfs.fs.size[/home,total])-last(/crm-app03-lp1/vfs.fs.size[/home,used]))<10G or timeleft(/crm-app03-lp1/vfs.fs.size[/home,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          },
          {
            "groupid": "107",
            "name": "SYSTEM_CRM"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "crm-app03-lp1",
            "hostid": "11907",
            "maintenance_status": "0",
            "name": "crm-app03-lp1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "306143",
            "key_": "vfs.fs.size[/home,pused]",
            "lastvalue": "81.001169",
            "name": "/home: Space utilization"
          },
          {
            "itemid": "306154",
            "key_": "vfs.fs.size[/home,total]",
            "lastvalue": "8579448832",
            "name": "/home: Total space"
          },
          {
            "itemid": "306165",
            "key_": "vfs.fs.size[/home,used]",
            "lastvalue": "6949421056",
            "name": "/home: Used space"
          }
        ],
        "lastchange": "1686129945",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "123970",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "124115": {
        "comments": "Two conditions should match: First, space utilization should be above 90.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 5G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/opt: Disk space is critically low",
        "error": "",
        "event_name": "/opt: Disk space is critically low (used > {$VFS.FS.PUSED.MAX.CRIT:\"/opt\"}%)",
        "expression": "last(/srp-app01-lp1/vfs.fs.size[/opt,pused])>90 and\r\n((last(/srp-app01-lp1/vfs.fs.size[/opt,total])-last(/srp-app01-lp1/vfs.fs.size[/opt,used]))<5G or timeleft(/srp-app01-lp1/vfs.fs.size[/opt,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "srp-app01-lp1",
            "hostid": "11957",
            "maintenance_status": "0",
            "name": "srp-app01-lp1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "306362",
            "key_": "vfs.fs.size[/opt,pused]",
            "lastvalue": "98.182057",
            "name": "/opt: Space utilization"
          },
          {
            "itemid": "306373",
            "key_": "vfs.fs.size[/opt,total]",
            "lastvalue": "12874416128",
            "name": "/opt: Total space"
          },
          {
            "itemid": "306384",
            "key_": "vfs.fs.size[/opt,used]",
            "lastvalue": "12640366592",
            "name": "/opt: Used space"
          }
        ],
        "lastchange": "1686129924",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "124115",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "124410": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/data: Disk space is low",
        "error": "",
        "event_name": "/data: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/data\"}%)",
        "expression": "last(/kzlappnsd01/vfs.fs.size[/data,pused])>80 and\r\n((last(/kzlappnsd01/vfs.fs.size[/data,total])-last(/kzlappnsd01/vfs.fs.size[/data,used]))<10G or timeleft(/kzlappnsd01/vfs.fs.size[/data,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlappnsd01",
            "hostid": "11991",
            "maintenance_status": "0",
            "name": "kzlappnsd01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "306794",
            "key_": "vfs.fs.size[/data,pused]",
            "lastvalue": "91.853923",
            "name": "/data: Space utilization"
          },
          {
            "itemid": "306805",
            "key_": "vfs.fs.size[/data,total]",
            "lastvalue": "107319660544",
            "name": "/data: Total space"
          },
          {
            "itemid": "306816",
            "key_": "vfs.fs.size[/data,used]",
            "lastvalue": "98577551360",
            "name": "/data: Used space"
          }
        ],
        "lastchange": "1686461616",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "124410",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "124785": {
        "comments": "Two conditions should match: First, space utilization should be above 90.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 5G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/usr: Disk space is critically low",
        "error": "",
        "event_name": "/usr: Disk space is critically low (used > {$VFS.FS.PUSED.MAX.CRIT:\"/usr\"}%)",
        "expression": "last(/kzlintraportal/vfs.fs.size[/usr,pused])>90 and\r\n((last(/kzlintraportal/vfs.fs.size[/usr,total])-last(/kzlintraportal/vfs.fs.size[/usr,used]))<5G or timeleft(/kzlintraportal/vfs.fs.size[/usr,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "kzlintraportal",
            "hostid": "11999",
            "maintenance_status": "0",
            "name": "kzlintraportal",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "307353",
            "key_": "vfs.fs.size[/usr,pused]",
            "lastvalue": "92.287473",
            "name": "/usr: Space utilization"
          },
          {
            "itemid": "307363",
            "key_": "vfs.fs.size[/usr,total]",
            "lastvalue": "8575254528",
            "name": "/usr: Total space"
          },
          {
            "itemid": "307373",
            "key_": "vfs.fs.size[/usr,used]",
            "lastvalue": "7913885696",
            "name": "/usr: Used space"
          }
        ],
        "lastchange": "1686133553",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "124785",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "125107": {
        "comments": "The system is running out of free memory.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High memory utilization",
        "error": "",
        "event_name": "High memory utilization (>{$MEMORY.UTIL.MAX}% for 5m)",
        "expression": "min(/smp-app01-lp1/vm.memory.utilization,5m)>90",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "smp-app01-lp1",
            "hostid": "12009",
            "maintenance_status": "0",
            "name": "smp-app01-lp1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "307929",
            "key_": "vm.memory.utilization",
            "lastvalue": "97.518443",
            "name": "Memory utilization"
          }
        ],
        "lastchange": "1686216368",
        "manual_close": "0",
        "opdata": "",
        "priority": "3",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22376",
        "triggerid": "125107",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "125147": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/home: Disk space is low",
        "error": "",
        "event_name": "/home: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/home\"}%)",
        "expression": "last(/smp-app01-lp1/vfs.fs.size[/home,pused])>80 and\r\n((last(/smp-app01-lp1/vfs.fs.size[/home,total])-last(/smp-app01-lp1/vfs.fs.size[/home,used]))<10G or timeleft(/smp-app01-lp1/vfs.fs.size[/home,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "smp-app01-lp1",
            "hostid": "12009",
            "maintenance_status": "0",
            "name": "smp-app01-lp1",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "307983",
            "key_": "vfs.fs.size[/home,pused]",
            "lastvalue": "81.722646",
            "name": "/home: Space utilization"
          },
          {
            "itemid": "307994",
            "key_": "vfs.fs.size[/home,total]",
            "lastvalue": "8579448832",
            "name": "/home: Total space"
          },
          {
            "itemid": "308005",
            "key_": "vfs.fs.size[/home,used]",
            "lastvalue": "7011352576",
            "name": "/home: Used space"
          }
        ],
        "lastchange": "1686219985",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "125147",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "125953": {
        "comments": "Operating system description has changed. Possible reasons that system has been updated or replaced. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Operating system description has changed",
        "error": "",
        "event_name": "",
        "expression": "last(/KZLAPPAPI01/system.sw.os,#1)<>last(/KZLAPPAPI01/system.sw.os,#2) and length(last(/KZLAPPAPI01/system.sw.os))>0",
        "flags": "0",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZLAPPAPI01",
            "hostid": "11988",
            "maintenance_status": "0",
            "name": "KZLAPPAPI01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "309939",
            "key_": "system.sw.os",
            "lastvalue": "Linux version 3.10.0-1160.92.1.el7.x86_64 (mockbuild@x86-040.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-44) (GCC) ) #1 SMP Thu May 18 11:23:40 UTC 2023",
            "name": "Operating system"
          }
        ],
        "lastchange": "1686521139",
        "manual_close": "1",
        "opdata": "",
        "priority": "1",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "22373",
        "triggerid": "125953",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "125991": {
        "comments": "Two conditions should match: First, space utilization should be above 80.\r\n Second condition should be one of the following:\r\n - The disk free space is less than 10G.\r\n - The disk will be full in less than 24 hours.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "/var: Disk space is low",
        "error": "",
        "event_name": "/var: Disk space is low (used > {$VFS.FS.PUSED.MAX.WARN:\"/var\"}%)",
        "expression": "last(/KZLAPPAPI01/vfs.fs.size[/var,pused])>80 and\r\n((last(/KZLAPPAPI01/vfs.fs.size[/var,total])-last(/KZLAPPAPI01/vfs.fs.size[/var,used]))<10G or timeleft(/KZLAPPAPI01/vfs.fs.size[/var,pused],1h,100)<1d)",
        "flags": "4",
        "groups": [
          {
            "groupid": "2",
            "name": "Linux servers"
          },
          {
            "groupid": "48",
            "name": "DC_NAURYZBAY_PROD"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "KZLAPPAPI01",
            "hostid": "11988",
            "maintenance_status": "0",
            "name": "KZLAPPAPI01",
            "proxy_hostid": "10559",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "310003",
            "key_": "vfs.fs.size[/var,pused]",
            "lastvalue": "81.400626",
            "name": "/var: Space utilization"
          },
          {
            "itemid": "310013",
            "key_": "vfs.fs.size[/var,total]",
            "lastvalue": "8579448832",
            "name": "/var: Total space"
          },
          {
            "itemid": "310023",
            "key_": "vfs.fs.size[/var,used]",
            "lastvalue": "6983704576",
            "name": "/var: Used space"
          }
        ],
        "lastchange": "1686295623",
        "manual_close": "1",
        "opdata": "Space used: {ITEM.LASTVALUE3} of {ITEM.LASTVALUE2} ({ITEM.LASTVALUE1})",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "125991",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "126961": {
        "comments": "",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "High ICMP ping response time",
        "error": "",
        "event_name": "",
        "expression": "avg(/GATEWAY_RKO_908_FILIAL_9/icmppingsec,5m)>0.15",
        "flags": "0",
        "groups": [
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "GATEWAY_RKO_908_FILIAL_9",
            "hostid": "12053",
            "maintenance_status": "0",
            "name": "GATEWAY_RKO_908_FILIAL_9",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "311815",
            "key_": "icmppingsec",
            "lastvalue": "0.02818",
            "name": "ICMP response time"
          }
        ],
        "lastchange": "1686562088",
        "manual_close": "0",
        "opdata": "Value: {ITEM.LASTVALUE1}",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "21614",
        "triggerid": "126961",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "127092": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Fa0/13(): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/TRZ-BRANCH-CROSS-f1-SW-1/net.if.duplex[dot3StatsDuplexStatus.10013])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "36",
            "name": "FILIAL_10_Taraz"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "TRZ-BRANCH-CROSS-f1-SW-1",
            "hostid": "12028",
            "maintenance_status": "0",
            "name": "TRZ-BRANCH-CROSS-f1-SW-1",
            "proxy_hostid": "11141",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "312043",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10013]",
            "lastvalue": "2",
            "name": "Interface Fa0/13(): Duplex status"
          }
        ],
        "lastchange": "1686311383",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "127092",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "127308": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Fa0/40(POS): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/TRZ-BRANCH-CROSS-f1-SW-5/net.if.duplex[dot3StatsDuplexStatus.10040])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "36",
            "name": "FILIAL_10_Taraz"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "TRZ-BRANCH-CROSS-f1-SW-5",
            "hostid": "12029",
            "maintenance_status": "0",
            "name": "TRZ-BRANCH-CROSS-f1-SW-5",
            "proxy_hostid": "11141",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "312569",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10040]",
            "lastvalue": "2",
            "name": "Interface Fa0/40(POS): Duplex status"
          }
        ],
        "lastchange": "1686311384",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "127308",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "127312": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Fa0/44(POS): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/TRZ-BRANCH-CROSS-f1-SW-5/net.if.duplex[dot3StatsDuplexStatus.10044])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "36",
            "name": "FILIAL_10_Taraz"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "TRZ-BRANCH-CROSS-f1-SW-5",
            "hostid": "12029",
            "maintenance_status": "0",
            "name": "TRZ-BRANCH-CROSS-f1-SW-5",
            "proxy_hostid": "11141",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "312573",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10044]",
            "lastvalue": "2",
            "name": "Interface Fa0/44(POS): Duplex status"
          }
        ],
        "lastchange": "1686311384",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "127312",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "127777": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Fa0/19(): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/TRZ-BRANCH-CROSS-f2-SW-4/net.if.status[ifOperStatus.10019])=2 and (last(/TRZ-BRANCH-CROSS-f2-SW-4/net.if.status[ifOperStatus.10019],#1)<>last(/TRZ-BRANCH-CROSS-f2-SW-4/net.if.status[ifOperStatus.10019],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "36",
            "name": "FILIAL_10_Taraz"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "TRZ-BRANCH-CROSS-f2-SW-4",
            "hostid": "12032",
            "maintenance_status": "0",
            "name": "TRZ-BRANCH-CROSS-f2-SW-4",
            "proxy_hostid": "11141",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "313790",
            "key_": "net.if.status[ifOperStatus.10019]",
            "lastvalue": "2",
            "name": "Interface Fa0/19(): Operational status"
          }
        ],
        "lastchange": "1686540527",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/TRZ-BRANCH-CROSS-f2-SW-4/net.if.status[ifOperStatus.10019])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "127777",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "127871": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Fa0/8(): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/AKTAU-CAT-2/net.if.duplex[dot3StatsDuplexStatus.10008])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "37",
            "name": "FILIAL_11_Aktau"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "AKTAU-CAT-2",
            "hostid": "12035",
            "maintenance_status": "0",
            "name": "AKTAU-CAT-2",
            "proxy_hostid": "11164",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "314045",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10008]",
            "lastvalue": "2",
            "name": "Interface Fa0/8(): Duplex status"
          }
        ],
        "lastchange": "1686310910",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "127871",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "127872": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Fa0/10(): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/AKTAU-CAT-2/net.if.duplex[dot3StatsDuplexStatus.10010])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "37",
            "name": "FILIAL_11_Aktau"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "AKTAU-CAT-2",
            "hostid": "12035",
            "maintenance_status": "0",
            "name": "AKTAU-CAT-2",
            "proxy_hostid": "11164",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "314046",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10010]",
            "lastvalue": "2",
            "name": "Interface Fa0/10(): Duplex status"
          }
        ],
        "lastchange": "1686310910",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "127872",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "127879": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Fa0/23(): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/AKTAU-CAT-2/net.if.duplex[dot3StatsDuplexStatus.10023])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "37",
            "name": "FILIAL_11_Aktau"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "AKTAU-CAT-2",
            "hostid": "12035",
            "maintenance_status": "0",
            "name": "AKTAU-CAT-2",
            "proxy_hostid": "11164",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "314053",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10023]",
            "lastvalue": "2",
            "name": "Interface Fa0/23(): Duplex status"
          }
        ],
        "lastchange": "1686310910",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "127879",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "128157": {
        "comments": "This trigger expression works as follows:\r\n1. Can be triggered if operations status is down.\r\n2. 1=1 - user can redefine Context macro to value - 0. That marks this interface as not important. No new trigger will be fired if this interface is down.\r\n3. {TEMPLATE_NAME:METRIC.diff()}=1) - trigger fires only if operational status was up(1) sometime before. (So, do not fire 'ethernal off' interfaces.)\r\n\r\nWARNING: if closed manually - won't fire again on next poll, because of .diff.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Fa0/1(): Link down",
        "error": "",
        "event_name": "",
        "expression": "1=1 and last(/AKTAU-CAT-2/net.if.status[ifOperStatus.10001])=2 and (last(/AKTAU-CAT-2/net.if.status[ifOperStatus.10001],#1)<>last(/AKTAU-CAT-2/net.if.status[ifOperStatus.10001],#2))",
        "flags": "4",
        "groups": [
          {
            "groupid": "37",
            "name": "FILIAL_11_Aktau"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "AKTAU-CAT-2",
            "hostid": "12035",
            "maintenance_status": "0",
            "name": "AKTAU-CAT-2",
            "proxy_hostid": "11164",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "315267",
            "key_": "net.if.status[ifOperStatus.10001]",
            "lastvalue": "2",
            "name": "Interface Fa0/1(): Operational status"
          }
        ],
        "lastchange": "1686560750",
        "manual_close": "1",
        "opdata": "Current state: {ITEM.LASTVALUE1}",
        "priority": "3",
        "recovery_expression": "last(/AKTAU-CAT-2/net.if.status[ifOperStatus.10001])<>2 or 1=0",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "128157",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "128974": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Gi1/0/37(): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/UST-BRANCH-f0-SW-1/net.if.duplex[dot3StatsDuplexStatus.10137])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "UST-BRANCH-f0-SW-1",
            "hostid": "12046",
            "maintenance_status": "0",
            "name": "UST-BRANCH-f0-SW-1",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "318003",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10137]",
            "lastvalue": "2",
            "name": "Interface Gi1/0/37(): Duplex status"
          }
        ],
        "lastchange": "1686311221",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "128974",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "128976": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Gi1/0/39(): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/UST-BRANCH-f0-SW-1/net.if.duplex[dot3StatsDuplexStatus.10139])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "UST-BRANCH-f0-SW-1",
            "hostid": "12046",
            "maintenance_status": "0",
            "name": "UST-BRANCH-f0-SW-1",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "318005",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10139]",
            "lastvalue": "2",
            "name": "Interface Gi1/0/39(): Duplex status"
          }
        ],
        "lastchange": "1686311221",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "128976",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "128996": {
        "comments": "This Ethernet connection has transitioned down from its known maximum speed. This might be a sign of autonegotiation issues. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Gi1/0/12(): Ethernet has changed to lower speed than it was before",
        "error": "",
        "event_name": "",
        "expression": "change(/UST-BRANCH-f0-SW-1/net.if.speed[ifHighSpeed.10112])<0 and last(/UST-BRANCH-f0-SW-1/net.if.speed[ifHighSpeed.10112])>0\r\nand (\r\nlast(/UST-BRANCH-f0-SW-1/net.if.type[ifType.10112])=6 or\r\nlast(/UST-BRANCH-f0-SW-1/net.if.type[ifType.10112])=7 or\r\nlast(/UST-BRANCH-f0-SW-1/net.if.type[ifType.10112])=11 or\r\nlast(/UST-BRANCH-f0-SW-1/net.if.type[ifType.10112])=62 or\r\nlast(/UST-BRANCH-f0-SW-1/net.if.type[ifType.10112])=69 or\r\nlast(/UST-BRANCH-f0-SW-1/net.if.type[ifType.10112])=117\r\n)\r\nand\r\n(last(/UST-BRANCH-f0-SW-1/net.if.status[ifOperStatus.10112])<>2)",
        "flags": "4",
        "groups": [
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "UST-BRANCH-f0-SW-1",
            "hostid": "12046",
            "maintenance_status": "0",
            "name": "UST-BRANCH-f0-SW-1",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "318257",
            "key_": "net.if.type[ifType.10112]",
            "lastvalue": "6",
            "name": "Interface Gi1/0/12(): Interface type"
          },
          {
            "itemid": "318315",
            "key_": "net.if.status[ifOperStatus.10112]",
            "lastvalue": "1",
            "name": "Interface Gi1/0/12(): Operational status"
          },
          {
            "itemid": "318489",
            "key_": "net.if.speed[ifHighSpeed.10112]",
            "lastvalue": "100000000",
            "name": "Interface Gi1/0/12(): Speed"
          }
        ],
        "lastchange": "1686371341",
        "manual_close": "1",
        "opdata": "Current reported speed: {ITEM.LASTVALUE1}",
        "priority": "1",
        "recovery_expression": "(change(/UST-BRANCH-f0-SW-1/net.if.speed[ifHighSpeed.10112])>0 and last(/UST-BRANCH-f0-SW-1/net.if.speed[ifHighSpeed.10112],#2)>0) or\r\n(last(/UST-BRANCH-f0-SW-1/net.if.status[ifOperStatus.10112])=2)",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "128996",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "129181": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Gi1/0/30(): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/UST-BRANCH-f0-SW-2/net.if.duplex[dot3StatsDuplexStatus.10130])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "UST-BRANCH-f0-SW-2",
            "hostid": "12047",
            "maintenance_status": "0",
            "name": "UST-BRANCH-f0-SW-2",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "318563",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10130]",
            "lastvalue": "2",
            "name": "Interface Gi1/0/30(): Duplex status"
          }
        ],
        "lastchange": "1686311222",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "129181",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "129201": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Gi1/0/21(): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/UST-BRANCH-f0-SW-3/net.if.duplex[dot3StatsDuplexStatus.10121])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "UST-BRANCH-f0-SW-3",
            "hostid": "12048",
            "maintenance_status": "0",
            "name": "UST-BRANCH-f0-SW-3",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "318583",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10121]",
            "lastvalue": "2",
            "name": "Interface Gi1/0/21(): Duplex status"
          }
        ],
        "lastchange": "1686311223",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "129201",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "129205": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Gi1/0/31(): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/UST-BRANCH-f0-SW-3/net.if.duplex[dot3StatsDuplexStatus.10131])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "UST-BRANCH-f0-SW-3",
            "hostid": "12048",
            "maintenance_status": "0",
            "name": "UST-BRANCH-f0-SW-3",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "318587",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10131]",
            "lastvalue": "2",
            "name": "Interface Gi1/0/31(): Duplex status"
          }
        ],
        "lastchange": "1686321183",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "129205",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "129208": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Gi1/0/34(): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/UST-BRANCH-f0-SW-3/net.if.duplex[dot3StatsDuplexStatus.10134])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "UST-BRANCH-f0-SW-3",
            "hostid": "12048",
            "maintenance_status": "0",
            "name": "UST-BRANCH-f0-SW-3",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "318590",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10134]",
            "lastvalue": "2",
            "name": "Interface Gi1/0/34(): Duplex status"
          }
        ],
        "lastchange": "1686311223",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "129208",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "129428": {
        "comments": "This Ethernet connection has transitioned down from its known maximum speed. This might be a sign of autonegotiation issues. Ack to close.",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Gi1/0/31(): Ethernet has changed to lower speed than it was before",
        "error": "",
        "event_name": "",
        "expression": "change(/UST-BRANCH-f0-SW-3/net.if.speed[ifHighSpeed.10131])<0 and last(/UST-BRANCH-f0-SW-3/net.if.speed[ifHighSpeed.10131])>0\r\nand (\r\nlast(/UST-BRANCH-f0-SW-3/net.if.type[ifType.10131])=6 or\r\nlast(/UST-BRANCH-f0-SW-3/net.if.type[ifType.10131])=7 or\r\nlast(/UST-BRANCH-f0-SW-3/net.if.type[ifType.10131])=11 or\r\nlast(/UST-BRANCH-f0-SW-3/net.if.type[ifType.10131])=62 or\r\nlast(/UST-BRANCH-f0-SW-3/net.if.type[ifType.10131])=69 or\r\nlast(/UST-BRANCH-f0-SW-3/net.if.type[ifType.10131])=117\r\n)\r\nand\r\n(last(/UST-BRANCH-f0-SW-3/net.if.status[ifOperStatus.10131])<>2)",
        "flags": "4",
        "groups": [
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "UST-BRANCH-f0-SW-3",
            "hostid": "12048",
            "maintenance_status": "0",
            "name": "UST-BRANCH-f0-SW-3",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "319912",
            "key_": "net.if.type[ifType.10131]",
            "lastvalue": "6",
            "name": "Interface Gi1/0/31(): Interface type"
          },
          {
            "itemid": "319970",
            "key_": "net.if.status[ifOperStatus.10131]",
            "lastvalue": "1",
            "name": "Interface Gi1/0/31(): Operational status"
          },
          {
            "itemid": "320144",
            "key_": "net.if.speed[ifHighSpeed.10131]",
            "lastvalue": "100000000",
            "name": "Interface Gi1/0/31(): Speed"
          }
        ],
        "lastchange": "1686321243",
        "manual_close": "1",
        "opdata": "Current reported speed: {ITEM.LASTVALUE1}",
        "priority": "1",
        "recovery_expression": "(change(/UST-BRANCH-f0-SW-3/net.if.speed[ifHighSpeed.10131])>0 and last(/UST-BRANCH-f0-SW-3/net.if.speed[ifHighSpeed.10131],#2)>0) or\r\n(last(/UST-BRANCH-f0-SW-3/net.if.status[ifOperStatus.10131])=2)",
        "recovery_mode": "1",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "129428",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      },
      "129795": {
        "comments": "Please check autonegotiation settings and cabling",
        "correlation_mode": "0",
        "correlation_tag": "",
        "description": "Interface Gi1/0/18(): In half-duplex mode",
        "error": "",
        "event_name": "",
        "expression": "last(/UST-BRANCH-f0-SW-6/net.if.duplex[dot3StatsDuplexStatus.10118])=2",
        "flags": "4",
        "groups": [
          {
            "groupid": "35",
            "name": "FILIAL_09_Oskemen"
          },
          {
            "groupid": "70",
            "name": "DEVICES_GATEWAY_FILIALS"
          }
        ],
        "hosts": [
          {
            "description": "",
            "host": "UST-BRANCH-f0-SW-6",
            "hostid": "12050",
            "maintenance_status": "0",
            "name": "UST-BRANCH-f0-SW-6",
            "proxy_hostid": "11108",
            "proxy": ""
          }
        ],
        "items": [
          {
            "itemid": "320747",
            "key_": "net.if.duplex[dot3StatsDuplexStatus.10118]",
            "lastvalue": "2",
            "name": "Interface Gi1/0/18(): Duplex status"
          }
        ],
        "lastchange": "1686311225",
        "manual_close": "1",
        "opdata": "",
        "priority": "2",
        "recovery_expression": "",
        "recovery_mode": "0",
        "state": "0",
        "status": "0",
        "templateid": "0",
        "triggerid": "129795",
        "type": "0",
        "url": "",
        "uuid": "",
        "value": "1"
      }
    }
  }
}
