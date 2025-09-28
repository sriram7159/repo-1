FROM ubuntu:22.04 AS build

RUN apt-get update && apt-get install -y openjdk-20-jdk && rm -rf /var/lib/apt/lists/*



WORKDIR /sriram1

COPY . /sriram1/

RUN javac Main.java


FROM ubuntu:22.04

RUN apt-get update && apt-get install -y openjdk-20-jre && rm -rf /var/lib/apt/lists/*

WORKDIR /sriram1

COPY --from=build /sriram1/Main.class/ sriram1/

CMD ["java","Main"]