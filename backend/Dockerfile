# Étape 1 : Construction (Build)
FROM eclipse-temurin:21-jdk-alpine AS myapp-build
ENV MYAPP_HOME=/opt/myapp
WORKDIR $MYAPP_HOME

# Installation de Maven
RUN apk add --no-cache maven

# Optimisation du cache : on télécharge les dépendances d'abord
COPY pom.xml .
RUN mvn dependency:go-offline

# Copie du code et compilation
COPY src ./src
RUN mvn package -DskipTests

# Étape 2 : Exécution (Run)
FROM eclipse-temurin:21-jre-alpine
ENV MYAPP_HOME=/opt/myapp
WORKDIR $MYAPP_HOME

# On ne copie QUE le résultat final (.jar) de l'étape précédente
COPY --from=myapp-build $MYAPP_HOME/target/*.jar $MYAPP_HOME/myapp.jar

ENTRYPOINT ["java", "-jar", "myapp.jar"]