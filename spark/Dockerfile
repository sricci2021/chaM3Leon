FROM apache/spark:3.5.4

USER root

ADD https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-bundle/1.12.262/aws-java-sdk-bundle-1.12.262.jar /opt/spark/jars/aws-java-sdk-bundle-1.12.262.jar
ADD https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-aws/3.3.4/hadoop-aws-3.3.4.jar /opt/spark/jars/hadoop-aws-3.3.4.jar
ADD https://repo1.maven.org/maven2/org/apache/spark/spark-connect_2.12/3.5.4/spark-connect_2.12-3.5.4.jar /opt/spark/jars/spark-connect_2.12-3.5.4.jar
ADD https://jdbc.postgresql.org/download/postgresql-42.7.5.jar /opt/spark/jars/postgresql-42.7.5.jar

RUN chmod -R +r /opt/spark/jars

RUN curl https://repo1.maven.org/maven2/org/apache/sedona/sedona-spark-shaded-3.5_2.12/1.6.0/sedona-spark-shaded-3.5_2.12-1.6.0.jar --output /opt/spark/jars/sedona-spark-shaded-3.5_2.12-1.6.0.jar; \
    curl https://repo1.maven.org/maven2/org/datasyslab/geotools-wrapper/1.6.0-28.2/geotools-wrapper-1.6.0-28.2.jar --output /opt/spark/jars/geotools-wrapper-1.6.0-28.2.jar; \
    curl https://repo1.maven.org/maven2/pl/tkowalcz/tjahzi/log4j2-appender-nodep/0.9.32/log4j2-appender-nodep-0.9.32.jar --output /opt/spark/jars/log4j2-appender-nodep-0.9.32.jar;


# AGGIUNTA: Imposta le variabili d'ambiente per il PATH di Spark
ENV SPARK_HOME=/opt/spark
ENV PATH=$SPARK_HOME/bin:$PATH

USER spark