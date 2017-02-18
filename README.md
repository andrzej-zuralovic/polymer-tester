# polymer-tester

Docker image for running polymer tests with firefox and chrome

It ws not possible to run selenium chrome tests on gitlab runner.

Main trick was to:
- install virtual display 
- install Java 8
- modify the /usr/bin/google-chrome in order to run with following parameters
	--no-sandbox --disable-setuid-sandbox --allow-sandbox-debugging 



```bash
docker build  -t printminion/polymer-tester .
docker run -it printminion/polymer-tester /bin/bash
```