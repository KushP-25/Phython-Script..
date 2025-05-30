# Phython-Script..
I'll try to get all the Github repository from the helium10 organization and ask for last commit and if it has a CircleCI workflow in it and when was the workflow last updated. Also, output as a HTML table.


Steps:
1. Talk to github and get repos
2. Check all repos for their last commit date and if it has CircleCI workflows.
3. Check for the last commit if older than 12 months trash it.
4. Output as HTML Table with all the info

<br /> 
<br /> 

Step 1:
how to access github repository from python
https://www.merge.dev/blog/github-get-repositories
<br /> 
<br /> 

Sub steps:
<br /> 
1. Generate the fine grained personal access token
https://www.merge.dev/blog/github-get-repositories
<br /> 
2. Making an Authenticated request
 we’ll first construct the URL that we want to make the request to, and this time we’ll also set up the headers for our request, which will contain our personal access token in the “Authorization” key.

<br /> 
1 Attemt: I failed
(
import requests


Github_BASE_URL = "https://api.github.com"
org_name = "heluim10"
org_url = f"{Github_BASE_URL}/orgs/{org_name}"

Github_TOKEN = "(Your Token)"


headers ={
    "Authorization": f"Bearer {Github_TOKEN}"
}

response = requests.get(org_url, headers=headers)

if response.status_code == 200:
   repos = response.json()
else:
 print(f"Failed to fetch organization data: {response.status_code}")
)
<br /> 

Error: 404
What does Error 404 mean?
means that the web server couldn't find the specific page or resource you were trying to access..

So probably there is wrong url or location... 

<br /> <br /> 

Fixed it: it was a typo in org_name.
