RealTime News Filtering System

Overview:
This project is a Python-based real-time RSS news filtering application that continuously fetches live news from Google and Yahoo feeds. It filters incoming news stories using customizable keyword, time-based, and logical triggers, and displays relevant alerts in a graphical user interface (GUI).
The system is designed using an event-driven and object-oriented architecture, making it extensible and easy to adapt for different filtering rules.

Key Features:
Live polling of Google News and Yahoo News RSS feeds
Keyword-based filtering on news titles and descriptions
Time-based filtering using before/after triggers
Logical trigger composition (AND, OR, NOT)
Object-oriented trigger framework for extensibility
Tkinter-based GUI for real-time news visualization
Duplicate story prevention using unique GUIDs

System Architecture:
The project is organized into the following logical components:

1. News Retrieval:
   
Uses RSS feeds to fetch live news data.
Parses feed entries into structured NewsStory objects.
Converts HTML content into clean, readable text.

2. Data Model:
   
NewsStory class encapsulates:
Unique ID (GUID), 
Title, 
Description, 
Publication date, 
Link

This abstraction simplifies filtering and display logic.

3. Trigger System:
   
A modular trigger framework determines whether a news story should be displayed.

Trigger Types:

Phrase Triggers: 
TitleTrigger, 
DescriptionTrigger

Time Triggers: 
BeforeTrigger, 
AfterTrigger

Composite Triggers: 
AndTrigger, 
OrTrigger, 
NotTrigger

Triggers can be combined logically to build complex filtering conditions.

4. Filtering Engine:

Applies a list of triggers to incoming news stories.
A story is selected if any trigger evaluates to true.
Prevents repeated display of the same story.

5. Graphical User Interface:
Built using Tkinter.
Displays filtered news in real time.
Updates continuously while polling feeds in a background thread.
Allows safe GUI updates without blocking execution.

Technologies Used:
Python
Tkinter (GUI)
feedparser (RSS parsing)
BeautifulSoup (HTML cleanup)
Threading (non-blocking real-time updates)
Datetime & pytz (timezone-aware time filtering)

How It Works (Execution Flow):

RSS feeds are polled at fixed time intervals.
Each news item is parsed into a NewsStory object.
Triggers evaluate each story based on defined rules.
Matching stories are displayed in the GUI.
The system repeats automatically at the next polling cycle.

Usage:
Install required dependencies.
Run the script.
The GUI window will open and start displaying filtered news in real time.

Customization:

Modify trigger keywords to track different topics.
Add new trigger types by extending the Trigger base class.
Adjust polling frequency by changing the SLEEPTIME variable.
Extend the GUI for additional interaction or logging.

Learning Outcomes:

Real-time data handling
Object-oriented software design
Event-driven programming
GUI development in Python
Logical rule-based filtering systems

Potential Extensions:

File-based trigger configuration. 
Logging filtered news to a database. 
Web-based GUI. 
Integration with APIs for alerts or notifications. 

