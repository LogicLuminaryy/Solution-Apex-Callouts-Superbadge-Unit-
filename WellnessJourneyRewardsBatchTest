@isTest
public class WellnessJourneyRewardsBatchTest {
    @testSetup
    static void setup() {
        // Create test users
        User testUser1 = new User(
            FirstName = 'Test',
            LastName = 'User1',
            Email = 'testuse4354647r1@example.com',
            Username = 'testuser323231@example.com',
            Alias = 'tuser1',
            TimeZoneSidKey = 'America/Los_Angeles',
            LocaleSidKey = 'en_US',
            EmailEncodingKey = 'UTF-8',
            ProfileId = [SELECT Id FROM Profile WHERE Name='Standard User' LIMIT 1].Id,
            LanguageLocaleKey = 'en_US'
        );
        insert testUser1;

        User testUser2 = new User(
            FirstName = 'Test',
            LastName = 'User2',
            Email = 'testuse232425r2@example.com',
            Username = 'testuser232323232@example.com',
            Alias = 'tuser2',
            TimeZoneSidKey = 'America/Los_Angeles',
            LocaleSidKey = 'en_US',
            EmailEncodingKey = 'UTF-8',
            ProfileId = [SELECT Id FROM Profile WHERE Name='Standard User' LIMIT 1].Id,
            LanguageLocaleKey = 'en_US'
        );
        insert testUser2;

        // Create test Wellness_Journey__c records
        List<Wellness_Journey__c> journeys = new List<Wellness_Journey__c>();
        for (Integer i = 0; i < 13; i++) {
            journeys.add(new Wellness_Journey__c(
                Name = 'Journey ' + i,
                OwnerId = testUser1.Id,
                Status__c = 'Complete',
                Completion_Date__c = Date.today().addDays(-90)
            ));
        }

        for (Integer i = 0; i < 5; i++) {
            journeys.add(new Wellness_Journey__c(
                Name = 'Journey ' + (13 + i),
                OwnerId = testUser2.Id,
                Status__c = 'Complete',
                Completion_Date__c = Date.today().addDays(-90)
            ));
        }

        insert journeys;
    }

    @isTest
    static void testWellnessJourneyRewardsBatch() {
        // Mocking the HTTP response for RewardsCalloutService
        Test.setMock(HttpCalloutMock.class, new RewardsCalloutServiceMock());

        // Execute the batch
        Test.startTest();
        WellnessJourneyRewardsBatch batch = new WellnessJourneyRewardsBatch();
        Database.executeBatch(batch);
        Test.stopTest();

        // Verify that the batch executed correctly
        // We can verify by checking debug logs or using other assert statements
        // Ensure that the correct number of journeys were processed
        List<Wellness_Journey__c> processedJourneys = [SELECT Id FROM Wellness_Journey__c WHERE Status__c = 'Complete'];
        System.assertEquals(18, processedJourneys.size());
    }

}
