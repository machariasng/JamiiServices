ARG BASE_IMAGE
FROM ${BASE_IMAGE}
COPY CompositeApps/*.car ${WSO2_SERVER_HOME}/repository/deployment/server/carbonapps/
COPY resources/wso2carbon.jks ${WSO2_SERVER_HOME}/repository/resources/security/wso2carbon.jks
COPY resources/client-truststore.jks ${WSO2_SERVER_HOME}/repository/resources/security/client-truststore.jks
COPY libs/*.jar ${WSO2_SERVER_HOME}/lib/
COPY --chown=wso2carbon:wso2 resources/Accounts-Family-Bank.db /home/wso2carbon/data/Accounts-Family-Bank.db
ENV accounts_db_url=jdbc:sqlite:/home/wso2carbon/data/Accounts-Family-Bank.db