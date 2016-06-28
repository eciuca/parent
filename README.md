# Parent project with distribution management, deploy and release plugins

1. Checkout the project
2. Build the 0.0.1 tag
3. Add the following to your settings.xml

```xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"                                        
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"                                   
        xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0                              
        http://maven.apache.org/xsd/settings-1.0.0.xsd">                                        
                                                                                                
<servers>                                                                                       
   <server>                                                                                     
     <id>docker-internal</id>                                                                   
     <username>admin</username>                                                                 
     <password>admin123</password>                                                              
     <configuration>                                                                            
       <email>your@email.com</email>                                                   
     </configuration>                                                                           
   </server>                                                                                    
   <server>                                                                                     
      <id>nexus-snapshots</id>                                                                  
      <username>admin</username>                                                                
      <password>admin123</password>                                                             
   </server>                                                                                    
   <server>                                                                                     
      <id>nexus-releases</id>                                                                   
      <username>admin</username>                                                                
      <password>admin123</password>                                                             
   </server>                                                                                    
</servers>                                                                                      
                                                                                                
<profiles>                                                                                      
   <profile>                                                                                    
     <id>pom-properties</id>                                                                            
     <properties>                                                                               
       <docker-server-id>docker-internal</docker-server-id>                                     
       <docker-registry>localhost:8444</docker-registry>                                        
       <nexus-url>http://localhost:8081/nexus</nexus-url>
    </properties>                                                                               
   </profile>                                                                                   
</profiles>

<activeProfiles>
  <activeProfile>pom-properties</activeProfile>
</activeProfiles>                                                                                     
                                                                                                
</settings>
```
