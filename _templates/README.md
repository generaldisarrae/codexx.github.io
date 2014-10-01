# Adding to the Devs list

The goal of this page is to help get yourself added to the [Devs list](http://chadev.github.io/devs/).  If anytime the directions are unclear or you need help with something, feel free to reach out on [the #chadev IRC channel on freenode](https://kiwiirc.com/client/irc.freenode.net/?nick=chadev-?#chadev) or via email, by emailing one of the Chadev leads or at chadevhelp@gmail.com and we would be more than happy to help you out.

## Getting on the Devs list

1. Fork the chadev.github.io repo.
  ![GitHub Fork button](http://i.imgur.com/0K2fyDs.png)
2. Clone the fork into your development environment
3. Copy the developer template _\_template/dev.md_ to _\_devs/YourHandle.md_
4. Replace the placeholder values with your details, see below for details about the file structure.
5. Commit and push your changes to your fork.
6. Submit a pull request to [chadev/chadev.github.io](https://github.com/chadev/chadev.github.io).

Once you submit your pull request, someone will review it and let you know if there any changes or fixes that need to be made.  If everything looks good then it will be pulled in and you will start showing up as a Chadev developer!

## The developer markdown file

The list of developers is autogenerated by reading a directory filled with individual markdown files for each dev.  The structure of the files is as follows:

``` md
---
name: <Real Name>
github: <GitHub Username>
gravatar-id: <Gravatar ID>
urls:
    -   name: website
        url: <URL>
    -   name: twitter
        url: <URL>
    -   name: google+
        url: <URL>
layout: default
---
```

Fields that are required are:
* name
* github
* gravatar-id
* layout

### Name

The ```name``` field is for your name as you would like it to appear on the Devs page.

### Github

The ```github``` field is for your GitHub username, this way we can link back to your GitHub profile (you do want people to see how awesome you are after all right? :smile: )

### gravatar-id

The ```gravatar-id``` field contains your gravatar profile ID which is used to fetch your Gravatar ID to display.  [Gravatar](https://en.gravatar.com/) is a free service which allows you to associate a single profile picture with an email address, or multiple addresses if desired,  allowing you to have the same profile picture across multiple sites (GitHub included).  The hash that you use in this field is an unsalted MD5 hash of your email address, don't worry if you don't know you hash that is easy to find.

#### Finding out your Gravatar ID

As said in the previous section your Gravatar ID is the unsalted hash value of your email address.  There are many very easy ways to find out what this is.

##### Using a *nix shell

Using Linux, BSD, or any other Unix like OS, you can get the hash value using a tool like [md5sum](http://linux.die.net/man/1/md5sum).  An example would be ```echo -n 'jsmith@example.com' | md5sum``` which would produce output like the following.

``` sh
$ echo -n 'jsmith@example.com' | md5sum
765d64036cc8ec496f31dd0c242dbeca  -
```

In this case ```765d64036cc8ec496f31dd0c242dbeca``` would be your Gravatar ID.

##### Using a online hash generator

Another way to get your ID would be to use an online tool to generate the hash for you.  There are several out there already and searching for [online md5sum](https://www.google.com/webhp?q=online%20md5sum) will give you plenty to choose from.  Doing this way you may want to ask someone to verify the resulting hash as there is no control over if the site is generating a proper hash or if they are applying a salt to the hash.

##### Ask a fellow Chadev member

You could also always just ask a Chadev member if they would be happy to help you get the correct hash value, we are here to help after all.

### Urls

The ```urls``` field is an optional field that is a list of other sites about you that you would like to promote (personal website/blog, Twitter, Google+, etc).  Each list item is made up of two sub fields: ```name``` and ```url```.  The name field is a keyword field and will determine which, if any, icon that link should get.  Where the url field is the URL for the site or profile page you want to link to.

#### Supported icons

Currently there are a small number of sites that have icons to go with them, only links tagged as "website", "twitter", or "google+" in the ```name``` field get a icon.  If you would like to see more then feel free to open an issue for it or submit a proposed icon in a pull request and we will take it into consideration.

### Layout

The ```layout``` field determines how your profile will look, currently only __default__ is supported.

## Example profile

``` md
---
name: Adam Jimerson
github: vendion
gravatar-id: ba6c5f19da87f22d0e54194b8d54c3e7
urls:
    -   name: website
        url: https://vendion.me
    -   name: google+
        url: https://google.com/+AdamJimerson
layout: default
---
```