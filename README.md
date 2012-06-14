#Managing Projects with GitHub --
![drupalcat](http://octodex.github.com/images/drupalcat.jpg)

We've tried a lot of project management systems over the years. In some way,
they have always seemed lacking, confusing or just a pain in the rear end. If
they had good tools for project managers, they were confusing to developers. If
they were useful for developers, designers complained about the eye-sores. No
one system ever seemed to satisfy the team.

We recently started using GitHub for project management after the developers
started raving about how much they loved it for managing code. To our
surprise, GitHub has proven a solid option for project management. Our designers have 
even started using it for some of their projects, which I think says something 
about GitHub's aesthetics. With a
little bit of something for each role, GitHub is starting to come out on top as
the tool of choice for hosting code, managing projects, and facilitating
project communication.

##Project Introductions
GitHub is pretty developer-centric. As such, the first thing a developer sees
when they open a project, is a view of the code repository. Below that, GitHub
automatically renders the README file found in the root of the code base. It's a
very typical practice for software projects, especially open source software
projects, to have this file in place. The README can be in various formats, but
a favorite of mine is [Markdown](http://daringfireball.net/projects/markdown/).
Simply giving the README an extension of .md tells GitHub to render your
README.md using the Markdown syntax. Even better, GitHub has it's
own [flavor of markdown](http://github.github.com/github-flavored-markdown/).
Since the developers of your project see the README first, this is a great
place for information that will get them up and running with the project as
quickly as possible. Be concise. If you need to write more than a few sentences,
chances are, you should be linking off to more in-depth documentation in your
project's wiki. Here's a quick guideline of some of the things that you might
want to include in your README.

1. A quick project overview.

    Provide a short description of the project's goals and a bit of
    background. Any links that you frequently access are also good to include up
    at the top as well, for easy access. Everyone loves easy access.

1. Information about the directory structure.

    Typically we have more than just Drupal in our repository root, so it's
    helpful to have a brief description of what is in there. We typically have a
    [drush folder](https://github.com/Lullabot/drupal-boilerplate/tree/master/drush)
    for aliases and commands, as well as a patches directory with its own README.

1. How to get started developing.

    Tell the developers what the best way to jump into the project might be.
    Things like, "clone this repository, create a feature branch, run the installer,
    download a copy of the database, etc.. Whomever reviews the 
    pull request should also do things
    like remove the remote branch from the repository once it is merged."

1. Code promotion workflow.

    It's a good idea to outline your development process, as it may change from
    project to project. Do you want people to fork your repository and send pull
    requests; create feature branches and send pull requests; or just go ahead
    and commit to master? Let the developers know up-front, so there's no
    confusion.

1. Environments.

    Outline information for your dev, staging and live environments, if you have
    them. Also, outline the process for getting things to the various places.
    How do I make sure my code is on staging? What is the best way to grab a
    database dump? We like to setup drush aliases for each environment ahead of
    time as a means of outlining this information and giving developers a good
    starting point. This document contains some example commands for doing some typical
    operations. [Here's an example](https://github.com/Lullabot/drupal-boilerplate/blob/master/drush/aliases/example.aliases.drushrc.php).

1. Links to where to find more information.

    Typically this is our wiki, where we keep more detailed documentation and
    notes on things; project details like the original proposal's SOW,
    credentials to environments, Scrum Notes, Pre-launch checklists, etc.

We've attempted to create a [drupal-boilerplate](https://github.com/Lullabot/drupal-boilerplate),
of sorts, for our Drupal projects which we're continuously re-using for new
projects and modifying when we find things that work better. Take a look, and if
you find it useful, please feel free to use it! If you find anything missing, or
have ideas on improving it, please fork it and send us a pull request!

## Working with GitHub Issues

GitHub has a pretty simple issue management system for bug tracking, but it is
flexible enough to be a pretty powerful tool for managing entire projects, large
and small. It has issues which can reference each-other; tags for attaching meta
data to your issues; methods for attaching code to your issues; and even
milestones for grouping and focusing your issues within time blocks.

### Referencing and Association

Issues can be associated with each other by simply throwing an #issue-number
(ex: #3) within the body of another issue. This is useful in many ways. Firstly,
it keeps the relationship simple. We don't have to worry about what kind of
relationship it is (parent/sibling/child), just that it's related. Nevertheless, there
are a couple of tricks that make this a little more useful if you understand how
it works. Let me give you an example.

Let's say you typically create an issue for a content type, and one of the
fields on that content type is a taxonomy vocabulary. You probably want to break
that vocabulary creation out into it's own issue. So you create the issue for the
news content type
![news-content-type](https://img.skitch.com/20120607-kday7nnj62xedpty25yxgmbd93.jpg)

and then you create an issue for the taxonomy vocabulary and, within your
description, link to the news issue.
![tags-taxonomy](https://img.skitch.com/20120607-gah6niabiwa1ybae99rmccnii9.jpg)

Just by putting in the #ticket-number (in this case #4) GitHub creates a link to
the news issue AND it places a back-link reference within the news issue to your
tags issue!
![news-tags](https://img.skitch.com/20120607-fkc64xhq47sq5ph7bj48d3ffnj.jpg)

As a part of this reference you will notice that it also gives you the status of
the referenced issue. Very handy for whomever is assigned this news issue. They
can easily see the status of it's 'dependency'. I use that term loosely because
it is a dependency in this instance, but not always.

### Issue Tags

Tags are a simple and effective way to add metadata to your issues. A lot of
systems tend to create fields and categories with various values in an effort to
allow you finite control of the metadata for an issue. I've found the simple
tagging system that GitHub employs to be very efficient and more flexible.

GitHub comes with a few tags by default: bug, duplicate, enhancement, invalid,
question, and won't fix. These give you a good idea of how to start using tags.
For example, "bug" is a type of issue, while "won't fix" is more of a status.
Tags can be anything, and if chosen wisely, can give any developer an immediate
clue as to what sort of ticket it is, what section it might apply to, or what
status it is in at a quick glance.

While they're useful for developers, they're also good for the organizer of the
project in that they serve as a great filtering mechanism as well. For instance,
just by selecting various tags, I can see all of the issues that are "migration"
issues for "taxonomy", or "content types."
![content-migration](https://img.skitch.com/20120607-kfqtrgq148ywk7xxp24fcy74wp.jpg)

### Attach Code to an Existing Issue

Pull requests are an amazing tool for code collaboration. If you're new to the
concept, check out this [pull request demo](https://vimeo.com/41045197). It's a
quick and easy way for developers to basically create a copy of the code base
(by either forking or branching) and suggest modifications to the existing
code, or contribute new code. It allows the other members of the project to
then review that code, make their own suggestions with in-line commenting, and
then make a decision as to whether to merge it into the main code base or not.
We've found the in-line commenting with pull requests to be immensely useful
since they keep everyone in the project in the loop with changes that are
happening.
![code-comments](https://img.skitch.com/20120609-e6pfy9sts7nbi2p3kw4um1iikx.jpg)

Pull requests in general are a great means of peer review and have helped to
keep the quality of our code up to everyone's standards. There's a bit of
overhead in that it may take a little longer for some new piece of code to be
merged in, so plan accordingly. But this also means we find bugs sooner,
typically before they're actually introduced into the master branch of the code.

I had one gripe with pull requests: when you create one through
GitHub's web interface, it basically creates a new issue. Though you can
certainly reference a particular issue within your pull request, it's still a
separate issue. However, through a nice command-line tool called [Hub](https://github.com/defunkt/hub),
we've found there's a way to [turn issues into pull requests](http://www.youtube.com/watch?v=suS3lDn20HY)!
Very handy for keeping your discussions and code all in one place and not having
to deal with multiple issues about the same thing.

### Milestones

GitHub has a mechanism for milestones that is actually quite typical of many
project systems these days. When you create a new milestone, it simply has a
title, description, and a date choosing mechanism.
![milestone](https://img.skitch.com/20120609-4nfhurufifhbxpic32j1ynt1b.jpg)

You can have a nice overview during the time-boxed iteration that gives you the percentage
complete.
![closed](https://img.skitch.com/20120609-1kcnp51njk55qqb71nfh5dssii.jpg)

We tend to only plan one sprint ahead, but there is a milestone created for each
iteration up until the end of the project. 
![open](https://img.skitch.com/20120609-fbaj8534tjhmt2t7jc661pquky.jpg)

We grab these tickets from the Backlog, which is essentially just any ticket
that is **not** in a Sprint.
![backlog](https://img.skitch.com/20120609-tx4b1a2iebb1a7i1f5higsdrf.jpg)


## Huboard

GitHub's issue tracking system lacks a mechanism for prioritizing your issues. You
could probably come up with tags for High, Medium and Low priorities, but I tend
to prefer an ordered list with the highest priority things on top.

Enter [Huboard](https://github.com/rauhryan/huboard), which gives you a nice
Kanban-style interface (similar to [Trello](https://trello.com/)) right on top
of the GitHub api. You're looking at your GitHub issues, but with a different
interface. The instructions for setting this up are quite sufficient, so I'll
not re-iterate those, but I've found that it's quite easy and quick to setup on
[Heroku](http://www.heroku.com/) with very little maintenance overhead. With
Huboard, we now have a means of seeing what the priority tasks are for the week
and it gives developers an easy way to see what they should work on next.
![huboard](https://img.skitch.com/20120609-my9ug4h3us75y98g71tdbssfp9.jpg)

## Logins

Some project management systems require a new login for every instance of the software. For instance,
if you have two different clients using the same project management software you may
have to remember two different username and password combinations and your authentication
will not transfer from one to the other. Github allows users to access all the projects and repositories 
you have permission to without multiple authentication.

---
Github is lean and spare, and you may find there are features missing that you're accustomed to. Luckily,
the team over at GitHub is continually making improvements to their product and they [blog](https://github.com/blog/)
about it often.

In summary, GitHub is great for the technically-minded person, but less
tech-savvy people may not find it as attractive. I'm still working on ways to
report on progress to project stakeholders in a more visual way and when I
find one I like, I plan to update you all.

If you have any suggestions on things we might also do to improve our process,
or would like to share with us some of the exciting things you're doing with
your own processes, please hit us up in the comments section! We'd love to hear
from you! And remember, Lullabot loves you!