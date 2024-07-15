Apex Callouts Superbadge Unit
Overview
This document provides the steps and code needed to complete the Apex Callouts Superbadge Unit, which is part of the Outbound Integration Specialist Superbadge. This superbadge tests your ability to make secure callouts from Apex, consume a WSDL and generate an Apex proxy class for SOAP callouts, and create comprehensive test classes.

Prerequisites
Sign Up for a Developer Edition Org with Special Configuration:

Sign up using the provided link.
Complete the registration process and save your credentials securely.
Additional Configuration:

Navigate to the Balanced Living app's homepage.
Click the Setup button within the Lightning web component.
Ensure credentials are set up correctly.
Connect Org to Trailhead:

Connect your new Developer Edition org to Trailhead using the provided instructions.
Challenges
Challenge 1: Balanced Living Wellness App
1. Apex Batch Class: WellnessJourneyRewardsBatch
This batch class identifies employees who have completed at least 12 wellness activities within a quarter, compiles their data, serializes it into JSON, and makes an HTTP callout to the external rewards management service.

apex
Copy code from WellnessJourneyRewardsBatch

2. Rewards Callout Service: RewardsCalloutService
This service class handles the HTTP callout to the external rewards management service.

apex
Copy code RewardsCalloutService

3. Mock Callout Class: RewardsCalloutServiceMock
This mock class simulates responses from the external service for testing purposes.

apex
Copy code RewardsCalloutServiceMock 

4. Test Class: RewardsCalloutServiceTest
This test class validates the HTTP callout logic under various scenarios.

apex
Copy code RewardsCalloutServiceTest 

>>>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>> >>>>

Challenge 2: Accessibility Project Billing
1. Generate Proxy Class from WSDL
Prepare the WSDL file from the provided link.
Log in to Salesforce and navigate to the Apex Classes setup.
Use the Generate from WSDL button to upload and parse the WSDL file.
Name the generated Apex class BillingServiceProxy.
Save the generated class.

2. Apex Class: AccessibilityProjectBilling
This class handles the SOAP callout for submitting billing claims.

apex
Copy code AccessibilityProjectBilling 


3. Mock Class: BillingCalloutServiceMock
This mock class simulates responses from the SOAP service.

apex
Copy code BillingCalloutServiceMock

4. Test Class: BillingCalloutServiceTest
This test class validates the SOAP callout logic.

apex
Copy code BillingCalloutServiceTest 

Conclusion
By following these steps and using the provided code, you will be able to complete the Apex Callouts Superbadge Unit. This includes making secure HTTP callouts, consuming a WSDL to generate a SOAP proxy class, and creating comprehensive test classes to ensure the reliability of your integration.



Name Credential to Start Challenge 2 


<img width="1489" alt="Screenshot 2024-07-15 at 11 32 42 PM" src="https://github.com/user-attachments/assets/b988d7fd-e77f-432f-99eb-21b38369f5c4">
<img width="1478" alt="Screenshot 2024-07-15 at 11 42 46 PM" src="https://github.com/user-attachments/assets/a65e089b-a5ca-44cf-b844-91a0a397caa1">
<img width="1447" alt="Screenshot 2024-07-15 at 11 43 12 PM" src="https://github.com/user-attachments/assets/4ab2b739-e3e6-4d34-9fc0-8c2437e1d844">
<img width="1048" alt="Screenshot 2024-07-15 at 11 43 24 PM" src="https://github.com/user-attachments/assets/5e7c1b38-279f-4fcc-8b79-93e09b757d42"> (User Id and Password you can provide your sandbox one only)



