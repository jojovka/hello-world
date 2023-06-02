# hello-world
Just my first repository

public void zabbixAuth() throws URISyntaxException {
        Long id = new Random().nextLong();

        RestTemplate restTemplate = new RestTemplate();

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

        System.out.println("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$");
        System.out.println("Auth");
        System.out.println(response.getBody());
        System.out.println("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$");
    }

org.springframework.web.client.ResourceAccessException: I/O error on POST request for "https://zabbixapp.eub.kz/api_jsonrpc.php": PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target; nested exception is javax.net.ssl.SSLHandshakeException: PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
