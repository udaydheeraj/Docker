FROM eclipse-temurin:17-jdk AS  builder

WORKDIR /app1

COPY Helloworld.java .

RUN javac Helloworld.java



FROM eclipse-temurin:17-jre

WORKDIR /app

COPY --from=builder /app1/Helloworld.class .

CMD ["java", "Helloworld"]

