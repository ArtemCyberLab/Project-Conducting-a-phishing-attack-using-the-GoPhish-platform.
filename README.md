Description:
As part of this hands-on task, I launched a virtual machine and accessed the GoPhish dashboard via the provided URL. After successfully logging in (username: admin, password: tryhackme), I proceeded to configure all the key components of the phishing campaign:

Creating a Sending Profile:

Name: Local Server

From address: noreply@redteam.thm

SMTP Server: 127.0.0.1:25

Setting up the Phishing Landing Page:

Name: ACME Login

The page mimics an IT support login form for the fictional company "ACME."

Enabled options to capture submitted data and passwords.

Creating the Email Template:

Name: Email 1

Subject: New Message Received

The body of the email contains a persuasive message with a clickable link labeled https://admin.acmeitsupport.thm which actually redirects to {{.URL}}, automatically replaced with the spoofed landing page URL.

Adding Target Users (Users & Groups):

Group: Targets

Email addresses:

martin@acmeitsupport.thm

brian@acmeitsupport.thm

accounts@acmeitsupport.thm

Launching the Campaign:

Name: Campaign One

Email Template: Email 1

Landing Page: ACME Login

URL: http://10.10.225.112

Launch Date: set to two days ago for timezone compatibility

Sending Profile: Local Server

Target Group: Targets

After launching the campaign, I was redirected to the results page. The status showed successful delivery to Martin and Brian, while the email to the accounts address failed due to the user being unknown.

After a short time, Brian's status changed to Submitted Data, indicating that he had entered his login credentials on the spoofed site. Upon inspecting the submission details, I was able to view Brian’s username and password.

Conclusion:
Through this project, I successfully organized and executed a phishing campaign, crafted a fake login page and email, and captured the credentials of one target. This experience provided me with a practical understanding of phishing techniques and emphasized the critical importance of user awareness and cybersecurity practices.
