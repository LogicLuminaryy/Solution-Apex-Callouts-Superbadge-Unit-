public class RewardsCalloutService {
    public static Integer submitUsersForRewardCallout(String jsonBody) {
        HttpRequest req = new HttpRequest();
        req.setEndpoint('callout:BalancedLiving/rewards');
        req.setMethod('POST');
        req.setHeader('Content-Type', 'application/json');
        req.setBody(jsonBody);

        Http http = new Http();
        HttpResponse res;
        Integer statusCode;
        try {
            res = http.send(req);
            statusCode = res.getStatusCode();
            System.debug('Response Status: ' + statusCode);
            System.debug('Response Body: ' + res.getBody());
        } catch (Exception e) {
            System.debug('Error: ' + e.getMessage());
            statusCode = 500; // Internal Server Error
        }
        return statusCode;
    }
}
