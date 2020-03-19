# Java 11 basic fetcher app

This project is intended to reproduce a bug about java.net.http.HttpClient class. 

## How to reproduce it ? 

Please download mockoon app and import mockoon.json file. Check the port used and change it if needed in BasicFetcherApp class. 
Then, start the app using open jdk11.0.6 and get the app pid in logs, and run ss command as follow 

```shell script
ss -np | grep <APP PID> | grep CLOSE-WAIT 
```

Then, you're supposed to see 100 CLOSE-WAIT socket

## Notes

This bug looks like those : 
* https://bugs.openjdk.java.net/browse/JDK-8221395
* https://bugs.openjdk.java.net/browse/JDK-8232965
