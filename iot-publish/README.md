ensure that  

adding below to policy, <<account_id>>

"arn:aws:iot:us-east-2:<<account_id>>:topic/energy/readings"


while running,

```
PS C:\....\Downloads\connect_device_package> python aws-iot-device-sdk-python\samples\basicPubSub\energy-device.py -e a1ygnd8pydzgx8-ats.iot.us-east-2.amazonaws.com -r root-CA.crt -c device-1.cert.pem -k device-1.private.key

```
