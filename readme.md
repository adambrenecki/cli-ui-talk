This is a lightning talk I gave at Linux.conf.au 2018; a couple of people have asked me for the slides, so I'm putting them up here until I get around to finding a good way to put Keynote slides on the perpetual work in progress that is [my website](https://adam.brenecki.id.au).

I've recently discovered that this sort of thing is something I'm really passionate about, so watch out for a full-length, better-researched, hopefully-slightly-less-fast-paced version of this talk coming to a CfP near you :)

---

<img src="slide001.png" width=400 />

Command line interfaces are user interfaces too. Normally when we’re building a user interface, we put a lot of thought into how easy it is to use; if we’re lucky, we even have people or teams whose whole job it is to do that. How do we take that and apply it to command line tools?

<img src="slide002.png" width=400 />

Give things sensible names. It’s okay to give your tool itself a clever or silly name; if you’re writing Python it’s actually required by law.

Things that are within your tool should have names that make their meaning obvious. That doesn’t mean that choosing the name is obvious. Trying to name things well can take hours.

<img src="slide003.png" width=400 />

Use consistent names. These three names all refer to the same thing in Git. Don’t be like Git.

<img src="slide004.png" width=400 />

Be consistent.

<img src="slide005.png" width=400 />

Be consistent between different parts of your own CLI.

<img src="slide006.png" width=400 />

TaskWarrior has tags, it has dynamic tags, and it has different places where tags are used. In every case, tags are denoted with a plus at the front. Be like TaskWarrior.

<img src="slide007.png" width=400 />

Different git subcommands have different ways to delete things. Don’t be like Git.

<img src="slide008.png" width=400 />

Here’s why. This will try to create a branch named ‘rm’. I do this all the time.

<img src="slide009.png" width=400 />

Be consistent with the ecosystem you’re in.

<img src="slide010.png" width=400 />

If you use the built-in argument parsing library in Go, it expects a single dash before every flag, rather than a double dash. That means everyone using your tool has to remember “oh, this is a weird Go thing, I need to use it differently to what I’m used to”. Use a library that lets you do what your users expect.

<img src="slide011.png" width=400 />

Don’t go overboard on consistency. Sometimes doing things a little differently actually makes sense for your users, if you’ve thought about it and you have a good reason for it.

<img src="slide012.png" width=400 />

This is a switch statement in Bash. What’s going on here? Why are there unbalanced parens? What the hell is an esac?

<img src="slide013.png" width=400 />

This is a switch statement in the Fish shell. It’s much easier to understand. It’s also not POSIX compatible, but that’s okay. You don’t need to be all things to all people, especially if you’re sacrificing usability for it.

<img src="slide014.png" width=400 />

Have good defaults. you might not think of defaults as being part of your user interface, but they are.

<img src="slide015.png" width=400 />

Docker has sane defaults, so people don’t shoot themselves in the foot.

Because of Docker’s defaults, I don’t even need to understand namespaces or capabilities or all the things Jess talked about this morning to start using it, even though I can learn about them and adjust the dials later. This is why Docker is popular.

Be like Docker.

<img src="slide016.png" width=400 />

Firewalld in fedora ships with every incoming port over 1024 open by default. Users expect their firewall to block things by default, and this is the exact opposite. Don’t be like firewalld.

<img src="slide017.png" width=400 />

On a similar vein, configuration files are also part of your UI.

<img src="slide018.png" width=400 />

Use a common format that’s clear and widely understood, so that your users only have to think about the actual configuration they’re doing, rather than your crazy custom syntax too.

<img src="slide019.png" width=400 />

Don’t ship a default configuration file with a million things in it; that just makes it hard for your users to keep track of what they’ve changed. When your default config is an empty file, your users can also roll back to default by just deleting everything. Your sane defaults should kick in for a particular option if it’s missing.

<img src="slide020.png" width=400 />

Document everything. Command line options, config files, interactive-mode behaviour. Use lots of examples. Writing good docs is an art in an of itself. If you do nothing else, do this.

<img src="slide021.png" width=400 />

Why should we care about CLI user interfaces anyway? These things are for developers and operators! They’re Computer People! They can just figure it out!

<img src="slide022.png" width=400 />

No.

<img src="slide023.png" width=400 />

We do not have infinite memory. The less I have to understand and remember about your tool in order to use it, the better.

<img src="slide024.png" width=400 />

We did not emerge from our mothers’ wombs with an intricate understanding of Git’s underlying data model. The easier your tool is to use, the less time it takes to learn, the more time your users can spend on important things.

<img src="slide025.png" width=400 />

That’s all. I’m on Twitter, you can shout at me there about why I’m wrong.
