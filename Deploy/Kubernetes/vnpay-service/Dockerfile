FROM openjdk:17-jdk-slim
RUN set -eux; \
    apt-get update; \
    apt-get install -y --no-install-recommends tzdata; \
    ln -snf /usr/share/zoneinfo/Asia/Ho_Chi_Minh /etc/localtime; \
    echo "Asia/Ho_Chi_Minh" > /etc/timezone; \
    apt-get clean; \
    rm -rf /var/lib/apt/lists/*
RUN mkdir -p /app
WORKDIR /app
COPY target/vnpay-service-0.0.1-SNAPSHOT.jar vnpay-service-0.0.1-SNAPSHOT.jar
ENTRYPOINT ["java", "-jar", "vnpay-service-0.0.1-SNAPSHOT.jar"]
