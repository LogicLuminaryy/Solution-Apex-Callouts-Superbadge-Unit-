public class AccessibilityProjectBillingTest {

    static void testCallBillingService() {
        // Set up test data
        Accessibility_Project__c project = new Accessibility_Project__c();
        project.Amount__c = 100.00;
        insert project;

        Test.startTest();
        
        // Set mock callout
        Test.setMock(WebServiceMock.class, new BillingCalloutServiceMock());

        // Call the method
        AccessibilityProjectBilling.callBillingService(project.Id, project.Amount__c);

        Test.stopTest();
        
        // Verify the project status
        project = [SELECT Status__c FROM Accessibility_Project__c WHERE Id = :project.Id];
        System.assertEquals('Complete', project.Status__c, 'Project status should be Complete');
    }
}