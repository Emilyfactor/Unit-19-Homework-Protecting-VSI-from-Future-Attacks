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
Based on the attack signatures, what mitigations would you recommend to protect each user account? Provide global mitigations that the whole company can use and individual mitigations that are specific to each user.
		
		> Best Global mitigation solution would be to add a multi-factor authenticator to the companies systems. This would reduce the number of successful threats to gain access to user accounts.
		> Individual Solutions:
			- User K: An attempt was made to reset password
						- Several attempts to reset password were made 
						- User should be set up with user-specific alerts with lower values in order to closely analyze 
			- User A: A user account was locked out
						-User should change password to something completely different immediately. A password that is complex to prevent a brute force attack in future.
			- User J: An account was successfully logged on
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

Based on the geographic map, recommend a firewall rule that the networking team should implement.
Provide a "plain english" description of the rule.

Firewall Rule Description- 

For example: "Block all incoming HTTP traffic where the source IP comes from the city of Los Angeles."


Provide a screen shot of the geographic map that justifies why you created this rule.


Question 2


VSI has insider information that JobeCorp will launch the same webserver attack but use a different IP each time in order to avoid being stopped by the rule you just created.


What other rules can you create to protect VSI from attacks against your webserver?

Conceive of two more rules in "plain english".
Hint: Look for other fields that indicate the attacker.




Guidelines for your Submission:
In a word document, provide the following:

Answers for all questions.
Screenshots where indicated

Submit your findings in BootCampSpot!

© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.