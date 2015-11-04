#Test 1
## Pre
1. Several weeks ago, I created a VPC docker-weavorm in sa-east-1
2. Created an instance with security group that allows TCP via all ports.  This will run an AMI with a python service SimpleHTTPServer.  Different handlers will respond differently.
3. Created an ELB.


## Tests

### Create a new bastion in a VPC that isn't default, in region sa-east-1
```
Nov 4, 11:08AM
info:
region: sa-east-1a
VPC ID: vpc-57581e32 (docker weavorm)
```

1. After the region select screen, received 

	>error connecting to opsee 
	* This is caused due to some connection between emissary and barnet.  
	* Refreshing allows or restarting the process allows us to continue with the installation
	
2. Restarted installation and we failed at the final step. 
	 ![image](./test-1.png)
    > Bastion Launch Bot: error while launching bastion BASTION LAUNCH FAILED - user-email: dan@opsee.co customer-id: 5963d7bc-6ba2-11e5-8603-6ba085b2f5b5 user-id 13
    * given that the error message is the same, seems likely that it's the same issue we saw in #1
    
    #### Post
    
    * No bastion instance exists in sa-east-1 due to connection error
    
    
    
# Test 2
```
Nov 4. 1PM
Same environment
```
1. After Region Select screen, Entering credentials

 > Received error (same as previous): WebSocket connection to 'wss://api.opsee.com/stream/' failed: Connection closed before receiving a handshake response 
 
2. Eventually got to VPC Select screen.  Reached failure due to error described above in #1. However, bartnet received the command to launch.

WebSocket connection to 'wss://api.opsee.com/stream/' failed: Connection closed before receiving a handshake response.  

  * See: 
  * launch event: https://papertrailapp.com/groups/1993213/events?centered_on_id=598664346226458625&q=program%3Aecs-bartnet-21-bartnet-e6f9e8bcc7d8fbd2c001
  * create status: https://papertrailapp.com/groups/1993213/events?centered_on_id=598664864046841857&q=program%3Aecs-bartnet-21-bartnet-e6f9e8bcc7d8fbd2c001
  * failure: https://papertrailapp.com/groups/1993213/events?centered_on_id=598664868182425614&q=program%3Aecs-bartnet-21-bartnet-e6f9e8bcc7d8fbd2c001
  * rollback: https://papertrailapp.com/groups/1993213/events?centered_on_id=598664872242511884&q=program%3Aecs-bartnet-21-bartnet-e6f9e8bcc7d8fbd2c001
  
  ### Post
  	Same as in Test 1
