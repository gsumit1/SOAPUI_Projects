import groovy.json.JsonSlurper

def obj=new JsonSlurper()
def response=context.expand('${APIKeyRequest#Response}')

def allValue=obj.parseText(response)

String id1=allValue.accessToken
log.info id1
testRunner.testCase.testSuite.setPropertyValue( "APIKey", id1 )
