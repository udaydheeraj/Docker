docker build -t java-multistage . [ creating image ]
docker run java-multistage [ creating container from image ]
In Docker file : first JDk binary with java code executed and comiled and the binary is send to JRE : so the image size is reduced and lot of memory is saved

images size 
java-1stage       latest    d98ebd4e583d   7 seconds ago   420MB
java-multistage   latest    f496fad4f5d2   5 minutes ago   263MB
