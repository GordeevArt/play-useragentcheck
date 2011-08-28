# UserAgentCheck module for the play framework

## What is UserAgentCheck ?

UserAgentCheck provides an easy way to notify users when their browser is outdated. It displays a non disruptive banner at the top of the page and drives the user to a page where he may upgrade his browser.

LOGO


## How does it work ?

It's no rocket science: the module provides a tag than needs to be included in your main template (typically main.html). In a nutshell, the module reads the user-agent header, figures the browser name and version and decides, based on your settings, if the banner should be displayed. To avoid redoing the same process on every request, it then stores the result in the session (which in Play translates to a cookie).

## Usage:

### Configuration

By using properties in `conf/application.conf` the developer has full control over when the banner should display.

    useragentcheck.minInternetExplorerVersion = 7
    useragentcheck.minOperaVersion = 10
    useragentcheck.minFirefoxVersion = 5
    useragentcheck.minChromeVersion = 13
    useragentcheck.minSafariVersion = 5

With the sample lines above, the banner will show if you use IE6 or prior, Opera 9 or prior..etc

### Tag

You should include this tag somewhere in your template. Preferable right at the top of the html body tag.

    …    
    <body>
    #{useragentcheck /}
    #{doLayout /}
    </body>
    ...

### Banner settings

The banner text and url are configured using the standard `conf/messages` file. The following entries are the defaults.

    useragentcheck.label=Your browser is no longer supported. Please click here to update...
    useragentcheck.url=http://www.google.com/chrome


## Sample application

Part of the distribution

## Credits

User Agent Utils - Harald Walker - [http://user-agent-utils.java.net/](http://user-agent-utils.java.net/)

play-useragentcheck module - Olivier Refalo - [https://github.com/orefalo](https://github.com/orefalo)