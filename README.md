# Log4j zero day RCE
https://www.lunasec.io/docs/blog/log4j-zero-day/

# Apache-Log4j
Apache Log4j Remote code execution

> Attackers can directly construct malicious requests to trigger remote code execution vulnerabilities. Vulnerability exploitation does not require special configuration, verified by Alibaba Cloud security team
> Equally affected: Apache Struts2、Apache Solr、Apache Druid、Apache Flink

![image](https://user-images.githubusercontent.com/45926593/145425339-47c71230-87d2-4519-8919-9c3520850f83.png)


### Repair plan：

（1）Modify jvm parameters
-Dlog4j2.formatMsgNoLookups=true

（2）Change setting
Add the log4j2.component.properties configuration file under the application classpath, log4j2.formatMsgNoLookups=true

## Issue reproduce

Create dummy ldap server for testing
https://www.npmjs.com/package/ldap-server-mock

And use wireshark to capture ldap traffice to verify (filter: tcp.dstport==1389)
