
---

| Title | Type | Duration | Name | City |
| --- | --- | --- | --- | --- |
| Activity Lifecycle | Lab | "1:00" | James Davis | NYC |

---  
# Activity Lifecycle Lab

## Introduction

Below, you will find three scenarios, and questions following each one.

To the best of your ability, answer the questions **in english**, not in code.

Below the scenarios, you will find a few questions. Answer those however you'd like.

Answer the questions by editing this readme, pushing your changes to your forked repo, and making a pull request.

## Exercise  


####Scenario 1:

Let’s say you made a To Do list app, where you can add things to a list and cross them off. You decide to cross some items off the list and mark them as complete.

When you rotate the device, the things you marked as complete are no longer crossed off.

**Question**: Why did this happen?
<br />Answer: If the screen is reoriented, the data is destroyed and treated like a new activity.

**Question**: How do you fix this issue?
<br />Answer: You must save it in sharedPreferences


####Scenario 2:

The Amazon Kindle Android app allows you to open and read eBooks. You discovered a bug! You opened a book, and read it from the beginning up to page 68. Then, you left the app and closed it completely so you can do other things.

When you opened the app again, and opened the book, it started from page 1 (and not page 68 where you left off)!

**Question**: How would you fix this issue?
<br />**Answer**: onPause -> sharedPreferences. Use putInt to save page number. onResume -> getSharedPreferences, getInt back.


####Scenario 3:

Facebook for Android added a feature last year where, if you started writing a comment on someone’s post and decided not to do so, the app would save a draft of it just in case you changed your mind.

Take this scenario. On a post on Facebook, you click the “comment” button (which opens a new CommentActivity). You start writing a comment, and then change your mind by pressing the back key (which closes the CommentActivity). You click on the “comment” button again, and in the newly-opened CommentActivity, the comment you were writing is still there.

**Question**: How would you implement this feature? Be specific; what lifecycle methods would you use in CommentActivity, and what techniques would you use?
<br />**Answer**: sharedPreferences and saveInstantState of the user input text in onPause, then utilize onResume upon resume.



In your own words…
==================

**Question**: What are the methods of the Activity Lifecycle?
<br />**Answer**: onCreate, onStart, onResume, onPause, onStop, onDestroy

**Question**: What order are the methods called?
<br />**Answer**: See above

**Question**: What is a bundle?
<br />**Answer**: An object used to store different values in order to send them to different parts of the app.

**Question**: How do you get the Shared Preferences of an app?
<br />**Answer**: SharedPref sharedPref = getSharedPreferences();
SharedPreferences.Editor editor = sharedPref.edit();
editor.put();
editor.commit();
String string = sharedPref.getString("Key","Nothing found");
