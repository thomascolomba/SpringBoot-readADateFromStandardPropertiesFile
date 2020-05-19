How to read a Date from the standard application.properties with Spring Boot.<br/>
<br/>
How to compile and execute :<br/>
mvn package<br/>
java -jar ./target/readADateFromStandardPropertiesFile-0.0.1-SNAPSHOT.jar<br/>
<br/>
<br/>
---application.properties<br/>
myDate=2020-01-01 00:00:00<br/>
---MyConfigurationBean.java<br/>
private String myDate;<br/>
+getter and setter<br/>
---MyDateConverter (technical class to parse the date from application.properties)<br/>
dateToReturn = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss").parse(source);<br/>
---The class who displays the value of the 'myDate' configuration<br/>
@Autowired<br/>
MyConfigurationBean myConf;<br/>
...<br/>
System.out.println(myConf.getMyDate());<br/>
<br/>
<br/>
The application will read the value '2020-01-01 00:00:00' of the property myDate in the standard application.properties configuration file then display it in the terminal.<br/>


