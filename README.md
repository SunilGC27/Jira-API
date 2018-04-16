# Jira-API
Jira API for executing and updating test case.
PUT updateTestStep
https://jira.icontrol.com/rest/zapi/latest/stepResult/283921
UpdateTestStep

projectId=12151&versionId=31026&cycleId=3639 Project id: Cycle Id: Version id:

http://docs.zapitest.apiary.io/#reference/stepresult-resource-api(s)/stepresult/get

HEADERS
AuthorizationBasic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=
Content-Typeapplication/json
BODY
{
            "id":283921,
            "issueId": 245771,
            "executionId": 259870,
            "status": "1",
            "defectList": [],
            "updateDefectList": "true",
            "comment": "updated by API call"
            }
            
            


Sample Request
updateTestStep
curl --request PUT \
  --url https://jira.icontrol.com/rest/zapi/latest/stepResult/283921 \
  --header 'Authorization: Basic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=' \
  --header 'Content-Type: application/json' \
  --data '{
            "id":283921,
            "issueId": 245771,
            "executionId": 259870,
            "status": "1",
            "defectList": [],
            "updateDefectList": "true",
            "comment": "updated by API call"
            }
            
            
'
PUT updateTestCase
https://jira.icontrol.com/rest/zapi/latest/execution/269767/execute
Updated the execution status of the test case to "pass", "fail", etc.

projectId=12151&versionId=31026&cycleId=3639

HEADERS
Content-Typeapplication/json
AuthorizationBasic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=
BODY
{
  "status": "5",
  "defectList": [],
  "updateDefectList": "true",
  "comment": "updated by API call"
}


Sample Request
updateTestCase
curl --request PUT \
  --url https://jira.icontrol.com/rest/zapi/latest/execution/269767/execute \
  --header 'Authorization: Basic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=' \
  --header 'Content-Type: application/json' \
  --data '{
  "status": "5",
  "defectList": [],
  "updateDefectList": "true",
  "comment": "updated by API call"
}'
GET getExecutionId
https://jira.icontrol.com/rest/zapi/latest/execution?projectId=12151&versionId=31026&cycleId=3639
Get executionId of the test case which will be used to pass as a parameter for updateTestCase call projectId=12151&versionId=31026&cycleId=3639

HEADERS
AuthorizationBasic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=
PARAMS
projectId12151
versionId31026
cycleId3639

Sample Request
getExecutionId
curl --request GET \
  --url 'https://jira.icontrol.com/rest/zapi/latest/execution?projectId=12151&versionId=31026&cycleId=3639' \
  --header 'Authorization: Basic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY='
GET getCycleId
https://jira.icontrol.com/rest/zapi/latest/cycle?versionId=31456&projectId=12151
Return cycleId which will be used as a parameter to get executionId

projectId=12151&versionId=31026&cycleId=3639

http://docs.zapitest.apiary.io/#reference/stepresult-resource-api(s)/stepresult/get

HEADERS
AuthorizationBasic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=
PARAMS
versionId31456
projectId12151

Sample Request
getCycleId
curl --request GET \
  --url 'https://jira.icontrol.com/rest/zapi/latest/cycle?versionId=31456&projectId=12151' \
  --header 'Authorization: Basic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY='
GET getTestStepNum 
https://jira.icontrol.com/rest/zapi/latest/teststep/245771
Get the test step id which will be passed to updateTestStep call to make any perticual step pass/fail "issueId": 221850, "issueKey": "CONVQA-10238",

HEADERS
AuthorizationBasic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=

Sample Request
getTestStepNum
curl --request GET \
  --url https://jira.icontrol.com/rest/zapi/latest/teststep/245771 \
  --header 'Authorization: Basic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY='
POST postAttachment
https://jira.icontrol.com/rest/zapi/latest/attachment?issueId=221850&versionId=31026&entityName=StepScreenshot.PNGcycleId=3639&entityId=1005603&comment=ExampleScreenshot&projectId=12151
Sample code: https://support.getzephyr.com/hc/en-us/articles/202466019-Sample-Add-Attachment-to-Execution https://support.getzephyr.com/hc/en-us/articles/202466019-Sample-Add-Attachment-to-Execution

HEADERS
AuthorizationBasic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=
X-Atlassian-Tokennocheck
Content-Typemultipart/form-data
PARAMS
issueId221850
versionId31026
entityNameStepScreenshot.PNGcycleId=3639
entityId1005603
commentExampleScreenshot
projectId12151
BODY


Sample Request
postAttachment
curl --request POST \
  --url 'https://jira.icontrol.com/rest/zapi/latest/attachment?issueId=221850&versionId=31026&entityName=StepScreenshot.PNGcycleId=3639&entityId=1005603&comment=ExampleScreenshot&projectId=12151' \
  --header 'Authorization: Basic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=' \
  --header 'Content-Type: multipart/form-data' \
  --header 'X-Atlassian-Token: nocheck'
POST createExecution 
https://jira.icontrol.com/rest/zapi/latest/execution
http://docs.zapitest.apiary.io/#reference/stepresult-resource-api(s)/stepresult/get

HEADERS
AuthorizationBasic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=
Content-Typeapplication/json
BODY
{
	"issueId": 245612,
	"versionId": 31026,
	"cycleId": 4099,
	"projectId": 12151
}


Sample Request
createExecution
curl --request POST \
  --url https://jira.icontrol.com/rest/zapi/latest/execution \
  --header 'Authorization: Basic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=' \
  --header 'Content-Type: application/json' \
  --data '{
	"issueId": 245612,
	"versionId": 31026,
	"cycleId": 4099,
	"projectId": 12151
}'
GET getSteps 
https://jira.icontrol.com/rest/zapi/latest/stepResult?executionId=260756
HEADERS
AuthorizationBasic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=
PARAMS
executionId260756

Sample Request
getSteps
curl --request GET \
  --url 'https://jira.icontrol.com/rest/zapi/latest/stepResult?executionId=260756' \
  --header 'Authorization: Basic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY='
POST createTestCycle 
https://jira.icontrol.com/rest/zapi/latest/cycle
create test cycle http://docs.zapitest.apiary.io/#reference/stepresult-resource-api(s)/stepresult/get

HEADERS
AuthorizationBasic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=
Content-Typeapplication/json
BODY
{
  "clonedCycleId": "",
  "name": "Dummy Cycle JI",
  "build": "",
  "environment": "",
  "description": "Dummy Cycle JI",
  "startDate": "",
  "endDate": "",
  "projectId": "12151",
  "versionId": "31026"
}


Sample Request
createTestCycle
curl --request POST \
  --url https://jira.icontrol.com/rest/zapi/latest/cycle \
  --header 'Authorization: Basic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=' \
  --header 'Content-Type: application/json' \
  --data '{
  "clonedCycleId": "",
  "name": "Dummy Cycle JI",
  "build": "",
  "environment": "",
  "description": "Dummy Cycle JI",
  "startDate": "",
  "endDate": "",
  "projectId": "12151",
  "versionId": "31026"
}'
GET getIssueId
https://jira.icontrol.com/rest/api/2/issue/CONVQA-11786
HEADERS
AuthorizationBasic aGF5eWFwcGFzYW15X2V4dDpBdXN0aW44MTY=
