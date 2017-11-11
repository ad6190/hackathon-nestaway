# hackathon-nestaway

### Project 1 : Group people with similar preferences. Max group size 5. Preferences are weighted. 

Approach : 
Since there were only 8 preferences, I treated them as 8 features. Each of them could take 2 values. I initially thought of giving them binary values because user had to make only 2 options for each preference, like a user could either prefer veg, or non-veg - but I later decided to give them -1 and 1 values - because they had weights. In retrospect, I think even 0,1 would have been just fine. So, I formed a sample space assigning each datapoint a given weight. 

I then applied K-Means clustering to the sample set. I kept the no. of clusters to 2. 
Taking 1000 random user preference vectors, I predicted their clusters. 
From among the clusters, I just grouped users in batches of 5 each.


Benefits of this approach: 
User can have more than 8 preferences. The sample space then grows from 2^8 to 2^n. 
They could take more than 2 values, in the range of [-1,1]

Input and Output:
Input, I did not want to parse any data. My approach is demonstrated on ipython notebook. One can run each cell and see the output. If one wants to change feature vector size, or weights, or number of clusters, then simply change the value of those variables in the file.



### Project 3 : Implement google login, but allow only certain domains to view the resource. 

Approach : 
Created a flask app that allows google login. 
Copied regular google login from https://pythonspot.com/en/login-to-flask-app-with-google/
Post successful google login, checked the returned email-id. If email had an allowed domain, resource could be seen. Otherwise, just printed an error message on the page. 

Steps : 
Followed the above link and obtained google client id and secret. Those are commented in the code for security reasons. 
Added a list of allowed_domains. 
Did some basic checks like presence of @ in the entered email. Gmail doesn't mandatorily require @gmail.com, etc. 

Input and Output:
Inside proper environment, just ran the google_login.py file (after filling in client id and secret). Pretty much it. 


Requirements:
flask, flask_oauth 
(Do check the requirements file if I missed any)


