#Managing Projects with GitHub
We've tried a lot of project management systems over the years and in some way they have always seemed lacking or confusing or just a pain in the rear end. If they had good tools for Project Managers, they were confusing to developers. If they were useful to developers, designers complained about the eye-sores. No one system ever seemed to satisfy the team.

We recently started using GitHub for project management after the developers started raving about how much they loved it for their code tools, and to our surprise, there are a lot of very competent organizational tools that come with any given project, and our designers even started using it for some of their own projects, which I think says something about GitHub's aesthetics. Will a little bit of something for each role, GitHub is starting to come out on top as the tool of choice for hosting code, managing projects, and greatly facilitating project communication to boot!

Some of the things I'd like to show you are pretty general practices we've been using, and are not entirely dependent upon GitHub, but rather just some good general practices. Mostly I'll be talking about how we are doing these things within GitHub and how we're using GitHub's tools for accomplishing our project goals. So whether you like GitHub as a tool for your projects or not, I hope you will get at least something out of this.

##Project Introductions
GitHub is pretty developer-centric, and as such, the first thing a developer sees when they to they open the project, is a view of the code repository. GitHub then automatically renders the README file found in the root of the code base. It's a very typical thing for software projects, especially open source software project to have this file in place. The README can be in various formats, but a favorite of mine is [markdown](http://daringfireball.net/projects/markdown/). Simply giving the README an extension of .md tells GitHub to render your README.md using the markdown syntax. But even better, is that GitHub has it's own [flavor of markdown](GitHub Flavored Markdown). Being that the developers of your project see the README first, this is a great place to give them the best information. Be concise and if you need to write more than a few sentences, chances are you should probably be linking off to more in-depth documentation in your wiki. Here's a quick guideline of some of the things that you might want to put in your README.

1. A quick project overview.

    Give a few sentences of the project's goals and maybe a small bit of background. Any links that you frequently access are also good to throw up at the top as well, for easy access. And everyone loves easy access.

1. Information about the directory structure.

    Typically we have more than just Drupal in our repository root, so it's helpful to have a brief description of what is in there. We typically have a drush folder for aliases and commands, as well as a patches directory with it's own README.

1. How to get started developing.

    Tell the developers what the best way to jump into the project might be. Things like, clone this repo, create a feature branch, and send a pull request for review. Whomever reviews the pull request should also do things like remove the remote branch from the repository once it is merged.

1. Development process.

    It's a good idea to outline your development process as it may change from project to project. Do you want people to fork your repository and send pull requests, create feature branches and send pull requests, or just go ahead and commit to master? Let the developers know up-front so there's no confusion.

1. Environments.

    Outline information for your dev, staging and live environments (if you have them) and also outline the process for getting things to the various places. How do I make sure my code is on staging? What is the best way to grab a database dump? We like to setup drush aliases for each environment ahead of time as a means of outlining this information and giving developers a good starting point. Then document some example commands for doing some typical operations. [Here's an example](boiler-plate).

1. Links to where to find more information.

    Typically this is our wiki, where we keep more detailed documentation and notes on things. Project details like the original proposal's SOW, credentials to environments, Scrum Notes, Pre-launch checklists, etc.

We've attempted to create a [drupal-boilerplate](https://github.com/Lullabot/drupal-boilerplate) of sorts for our Drupal projects which we're continuously re-using for new projects and modifying when we find things that work better. Take a look, and if you find it useful, please feel free to use it! If you find anything missing, or have ideas on improving it, please fork it and send us a pull request!

## Issue Associations and Back References

GitHub has a pretty simple issue management system for bug tracking, but in the right hands it's flexible enough to be a pretty powerful tool for managing projects, large and small. It has issues which can reference each-other, tags for attaching meta data to your issues, methods for attaching code to your issues, and even milestones for grouping and focusing your issues to be done within time blocks.

Issues can be associated with each other by simply throwing a #issue-number (ex: #3) within the body of another issue. This is useful in many ways. Firstly, it keeps the relationship simple. We don't have to worry about what kind of relationship it is (parent/sibling/child) just that it's related. However, there are a couple of tricks that make this a little more useful if you understand how it works, so let me give you an example.

Let's say you typically create an issue for a content type, and one of the fields on that content type is a taxonomy vocabulary. You probably want to break that vocabulary creation out into it's own issue. So you create the issue for the news content type
![news-content-type](https://img.skitch.com/20120607-kday7nnj62xedpty25yxgmbd93.jpg)
and then you create an issue for the taxonomy vocabulary and within your description, link to the news issue.
![tags-taxonomy](https://img.skitch.com/20120607-gah6niabiwa1ybae99rmccnii9.jpg)
Just by putting in the #ticket-number (in this case #4) GitHub creates a link to the news issue ticket AND it also places a back-link reference within the news issue to your tags issue!
![news-tags](https://img.skitch.com/20120607-fkc64xhq47sq5ph7bj48d3ffnj.jpg)
With this reference you will notice that it also gives you the status of the referenced issue. Very handy for whomever is assigned this news issue, because they can easily see the status of it's 'dependency'. I use that term loosely, because in this instance it's a dependency, but not always. It's a logical conclusion in this instance.

## Issue Tags

Tags are a simple and effective way to add meta data to your issues. A lot of systems tend to create fields and categories with various values in a effort to allow you to have finite control of the meta data for an issue, but I've found the simple tagging system that GitHub employs to be very efficient and extremely flexible.

GitHub comes with a few by default: bug, duplicate, enhancement, invalid, question, and won't fix. These give you a good idea of how to start using them. For example, "bug" is a type of issue, while "won't fix" is more of a status. Tags can be anything, and if chosen wisely, can give any developer an immediate clue as to what sort of ticket it is, what section it might apply to, or what status it is in at a quick glance.

But while they're useful for developers, they're also good for the organizer the project in that they serve as a great filtering mechanism as well. For instance, just by selecting various tags, I can see all of the issues that are "migration" issues for "taxonomy", or "content types".
![content-migration](https://img.skitch.com/20120607-kfqtrgq148ywk7xxp24fcy74wp.jpg)

##Milestones
* backlog
* 1 week sprints
* shorter review/planning meetings


##Pull requests
* turn issue into pull request
* link to Brock's video


##Huboard

##Responsibilities
