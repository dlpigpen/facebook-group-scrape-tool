# Verba FGPS - Facebook Group Posts Scraper


This tool is considering as a synchronization mechanism between FB group and site storage
Written in Java and `Selenide Web Driver`. Simple `jar` file scrapes facebook group posts and push them to database

### Important news
The tool has been developed to store data into Firebase.
Currently, export data into `.xsl` file and `postgres` is under development
  
#### Requirements:  
- java 8;   
- FireFox 60.3.0esr (64-bit);  
 

#### What does it scrape
- post text
- post images
- post link
- post date
- author name
- author link
- author avatar

#### How it scrapes
1. tool reads last `N` posts from specified facebook group
2. store them into `database` (needs to be intalled on computer)
3. wait `Z` minutes 
4. go to step 1

`N`, `Z` and `database` parameters are configurable

#### Run commands: 

 1. Open JAR with WinRAR and navigate to `BOOT-INF/classes/properties/PostDataToFirebase.properties`
 2. Adjust app parametrs `fb.login fb.pass`, `fb.group.url`, `posts.to.fetch` and save them into archive
	More parameters you may find at `BOOT-INF/classes/application.properties`
 3. Run JAR: `java -jar fbreaper-MILESTONE-2.1.jar --scheduling.enabled=false`
 4. Run JAR with scheduling: `java -jar target\fbreaper-MILESTONE-2.1.jar --scheduling.enabled=true --cron.expression="* */5 * * * *"`
 
### Availabel parameters:  
  
**PostDataToFirebase.properties:**  
 
    fb.login fb.pass   
    fb.group.url
    posts.to.fetch 
     
**application.properties:**  
 
    firebase.jsonfile.path
    firebase.storage.bucket
    cron.expression
    fb.big.images.limit
    fb.big.images.load.timeout
    selenide.timeout


### Contact information
Feel free to tell me what extra features do you require

`email` - postullat2@gmail.com

`telegram` - https://t.me/postullat

`Skype` - postullat2@gmail.com
