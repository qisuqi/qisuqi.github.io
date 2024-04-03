---
title: "Film Logging and Recommendation iOS App"
collection: projects
permalink: /projects/film-analysis-swift/
excerpt: ""
---

## Introduction

After building the film logging/recommendation [app]({% link _projects-other/film-analysis-streamlit.md %}) using 
Streamlit, I have realised that logging films is not really convenient. Firstly, Streamlit puts your app to "sleep" after
a period of inactivity. Also, although the Streamlit app looks great on a PC or laptop, on phone on the other hand, not 
so great...

Therefore, I decided to build an iOS app that would make logging films more easily accessible and learn another 
programming language at the same time. I will go through some code snippet and how it looks on an iPhone below. Full code
is not yet available on GitHub, as some functionalities are not fully implemented. 

## Database
At first, I decided to use Apple's own [CoreData](https://developer.apple.com/documentation/coredata/) as the database 
for its compatibility with iOS app development. Storing, fetching, persisting, and caching data worked seamlessly. 
However, I soon realised that the only way to sync core data is through Apple's [CloudKit](https://developer.apple.com/documentation/cloudkit/), and to use CloudKit would require an Apple Developer account
that comes with a subscription fee. So, after a bit of searching and reading, I decided to use [RealmSwift](https://realm.io/realm-swift/) powered by MongoDB. RealmSwift can basically do what CoreData does, plus it allows
cloud data syncing. 

Firstly, some _Persisted_ properties are defined, these properties will be persisted in the database.

```
    @Persisted var title = ""
    @Persisted var director = ""
    @Persisted var genre = ""
    @Persisted var subGenre = ""
    @Persisted var ratingQ = 0.0
    @Persisted var ratingG = 0.0
    @Persisted var books = false

```

To fetch data from the database, there are two options: _@ObservedRealmObject_ or _@ObservedResult_. To use one of the
state object's property, _@ObservedRealmObject_ can be used. On the other hand, _@ObservedResult_ is a mutable collection
that contains all the data. 

## User Authentication

For user authentication, an _Observable Object_ is used that is hooked with MongoDB's app service. To allow user to 
sign up would look like something like this:

```
    func signup() {
        
        let client = app.emailPasswordAuth
        
        isLoading = true
        errorMessage = nil
        
        client.registerUser(email: email, password: password) { [weak self] error in
            DispatchQueue.main.async {
                if let error = error {
                    self?.errorMessage = "signup error: \(error.localizedDescription)"
                    self?.isLoading = false
                }
                else {
                    self?.login()
                }
            }
            
        }
    }
    
```

## OverView
When the app is opened, depending on the state of fetching data from MongoDB, either the Welcome View or the OverView
will be displayed. The OverView looks like this:

<p float="left">
    <img src='/images/ios-overview.png' width="350"/>
    <img src='/images/ios-detail.png' width="350"/>
</p>

The Overview View displays all films we have watched, with title, director, and average rating. Clicking on the film
title would bring you to a detailed view with this film's director, genre, sub-genre, if it's based on books, if it's
based on true story, and average rating with our own rating for this film. One cool thing the film detail view has is 
the book symbol would be filled if it is based on book (likewise for true story), and would be empty if not. 

<p float="left">
    <img src='/images/ios-search.png' width="350"/>
    <img src='/images/ios-overview-edit.png' width="350"/>
</p>

The tab at the bottom allows user to navigate between views easily. This Overview View is searchable using both film 
title and director. Clicking the Edit button also allows user to delete any data entry by batch. Swiping left would
delete each data entry one by one. To submit a film, click on the Add button would bring up a form for user to fill in.
If the Clear button is pressed, the form is cleared and user can submit another film. 

<p float="left">
    <img src='/images/ios-overview-delete.png' width="350"/>
    <img src='/images/ios-submit.png' width="350"/>
</p>

## Visualisation

In Visualisation, similar plots in the Streamlit app are shown. Different options can be chosen using the picker at the
top. The below is a visualisation example of ratings per director. The _Sort by:_ option allows user to choose between
sort the visualisation by rating or by director. 

<p float="left">
    <img src='/images/ios-vis.png' width="350"/>
    <img src='/images/ios-vis2.png' width="350"/>
</p>

## Recommend

This is the functionality still under development. At the moment, the model is built with Apple's 
[Create ML](https://developer.apple.com/documentation/createml/). However, the prediction/recommendation results are not
very good as CreatML only takes 2 inputs, and the recommendation list would be exactly the same everytime. But the idea
is, user would select a film from the drop-down list and how many films they wish to recommend, then a list of recommended
films would be displayed. As you can see, the recommendation can be improved a lot!

<p float="left">
    <img src='/images/ios-recom.png' width="350"/>
    <img src='/images/ios-recom2.png' width="350"/>
</p>

I am planning to build an item-item recommendation system, which would take our rating into account and recommend films
based on our rating. This might involve building the model in Python then convert the format to something that is usable
with iOS and Swift. 

## User

In this view, our own top-rated film, director, and genre are displayed. 

<p float="left">
    <img src='/images/ios-user.png' width="350"/>
    <img src='/images/ios-user2.png' width="350"/>
</p>

## Watch List

Finally, the watch list shows the films that we are planning to watching. One cool functionality that I have implemented
is clicking on the title leads to the iMDB page. 

<p float="left">
    <img src='/images/ios-list.png' width="350"/>
    <img src='/images/ios-imdb.png' width="350"/>
</p>

## Final Words

There are so many more functionalities that I want to implement, for example, clicking on the bar in the visualisation 
that can leads to the film details, or hook up to iMDB API so all the information can be filled in automatically (but 
iMDB API is VERY pricey). 
