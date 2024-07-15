global class AccessibilityProjectBilling {
    
    @future(callout=true)
    public static void callBillingService(String projectId, Decimal billingAmount) {
        BillingServiceProxy.InvoicesPortSoap11 stub = new BillingServiceProxy.InvoicesPortSoap11();
        
        BillingServiceProxy.project project = new BillingServiceProxy.project();
        project.projectid = projectId;
        project.billAmount = Double.valueOf(billingAmount);
        project.username = '{!$Credential.BillingServiceCredential.username}';
        project.password = '{!$Credential.BillingServiceCredential.password}';

        try {
            String status = stub.billProject(project);

            if (status == 'ok') {
                Accessibility_Project__c accProject = [SELECT Id, Status__c FROM Accessibility_Project__c WHERE Id = :projectId LIMIT 1];
                accProject.Status__c = 'Complete';
                update accProject;
            }
        } catch (Exception e) {
            System.debug('SOAP call failed: ' + e.getMessage());
        }
    }
}
