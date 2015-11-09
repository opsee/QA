```
Nov 9, 1:30PM
info: create check for status code 404 and visually validate check
test: 1
region: us-east-1
target: i-90b15e2e
VPC ID: vpc-31a0cc54 (default vpc)
```
1. Create Check against simpyton target instance (i-90b15e2e):
    * Assert 404 (success)
    * Expected response of the form:
    
    > {"status_code":"404"}
    * Check created successfully

2. Visually validate check
    * Check shows correct target and assertions (failure)
    * Check ID: https://app.opsee.com/check/39qTBzw7yeWRw6RWUbJbLw
    * curl 'https://api.opsee.com/checks' -H 'Pragma: no-cache' -H 'Origin: https://app.opsee.com' -H 'Accept-Encoding: gzip, deflate, sdch' -H 'Accept-Language: en-US,en;q=0.8' -H 'Authorization: Bearer eyJhbGciOiJBMTI4R0NNS1ciLCJlbmMiOiJBMTI4R0NNIiwiaXYiOiJvbzBYaE9EM0FGMDhsbUhKIiwidGFnIjoiV04wVXNrcXg2ZmJ4T1NLWTJ6bW16USJ9.BTbP14cxEsCv_e6cXRuVmQ.djuoS3CM3vPpdPmB.5nmu7uD7GxzHw92ig8PLr7VkaDibzCDDWf_sqZ764ampj4ME99EEGNH1L3jcuDD_jSQQQOovFGwl04z3ktx7L8r2F2HyskOEgMnkX4nNeZxZ9PTdpPVk0DitivYqEzqEnjzeVwrBi0DVCdj3Xqb4Y9xDl_5YyyGedkGV7aShIp92Nfw_SrwN6MMSnaX2JUCoVm6aTuR2Xx-38EXtQc3DjL04Mmm4L-diohfHmWdNNQMcMrfB67hyctDAyRvcEfjYsaNCAAY.c6Q3x0mSAO4Zv2fzRTqgYw' -H 'Accept: */*' -H 'Cache-Control: no-cache' -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/46.0.2490.80 Safari/537.36' -H 'Connection: keep-alive' -H 'Referer: https://app.opsee.com/' --compressed 

    ![incorrect target](./incorrect_target.png) 
    
    #### Post
    
