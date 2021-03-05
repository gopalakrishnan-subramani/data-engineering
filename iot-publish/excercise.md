energy-device.py

    pushing data every 5 seconds

        push data to kinesis firehose

        part 0:
            300 seconds 
            group the messages
            s3 

        part 1:
            add a rule, if the v > 145
                call a lambda as action
                    let that lambda to insert the readings into dynamo db

        part 2:
            300 seconds
            group the messages
            call lambda /new lambda 
            whihc convert json to csv 
