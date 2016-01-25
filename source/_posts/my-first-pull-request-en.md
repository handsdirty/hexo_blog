---
title: First Experience on GitHub Pull Request | Add Comments to Hexo Blog GuestBook Page
date: 2015-12-30 21:33:29
categories:
- Tech
tags:
- GitHub
- English
---
Today is a special day for me that my first pull request in GitHub got accepted. Though it is just a two-line change, it is the very first time that I 'improved' someone else's codebase in GitHub community.  Shamelessly speaking, the positive effect will be passed on and on as time and users accumulate.

*Non-tech-savvy readers, you can skip following paragraphs and read the story section directly.*
Last night, I was doing configuration for this blog. I found the [reference blog](https://www.haomwei.com/) has a guestbook page, but my newly created guestbook page doesn't contain a discuss section. How can we call it guestbook if guests cannot comment on it? After reading the original blog writer's notes, I found he did it in a brute-force approach by adding disqus *html/javascript* code to the markdown text. But I couldn't reproduce it anyway and some other users complained about the same issue. After I did more research, it turns out such themes treat *page* and *post* differently and the *page* usually doesn't contain comment system. It can definitely be hacked. I found some examples in *swig* and *ejs* but the theme I am using is written in *jade*. I was very confused as I knew little about *jade.*
Eventually after midnight, I figured out the right code location and how it works. I just needed to add code for the comment system in the section where page files were generated. And it can be controlled by `page.comments` variable, so that I can make the about page with no comments but the guestbook page with comments. Following is the code:
```
  if page.comments
    include _partial/comments
```
Then I realized that I can add it to the original codebase as my first code change. Let's do it. And it seems like the so-called pull request. I was a little confused when I heard the concept for the first time. Because obviously I was pushing the code to the owner's codebase, how can we call it a pull? Maybe it means to request the owner to pull? Well, no problem. It should be similiar to how we check in code at work, and it actually is. As a professional programmer, I updated the English document as well. It was 2am after I sent out the pull request and I was excited. The next morning when I woke up at 10am, the owner approved and merged my pull request. After work, I found the owner updated the Chinese document as well. For details, [see my first pull request here](https://github.com/tufu9441/maupassant-hexo/pull/32).

*Now story time!*
This day is actually late for 5 years.
In 2010, the winter of my 3rd year in college, I heard about GitHub for the first time in the CS Building of National Taiwan University. As an exchange student, I attended a talk for programming careers. The speaker mentioned JitHat (by sound) for several times, and said it is so useful. I raised my hand to question, "What is JitHat?" Then I heard its real name, "GitHub". A Mrs. Professor in front row spoke up, "Every programmer and CS student should know about GitHub." Then everyone in the classroom laughed. After the talk, I opened the website quietly and registered my account. But I still didn't know what it is about, what repo and pull request mean, what is the relationship between git and github, and what the users are there for.
In first half year of 2011, I downloaded a GitHub Handbook shared by a classmate, scanned it and closed it.
In second half year of 2011, as an intern in Microsoft, I needed to work with my mentor in the same codebase. My mentor was the top student in science (Li Ke Zhuang Yuan) of Chengde City. He asked whether I used any version control system such as svn or git. I answered, "I heard about them but I never tried."
In 2013, I used svn for the first time when I was on a project with a senior lab mate.
In 2013, after 3 years, I created my first GitHub repo to save my code for programming contests and interview questions.
In 2013, a class project by my friends and I was hosted in GitHub.
In 2013, I was helping with a project for a girl who looks similiar to Tang Wei. She was successfully converted by me to a GitHub user. But later, she was together with a talented handsome senior fellow student.
In 2014, I created a GitHub repo for my Masters' project.
In June 2015, I created a blog in GitHub but never started writing.
In the end of 2015, I restarted my blog, read and forked someone else's code, and did my first pull request.

One thing which I admire a lot about American students (including Chinese overseas students in U.S.) is that, they have a strong culture and tradition for tech community. But in China, or in the environment where I grew up around, we still have a long way to go.

By online tech community such as Github, Quora and Stackoverflow, we can share experiences, discuss problems and make friends. We write blogs and do projects. Together we write blogs and do projects. What a spectacular scene it is!

*Epilogue*
Our journalist walked across the intersection of Castro Street and Villa Street in Mountain View, and interviewed a programmer who has just achieved his first pull request, "What are you thinking about right now?"
The programmer will pick up the microphone and said, "Thanks everyone. If I can contribute some solid code and features to famous repos like TensorFlow in the coming year, it will sound really cool."

[Click Here for Chinese Version](2015/12/30/my-first-pull-request/)