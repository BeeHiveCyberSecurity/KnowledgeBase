# Splunk Queries

index=pan sourcetype="pan:threat" ",threat," (critical OR high) (severity=critical OR severity=high) action!="blocked" action!="dropped" | bucket span=1h \_time | stats values(signature) as signature mode(dest) as dest values(dest\_port) as dest\_port values(file\_name) as file\_name values(file\_hash) as file\_hash count by \_time, src, severity, action | eval signature=mvjoin(signature," , ") | eval dest\_port=mvjoin(dest\_port," , ") | eval file\_name=mvjoin(file\_name," , ") | eval file\_hash=mvjoin(file\_hash," , ")
