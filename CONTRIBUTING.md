# Guidelines for Contributing

Thanks for checking out our stuffs(?) / organization / repos. Please see below for some general info on how to contribute.

## Access Privileges

All the Open Data Science repos are under the umbrella GitHub organization "Open-Data-Science-at-SIO". The `Teams` interface grants access to the various repos for various groups:
https://github.com/orgs/Open-Data-Science-at-SIO/teams

In general, members of the organization have the ability to create new repositories.
Default permissions:
* **admins** of a repo have full read/write/delete access.
* **members** of the organization have read access to **public** and **private** repos.
* **owners** of the organization have the ability to manage teams.
* **team** members can be given fine-grained access to repos. For example, there is a `website-admin` team with admin access to the website repo (this one).

## Updates

Updates to the website can be handled from within the GitHub interface by editing the raw files or creating new files.

Alternatively, you can clone the repo to get a whole copy for yourself, edit / add files, commit, and push back any changes.

## Content Formatting

Most content is in the form of markdown files. You can find a basic guide [here](https://guides.github.com/features/mastering-markdown/). 

Code in markdown will be colored accordingly. To use code syntax highlighting, use the following syntax:

```
```python
import random

# Roll the die
roll = random.randint(1, 20)
print('You rolled a %d.' % roll)
``` #REMOVE
```

(Remove #REMOVE from the end of the last line). Which will look like this in
the rendered jekyll output using the default css/syntax.css provided with this
theme (which is the **colorful** theme from [https://github.com/iwootten/jekyll-syntax](https://github.com/iwootten/jekyll-syntax)):

```python
import random

# Roll the die
roll = random.randint(1, 20)
print('You rolled a %d.' % roll)
```

## File Layout
```
{repo folder}
|-- {misc top level files}
|-- _config.yml      # configuration file for the website
|-- about.html       # "about" page
|-- archive.html     # template page for archive of posts
|-- events_list.html # template page for list of events
|-- index.html       # main splash page
|-- links.html       # links to external tutorials / readings
|-- mission.html     # mission statement and code of conduct
|-- resources.html   # repo guide
|-- _events          # folder for events
|-- _includes        # folder for misc. html components (e.g. header, footer)
|-- _layouts         # folder for post/event templates
|-- _posts           # folder for news posts
|-- css              # folder for css files
|-- images           # folder for image files
|-- js               # folder for javascript files
```

## Website Content

### Dynamic Content

The website automatically updates on new commits. So in general, nothing needs to be done to keep it up to date, once events and posts are added to the repo. However, the calendar function for upcoming events is not encoded as javascript, so will only "roll over" on a new commit. 

#### Events

Add new markdown files to this folder - easiest is to copy the raw template from a previous event and update the info. Note that the filename is not particularly important (I use it mainly to keep track of past and upcoming events at a quick glance), as the date/time info in the markdown header is used to populate the calendar.

General markdown format is supported.

#### Posts

Add new markdown files to this folder - easiest is to copy the raw template from a previous post and update the info. Again, filename is not important, as the posts are ordered by the date info in the markdown header.

**Post Author Attribution**

To get correct authorship on posts, check that you have an author entry in the `_config.yml` file. This will set up the "username" you use for posts, as well as info for how your name is displayed and email. After that, you just need to use that username in the author field of any posts.

### Static Content

Most of the remaining content on the website is static. Here, the main files to keep track of are the `.html` files in the top-level folder, as they are the primary pages for the website. 

*Note that the links are not fully hard-coded, but are variables that are filled with content later. This is important for them to work even if moved around to a different part of the folder structure.*
