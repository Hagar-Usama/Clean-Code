# /* _Comments_ */
 
## Table of Contents

* [Good Comments](#Good-Comments)
* [Bad Comments](#Bad-Comments)
* [References](#References)
---
## Good Comments
---

## Bad Comments

### Mumbling
 His mumbling left behind an _enigma_
```java
public void loadProperties()
   {
     try
     {
      String propertiesPath = propertiesLocation +
       ”/” + PROPERTIES_FILE;
      FileInputStream propertiesStream = new
       FileInputStream(propertiesPath);
      loadedProperties.load(propertiesStream);
     }
     catch(IOException e)
     {
       // No properties files means all defaults are loaded
     }
   }

```
### Redundant Comments
> If comments are not inforamtives, add no value to your code, just remove them.

 The comment probably takes longer to read than the code itself.
```java
 // Utility method that returns when this.closed       is true.  Throws an exception   // if the timeout is reached.

 public synchronized void waitForClose(final long timeoutMillis)  throws Exception   {     
      if(!closed)      {       
       wait(timeoutMillis);
      if(!closed)
      throw new Exception("MockResponseSender could not be closed");      }

```

### Misleading Comments
> Code never lies, comments do sometimes

> Comments should desribe what your code **actualy** do, but not what you **wish** your code to do.


### Mandated Comments
> Do not add a comment for each function or  variable. If they do not need commenting, leave them uncommented.
```java
/**
    * 
    * @param title The title of the CD
    * @param author The author of the CD
    * @param tracks The number of tracks on the CD
    * @param durationInMinutes The duration of the CD in minutes
    */
   public void addCD(String title, String author, 
                      int tracks, int durationInMinutes) {
     CD cd = new CD();
     cd.title = title;
     cd.author = author;
     cd.tracks = tracks;
     cd.duration = duration;
     cdList.add(cd);
   }

```
### Journal Commnets
>  Adding a log-like comment isn't a good idea.<br> ⚠ Hey, we have version control now!

```java

 * Changes (from 11-Oct-2001)
 * --------------------------
 * 11-Oct-2001 : Re-organised the class and moved it to new package 
 *               com.jrefinery.date (DG);
 * 05-Nov-2001 : Added a getDescription() method, and eliminated NotableDate 
 *               class (DG);
 * 12-Nov-2001 : IBD requires setDescription() method, now that NotableDate 
 *               class is gone (DG);  Changed getPreviousDayOfWeek(), 
 *               getFollowingDayOfWeek() and getNearestDayOfWeek() to correct 
 
 *               bugs (DG);
 * 05-Dec-2001 : Fixed bug in SpreadsheetDate class (DG);
 * 29-May-2002 : Moved the month constants into a separate interface 
 *               (MonthConstants) (DG);
 * 27-Aug-2002 : Fixed bug in addMonths() method, thanks to N???levka Petr (DG);
 * 03-Oct-2002 : Fixed errors reported by Checkstyle (DG);
 * 13-Mar-2003 : Implemented Serializable (DG);
 * 29-May-2003 : Fixed bug in addMonths method (DG);
 * 04-Sep-2003 : Implemented Comparable.  Updated the isInRange javadocs (DG);
 * 05-Jan-2005 : Fixed bug in addYears() method (1096282) (DG);
```


### Noise Comments
* Stating the Obvious
```javascript
// Avoid Monkey Patches from Application Insights// Avoid Monkey Patches from Application Insights
bootstrap.avoidMonkeyPatchFromAppInsights();
// Enable portable support
bootstrap.configurePortable();
// Enable ASAR support
bootstrap.enableASARSupport();
// Load CLI through AMD loader
require('./bootstrap-amd').load('vs/code/node/cli');

```

### Scary Noise Comments

```java
   /** The name. */
   private String name;

   /** The version. */
   private String version;

   /** The licenceName. */
   private String licenceName;

   /** The version. */
   private String info;

```

---
# Don't use a comment when you can use a function or a variable

Consider the following stretch of code:
```java
// does the module from the global list <mod> depend on the
// subsystem we are part of?
if (smodule.getDependSubsystems().contains(subSysMod.getSubSystem()))
```
This could be rephrased without the comment as
```java
ArrayList moduleDependees = smodule.getDependSubsystems();
String ourSubSystem = subSysMod.getSubSystem();
if (moduleDependees.contains(ourSubSystem))
```


//Actions/////////////////////////
# Position Markers

   In general banners are clutter that should be eliminated.A banner is startling and obvious 
   if you don’t see banners very often. So use them very sparingly, and only when the benefit is significant. 
   If you overuse banners, they’ll fall into the background noise and be ignored.

# Closing Brace Comments

   If you find yourself wanting to mark your closing braces, try to shorten your functions instead.
   
```java

    public class wc {
public static void main(String[] args) {
BufferedReader in = new BufferedReader(new InputStreamReader(System.in));
String line;
int lineCount = 0;
int charCount = 0;
int wordCount = 0;
try{ while ((line = in.readLine()) != null) {
lineCount++;
charCount += line.length();
String words[] = line.split("\\W");
wordCount += words.length;
} //while
System.out.println("wordCount = " + wordCount);
System.out.println("lineCount = " + lineCount);
System.out.println("charCount = " + charCount);
} // try
catch (IOException e) {
System.err.println("Error:" + e.getMessage());
} //catch
} //main
}

```
# Attributions and Bylines
/* Added by Rick */
Source code control systems are very good at remembering who added what, when.
There is no need to pollute the code with little bylines.
Again, the source code control system is a better place for this kind of information.

# Commented out Code
  ```java
  InputStreamResponse response = new InputStreamResponse();
response.setBody(formatter.getResultStream(), formatter.getByteCount());
// InputStream resultsStream = formatter.getResultStream();
// StreamReader reader = new StreamReader(resultsStream);
// response.setContent(reader.read(formatter.getByteCount()));
```

Others who see that commented-out code won’t have the courage to delete it. They’ll think
it is there for a reason and is too important to delete. 

Good source code control systems  will remember the code for us. We don’t have to comment it out any more. Just
delete the code. We won’t lose it. Promise.

## References
* Clean Code - ch4
* [Five code comments you should stop writing // and one you should start](https://www.freecodecamp.org/news/5-comments-you-should-stop-writing-and-1-you-should-start-4d66a367cd2c/)
* [Comments In Your Code](https://medium.com/better-programming/comments-in-your-code-730cfd1dde02)
* [Clean Code – Comments and Formatting](https://www.todaysoftmag.com/article/1120/clean-code-comments-and-formatting)
* [Clean Code Slides](https://www.slideshare.net/arturoherrero/clean-code-8036914)