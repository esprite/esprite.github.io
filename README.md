# Jekyll based URL Shortener

### Purpose
This program is designed to provide all the functionality of a URL shortener, while running on a Jekyll based server.  This will allow for a more efficient operation than running on a Rails or Django server.  It will also allow the static HTML files to be placed on an Apache or Nginx server, to allow for even more efficiency.  Finally, it will allow the server to be hosted on a free github based gh-pages site to allow anyone to have a fast, efficient, and free URL shortener.

*Note:  This does not include analytics.  If you want analytics, click the link below.*

### Quick Start
1.  Fork the github repo
2.  Configure the config file
3.  Forward your custom domain to your gh-pages
4.  Add data to your _data/short.csv file

## The Setup

### Fork the github repo
Create an account on github if you haven't already.  Then from the repo click the fork icon in the upper right hand corner.  This will create a copy of the repo in your github account.  Check and make sure that you are on the "gh-pages" branch.  

It may take a few minutes to an hour for everything to get set up, but once it is complete, you should be able to test your URL shortener by going to https:// {github username} .github.io/name-shortener/add/

Before you begin using your URL Shortener, make sure to set up the config file first.

### Setting up the _config.yml file
Now that you have forked the repo, it is time to set up the config file.  Click on the _config.yml file and then click on edit.

For this walkthough, I am going to assume you have a custom domain name that you will be setting up.  In this case, we will be using www.7bl.ink as our custom domain.

The first setting to change will be the root redirect.  In our case, we want www.7bl.ink to redirect to www.7blink.com.  To do that, we set 'root: "http://www.7blink.com"'.  This will forward all traffic to the root of our domain to our main website.  
We haven't linked our custom domain yet, but you can still test this out by going to https:// {github username} .github.io/name-shortener/

which should redirect to the site you set as root.

Next is to set the custom prefix.  Since we want all of our links to begin with our custom domain (www.7bl.ink), we need to tell the URL shortener what the prefix is.  So we are going to set 'url: "http://www.7bl.ink"'

Once you set that up with your custom domain, you can test it by going to https:// {github username} .github.io/name-shortener/add/

and you should see your new custom prefix showing up for the links.

Lastly, it to set up the link to the _data/short.csv file.  The short.csv is the file that holds all of the links for us.  You can easily set add a new link to be shortened by adding it into the short.csv file and giving it a short link.  To make it easy to find this file we can set it in the config file.  Simply find the line with 'add: "https://github.com/7blink/name-shortener/blob/gh-pages/_data/short.csv"' and replace 7blink with your username.  Again, it may take up to an hour to update, but once it does we can test it by going to https:// {github username} .github.io/name-shortener/add/

and clicking on "add new link."  This should open up a new page with our current short.csv file.  We can then click edit to add a new link to shorten.

### Forward your custom domain to the URL Shortener

This one is pretty easy.  Your domain name provider may have an option to forward your custom domain to another URL.  If that is the case, then that would be the easiest option.  Just forward the domain name to https:// {github username} .github.io/name-shortener/ but it may add a slight delay as the user will have to load both the custom domain's dns record as well as the forwarded address' dns record.

If not, you can edit the domain name's A record or CNAME.  Github has detailed instructions at [https://help.github.com/articles/using-a-custom-domain-with-github-pages/](https://help.github.com/articles/using-a-custom-domain-with-github-pages/ "Github Instructions")

It may take up to 24 hours for your custom domain to update.  Please be patient.  Once it is complete, you can check it out at {your custom domain}/add

### Adding Data to the CSV File

To add a new short link, go to {your custom domain}/add and click on "Add A New Link."  This will take you to the CSV file (if it doesn't, then it isn't properly set up in the _config.yml file).  Then click on edit to edit the file.  

There are already 2 links for you to see how to set it up.  To add a new link, type in the short name (such as "AAA") followed by a comma and the long link to forward to (such as www.yahoo.com).  Then click "Commit Changes" as the bottom and the link will be updated.  The page should now be at {your custom domain}/#{short name}.  

You can also close out the window and that should bring you back to {your custom domain}/add which you can refresh to see your new link.  You can then click on "Copy to Clipboard" and then paste it into a text message or wherever.




