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
      "jsonrpc": "2.0",
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
      },
    "auth": "cfb840b0202e544a0a5512dbbabf72f9",
    "id": 1
 }

public void triggerGet() throws URISyntaxException, KeyStoreException, NoSuchAlgorithmException, KeyManagementException {
    RestTemplate restTemplate = restTemplate();

    URI uri = new URI("https://zabbixapp.eub.kz/api_jsonrpc.php");

    HttpHeaders headers = new HttpHeaders();
    headers.set("Content-Type", "application/json-rpc");

    JSONObject body = new JSONObject();
    body.put("jsonrpc", "2.0");
    body.put("method", "trigger.get");

    JSONObject params = new JSONObject();
    params.put("output", "extend");
    
    JSONArray triggerids = new JSONArray(Arrays.asList("121082", "73303", "96874", "96878", "96877", "96876", "96875", "96873", "96872", "96871", "96870", "96869", "96924", "96923", "96913", "96912", "96911", "96910", "96909", "96908", "96907", "96906", "96905", "96904", "96903", "96902", "96901", "96900", "96899", "96898", "96897", "96896", "96895", "96894", "96893", "96892", "96891", "96890", "96889", "96888", "96887", "96886", "96885", "96884", "96883", "96882", "96881", "96880", "96879", "96754", "96922", "96921", "96920", "96919", "96918", "96917", "96963", "96916", "96915", "96914", "126961", "23236", "71594", "83401", "66315", "128157", "93302", "77804", "86980", "81915", "80473", "84849", "69336", "69334", "33033", "127777", "117490", "81925", "96520", "119452", "62963", "62940", "62848", "63929", "61675", "63538", "32914", "113322", "113276", "63331", "63308", "63285", "63239", "119679", "63216", "113092", "119656", "119633", "64274", "63147", "64251", "119587", "63124", "63101", "114884", "63078", "114861", "125953", "61905", "63009", "61859", "99946", "97761", "71595", "96239", "96430", "96240", "124410", "71569", "71596", "128996", "86783", "116351", "116350", "129428", "129205", "69468", "127312", "127308", "127092", "129795", "129208", "129201", "129181", "128976", "128974", "127879", "127872", "127871", "89477", "90506", "125991", "77848", "96571", "71562", "80299", "97289", "75215", "86114", "125147", "125107", "98812", "99082", "116181", "90918", "98777", "81393", "81392", "124785", "81391", "81415", "122218", "121405", "121650", "121350", "121214", "123970", "122270", "124115", "118227", "118020", "81928", "116821", "116191", "116190", "112376", "112537", "112283", "101727", "100014", "108738", "110266", "110215", "108552", "108551", "108545", "108544", "108543", "108580", "108579", "108578", "108279", "104233", "96316", "102640", "102641", "102584", "102590", "101716", "101717", "88477", "101570", "101433", "101198", "93273", "73627", "93230", "100827", "100828", "100817", "100818", "100812", "100811", "100801", "100802", "100799", "100800", "100795", "100796", "40956", "100532", "99360", "99220", "100080", "99174", "99828", "99268", "99140", "99794", "100058", "99568", "99734", "98916", "76361", "98622", "63357", "88631", "86660", "98122", "98121", "97303", "97311", "96748", "96100", "96572", "96196", "90627", "90972", "90966", "90893", "86981", "41323", "77648", "78443", "85223", "37261", "37294", "63174", "89036", "82785", "82873", "36751", "78896", "74292", "69421", "69157", "69311", "67987", "40955", "41287", "41263", "30467", "31564", "30165", "30619", "30941", "30620"));
    params.put("triggerids", triggerids);
    params.put("expandDescription", true);
    params.put("expandData", true);
    params.put("expandComment", true);
    params.put("expandExpression", true);
    params.put("monitored", true);
    params.put("skipDependent", true);
    
    JSONArray selectGroups = new JSONArray(Arrays.asList("name", "groupid"));
    params.put("selectGroups", selectGroups);
    
    JSONArray selectHosts = new JSONArray(Arrays.asList("hostid", "name", "host", "maintenance_status", "proxy_hostid", "description"));
    params.put("selectHosts", selectHosts);
    
    JSONArray selectItems = new JSONArray(Arrays.asList("itemid", "name", "key_", "lastvalue"));
    params.put("selectItems", selectItems);
    
    params.put("preservekeys", "1");

    body.put("params", params);
    body.put("id", 1);
    body.put("auth", "cfb840b0202e544a0a5512dbbabf72f9");

    HttpEntity<String> entity = new HttpEntity<>(body.toString(), headers);

    ResponseEntity<String> response = restTemplate.exchange(uri, HttpMethod.POST, entity, String.class);

    System.out.println(response.getBody());
}

private RestTemplate restTemplate() throws KeyStoreException, NoSuchAlgorithmException, KeyManagementException {
    TrustStrategy acceptingTrustStrategy = (X509Certificate[] chain, String authType) -> true;
    SSLContext sslContext = org.apache.http.ssl.SSLContexts.custom().loadTrustMaterial(null, acceptingTrustStrategy).build();
    SSLConnectionSocketFactory csf = new SSLConnectionSocketFactory(sslContext);
    CloseableHttpClient httpClient = HttpClients.custom().setSSLSocketFactory(csf).build();
    HttpComponentsClientHttpRequestFactory requestFactory = new HttpComponentsClientHttpRequestFactory();
    requestFactory.setHttpClient(httpClient);
    return new RestTemplate(requestFactory);
}
