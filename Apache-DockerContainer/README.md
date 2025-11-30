docker build -t apache-html .
docker run -d -p 8080:80 apache-html

port forwarding : so webpage runs on ec2publicip:8080

to check containers: docker ps -q

to stop : docker stop $(docker ps -q)


