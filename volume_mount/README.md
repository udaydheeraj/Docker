docker volume create volume1   # creating volume

docker run -it -v volume1/:/data ubuntu    [crating image ubuntu and adding volume to /data file in ubuntu container]

cd /data
echo "hello my name :uday : working on docker volumes" > file.txt


root@e2b6611b8f3f:/# ls
bin  boot  data  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@e2b6611b8f3f:/# cd /data
root@e2b6611b8f3f:/data# ls
file.txt
root@e2b6611b8f3f:/data# cat file.txt
Hello my name : uday : working on docker volumes
root@e2b6611b8f3f:/data#  


Creating Apache container with apache-vol volume::
root@ip-192-168-0-42:/home/ubuntu# docker volume create apache-vol
apache-vol
root@ip-192-168-0-42:/home/ubuntu# docker run -d -p 8001:80 -v apache-vol:/usr/local/apache2/htdocs httpd:2.4
Unable to find image 'httpd:2.4' locally
2.4: Pulling from library/httpd
5b4d5959fc75: Pull complete 
87a14f083967: Pull complete 
9cd0271fa751: Pull complete 
4f4fb700ef54: Pull complete 
0e4bc2bd6656: Pull complete 
4742a9e996d1: Pull complete 
02a2ab6f64c1: Download complete 
a675b28a7d22: Download complete 
Digest: sha256:f9b88f3f093d925525ec272bbe28e72967ffe1a40da813fe84df9fcb2fad3f30
Status: Downloaded newer image for httpd:2.4
beccee4ea8b23c68e525f555c56c638ed1834268b05a070d9b84320a02334c1b
root@ip-192-168-0-42:/home/ubuntu# docker exec -it $(docker ps -aq) sh echo "<h1> name : uday : apache volume in httpd container<h1>" > /usr/local/apache2/htdocs/index.html
bash: /usr/local/apache2/htdocs/index.html: No such file or directory
root@ip-192-168-0-42:/home/ubuntu# docker ps -qa
beccee4ea8b2
root@ip-192-168-0-42:/home/ubuntu# docker exec -it $(docker ps -aq) sh
# echo "<h1> name : uday : apache volume in httpd container<h1>" > /usr/local/apache2/htdocs/index.html
