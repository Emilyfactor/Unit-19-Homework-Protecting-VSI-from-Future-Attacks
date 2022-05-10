Unit 19 Homework: Protecting VSI from Future Attacks

Scenario
In the previous class,  you set up your SOC and monitored attacks from JobeCorp. Now, you will need to design mitigation strategies to protect VSI from future attacks.
You are tasked with using your findings from the Master of SOC activity to answer questions about mitigation strategies.

System Requirements
You will be using the Splunk app located in the Ubuntu VM.

Logs
Use the same log files you used during the Master of SOC activity:

Windows Logs
Windows Attack Logs
Apache Webserver Logs
Apache Webserver Attack Logs



Part 1: Windows Server Attack
Note: This is a public-facing windows server that VSI employees access.
(source used sectigostore.com)

Question 1

Several users were impacted during the attack on March 25th.

![image](https://user-images.githubusercontent.com/96030770/167719421-be179805-108f-4779-aac5-6af2c9889651.png)

![image](https://user-images.githubusercontent.com/96030770/167720563-29b0f7a1-5f9e-47a5-9bce-ac4fa5ba5d08.png)

![image](https://user-images.githubusercontent.com/96030770/167720654-7408ff16-d685-4e43-9c57-875116296794.png)

![image](https://user-images.githubusercontent.com/96030770/167720718-878e0517-ab61-4811-ad00-2a1c282e397d.png)


Based on the attack signatures, what mitigations would you recommend to protect each user account? Provide global mitigations that the whole company can use and individual mitigations that are specific to each user.
		
		> Best Global mitigation solution would be to add a multi-factor authenticator to the companies systems. This would reduce the number of successful threats to gain access to user accounts.
		> Individual Solutions:
			- User K: An attempt was made to reset password
			
![image](https://user-images.githubusercontent.com/96030770/167730648-2455f001-62cd-48ac-a04f-3b7a901dd90f.png)
			
						- Several attempts to reset password were made 
						- User should be set up with user-specific alerts with lower values in order to closely analyze 
			- User A: A user account was locked out
			
![image](https://user-images.githubusercontent.com/96030770/167730899-55d2b807-2f2e-45e0-afdc-312228b0facd.png)
		
						-User should change password to something completely different immediately. A password that is complex to prevent a brute force attack in future.
			- User J: An account was successfully logged on
			
![image](https://user-images.githubusercontent.com/96030770/167731117-bdf487a0-e529-48b4-a27c-d506776b0907.png)
		
						- This log indicates the attacker was able to successfully obtain user's password
						- Password should be changed to something more complex
						- User should be set up with user-specific alerts with lower values in order to analyze closely			  	 		

Question 2

VSI has insider information that JobeCorp attempted to target users by sending "Bad Logins" to lock out every user.
What sort of mitigation could you use to protect against this?

		> Offer regular cyber awareness training and workshops. Regular, interactive cyber awareness programs, simulated phishing attacks, etc. can help train employees to identify and react better to information security threats.
		> Assess the security prowess of vendors before providing them with access. It makes sense to conduct a comprehensive, end-to-end vendor risk assessment for third parties to understand and evaluate their security posture before providing any access to the business network and prior to sharing any critical data.
		> Verify, and verify again. Get into the habit of verifying and cross-verifying credentials and authorization before sharing any sensitive information. Use official contact information (such as the person’s phone number from your organization’s internal contact directory) and not information that’s provided to you by the suspicious individual.


Part 2: Apache Webserver Attack:

Question 1

![image](https://user-images.githubusercontent.com/96030770/167729340-23616640-74f8-40e0-94b6-3a3c38bf7e33.png)

![image](https://user-images.githubusercontent.com/96030770/167729652-3aaf379c-c8ad-4dd6-ad45-bf9bac3c5c18.png)

![image](https://user-images.githubusercontent.com/96030770/167729709-75f91a43-e524-4dcb-974e-0db0657a5acc.png)

![image](https://user-images.githubusercontent.com/96030770/167722677-863fc2b4-0577-4806-bc47-f70a35b7ed33.png)

![image](https://user-images.githubusercontent.com/96030770/167722731-e9e27a35-89ae-4adf-9e71-6041bbcca1f3.png)


Based on the geographic map, recommend a firewall rule that the networking team should implement.
Provide a "plain english" description of the rule.

Filtering out the traffic from the United States, the country which had the most activity is coming from Ukraine.

		> Firewall Rule Description- Block all incoming HTTP traffic where the source IP comes from the country of Ukraine.


Question 2

VSI has insider information that JobeCorp will launch the same webserver attack but use a different IP each time in order to avoid being stopped by the rule you just created.

What other rules can you create to protect VSI from attacks against your webserver?

Most of the data coming from the Ukarine is approximately 34% of the network. There are 3 other vaules that could cause for the creation of more firewalls: bytes, ip, useragent.
	> Block all incoming HTTP traffic where the bytes are equal to 65748
	> Block all incoming HTTP traffic where the ip address is equal to 194.105.145.147 AND 79.171.127.34
	> Block all incoming HTTP traffic where the useragent is equal to Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.2; SV1; .NET CLR 2.0 50727987787; InfoPath.1)

Conceive of two more rules in "plain english".
Hint: Look for other fields that indicate the attacker.

![image](https://user-images.githubusercontent.com/96030770/167731675-6532bc9f-268f-4bc6-8453-434e7a1f9479.png)


![image](https://user-images.githubusercontent.com/96030770/167731575-ee6056dc-3b5e-4dc7-bf9d-946ca30965a4.png)


Guidelines for your Submission:
In a word document, provide the following:

Answers for all questions.
Screenshots where indicated

Submit your findings in BootCampSpot!

© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
