# Setting up a New Site

## Objectives

1. Set up initial GitHub repository for upcoming labs
2. Review branching, committing and pushing to GitHub

## Introduction

In the upcoming labs, we will be working through the creation of a full website, introducing various HTML concepts and components while applying them to our site. As each lesson builds off of the work completed in the last, in this lesson, we will be going through the process of setting up your own GitHub repository to code along in. In addition to this, in the event that you get stuck or your personal repository isn't working as intended, each lesson will contain some basic code that you can use to code along with.

**NOTE**: Videos are provided in these lessons, but contain some instructions and steps that have changed, especially if you are using the in-browser Learn IDE. For this reason, the Readme content of these lessons will differ slightly from video instructions, and will include up-to-date steps for navigating the Learn IDE and completing these lessons entirely within your browser Learn environment. You do not need specific applications such as Sublime or iTerm.

While using the in-browser Learn IDE, if you leave the page or refresh, _any work done will be lost unless it is pushed up to a remote repository_, which we will be discussing in this lesson. Make sure, though, to **always open a new browser tab or window when navigating to a different page on the internet**.

## Instructions

If you run into any issues while following along, or are unable to set up your own repository, remember that you will still be able to use the files provided in each of the following lessons to code along.

### Setting Up Your GitHub Repository

Let's start by creating some initial folders and files before creating a remote git repository online.

* We will be creating a website for a fake real estate company called 'Exceptional Realty.' Before anything else, we need a place to do our work in. In your Learn terminal, create a project folder by typing `mkdir exceptional-realty`. Then, to navigate into that folder, type `cd exceptional-realty`.
* We'll be connecting this folder to a remote GitHub repository, so we'll need to create some basic files first. From inside your project folder, type `touch README.md` to create an empty README file. The file should appear in the folder tree beside the text-editor in the Learn IDE, within the `exceptional-realty` folder.
* We can add some content to this file by clicking the file to open it. Let's add a title, 'Exceptional Realty Group website' and on a new line, we'll add a description: 'This is an example site for the Intro to Front-End Web Development course at the Flatiron School'.
* We should also create a `.gitignore` file, which is _essential_ in preventing private and/or sensitive files from being shared publicly when your repository is published online. First, type `touch .gitignore` to create the file. For now, we can use a list of common `.gitignore` configurations to populate this file, provided via GitHub. Navigate to <a href="https://gist.github.com/octocat/9257657" target="_blank">https://gist.github.com/octocat/9257657</a>, copy the contents of the `.gitignore` file provided there, and paste them into your newly created file.

Now that we've got some files in our project, let's initialize a new git repository locally, then create a remote repo and connect them.

* To initialize a new git repository locally, in our `exceptional-realty`
  folder, type `git init`. You should see a line in your terminal that displays where your git file has been created:

  ```
  Initialized empty Git repository in /home/.../.git/
  ```

* We now have a local git repository. If you type `git status` in your terminal, you should see the
  files we just created listed as 'Untracked files'. Since these files are untracked, any changes made
  to them won't be recognized by our git repository.
* To track the files we've created and changed, type `git add .`. Then, we want to record, a.k.a 'commit', these changes to our git repo by typing `git commit -m 'first commit'`. The `-m` is short for `--message=`, which we'll use to state what we're doing during this particular commit.
* If you type `git status` now, you'll see that our files are no longer listed, and that there is 'nothing to commit, the working directory is clean', meaning there are no new changes since the last commit.

We've got our local work ready to go, so now we need to set up a new remote repository to store this in.

* Open a new browser tab and go to <a href="github.com" target="_blank">github.com</a> and make sure you are signed in.
* In the upper right-hand corner of the page, click the **`+`** button and choose **_New repository_**
* You'll be brought to the _'Create a new repository'_ page. We can go ahead and name this repository the same name we gave our folder, so in the _'Repository name'_ field, enter 'exceptional-realty'. Then, let's add a brief description of what this repository is for in the _'Description'_ field.
* We can leave this repository set to _Public_. We also already have a README.md file, so we do not need to initialize this repository with one. Click _'Create repository'_ to continue.
* GitHub provides commands in the _'Quick setup'_ page for starting from scratch, pushing an existing local repository, or importing code from another repository. In our case, we need the commands for pushing an existing repository. The url provided will be unique to your GitHub username and repo, so copy the first command:

`git remote add origin https://github.com/<your_username_here>/exceptional-realty.git...`

* Back in the Learn terminal, paste in the copied command and press `enter`. If you have any trouble, make sure you've set up an GitHub account SSH key to your local computer. Checkout this link for more info on setting up your SSH: <a href="https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/" target="_blank">Adding a New SSH Key to Your GitHub Account</a>.
* To push up your local work to this new remote repository, we'll use the second command GitHub provides:

```
git push -u origin master
```

* This tells our git repository to push up to our remote repository, `origin`, using our local repository's `master` branch. The `-u` is necessary for the first time we do this, as it also tells git to set up tracking between our local and remote `master` branches. You may need to enter your GitHub credentials in the terminal to complete this step. If successful, your terminal will display that it is counting and writing objects to your remote repository, and that `Branch master set up to track remote branch master from origin.`
* Head back github.com and refresh the _'Quick setup'_ page. Your pushed up files should appear.
* At any point going forward, if you accidentally navigate away from these learn lessons or refresh the page, you can always re-clone a copy of your remote repo by entering the following into your terminal:

`git clone https://github.com/<your_username_here>/exceptional-realty`

This will download a copy to your Learn IDE based on whatever you last committed and pushed up to GitHub. Always remember to push up any work you want to keep and access again!

### Adding Branches

* From inside your repository folder in the Learn IDE, type `git branch`. This command will show you all the existing branches that are stored locally on your computer, and currently, we only have one, `master`. As a general best practice, the `master` branch should always be kept in a fully functional state; any new features or additions made on a repo should be done on a separate branch, allowing one or more developers to work on isolated parts of a project without interfering with the `master` version until the branch code is fully ready.
* We're going to create a new branch and add some files to this repository. To do this, type

```
git checkout -b main-pages
```

Your terminal should now display that you are on a new branch, `(main-pages)`, instead of `(master)`.

* Let's create some additional web pages for out website. You can do this by choosing to click the `Create New` button in your Learn IDE and choosing `File`, or by using your terminal and the command `touch`, followed by the name of the file. Go ahead and create our first file, `index.html`, all lowercase, which will be our homepage on the website. Now let's create the rest of our web pages:

```
touch contact.html
touch market-report.html
touch new-properties.html
touch real-estate-listings.html
```

* Naming these files based on what they will contain will keep us better organized, and can also help when it comes to Search Engine Optimization, as search engine bots use file names find relevant search information.

* We also will need a separate folder for storing some image files. Create a directory using `mkdir` or your `Create New` button, and name it `images`.

* Let's go ahead and add an image to this folder. You may be used to downloading images off the internet by simply navigating to that image, right clicking, and saving the file. We're going to employ a special terminal command that will work regardless of your environment setup.
* Either run the `learn open` command or [manually open the lab](http://help.learn.co/workflow-tips/github/how-to-manually-open-a-lab).
* Code along with the provided video below and/or its supplementary reading located below the video. Code everything you see there. Feel free to stop, pause, rewind or fast forward through the content to keep pace.

<iframe width="640" height="480" src="//www.youtube.com/embed/lYHcdsF0Iug?rel=0&modestbranding=1" frameborder="0" allowfullscreen></iframe>

**NOTE**: The Google Maps interface has changed slightly since this video was recorded. We'll re-record the video ASAP, but we're sure you can find your way around (the changes are minimal and intuitive).

### Map Embed

Start by creating a new feature branch in Terminal by typing `git checkout -b contact-page`.

Then open the contact.html page in your code editor. Under the `<h3>Contact</h3>` write some comments for the content we will add like so,

```html
<h3>Contact</h3>

<!-- Map -->

<!-- Contact Form -->
```

Next, in your browser head to [https://www.google.com/maps](https://www.google.com/maps) and search for a general location. I searched for `Brooklyn Heights, Brooklyn, NY`.

Now click the menu icon located at the top left of the screen and select **Share or embed map**. Then click the **Embed map** tab.

Next to the link with the iframe code click the drop menu to select the size of the iframe and choose **Custom size**. Then set the width to `425` pixels wide and set the height to `350` pixels tall. Then highlight the iframe embed code and copy it to your clipboard using Command + c (Mac) or Ctrl + c (Windows) and the head back to your code editor and paste the code snippet Command + v (Mac) or Ctrl + v (Windows) under the comment `<!--map-->` like so,

```html
<!-- Map -->
<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d6049.881319200985!2d-74.00151372674895!3d40.69730452928296!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89c25a47df06b185%3A0xc889234bc07c42ee!2sBrooklyn+Heights%2C+Brooklyn%2C+NY+11201!5e0!3m2!1sen!2sus!4v1461598289488" width="425" height="350" frameborder="0" style="border:0" allowfullscreen></iframe>
```

This long code snippet uses the `<iframe>` element that allows us to load another HTML page inside of a frame within our HTML page. It is like looking through a window from our page into another page displaying a Google Map.

Next go ahead and save this page and preview it in the browser. The map should look something like this:

<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d6049.881319200985!2d-74.00151372674895!3d40.69730452928296!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89c25a47df06b185%3A0xc889234bc07c42ee!2sBrooklyn+Heights%2C+Brooklyn%2C+NY+11201!5e0!3m2!1sen!2sus!4v1461598289488" width="425" height="350" frameborder="0" style="border:0" allowfullscreen></iframe>

Looks good! Let's stage and commit our code. In Terminal type `git add contact.html` and press return. Then type `git commit -m "add google map to contact page"` and press return. Then we will push up our feature branch as a backup for safe keeping, type `git push -u origin contact-page` and press return.

### Form

Next let's add a contact form. Under our `<!-- Contact Form -->` comment let's start by creating a `<form>` element. This will wrap all of our form inputs.

```html
<!-- Contact Form -->
<form>...</form>
```

We need to give our opening form element two attributes. The first is an action which is the location that our form will submit its input information to. In our case we will be submitting to a PHP script that will send an email later on. For now, we will insert a `#` pound sign as a placeholder. Second, we will include the method attribute. This tells the browser the type of request we are making to the location we are submitting in the action. Here we will set the value as `post`.

```html
<!-- Contact Form -->
<form action="#" method="post">
  ...
</form>
```

Next, we would like to create inputs for the user to insert their name, email, phone, and a message. We will start by adding a label and input for fullname like so,

```html
<!-- Contact Form -->
<form action="#" method="post">
  <label for="fullname">Name</label>
  <input type="text" id="fullname" name="fullname" placeholder="your name" required>
</form>
```

On line 3 we use a `<label>` element to create a text label associated with the form input. By using the `for` attribute set on the label to match the value of the `id` attribute in the input this ties the label to the input so that if a user clicks on the text of the label "Name" it will select the input next to it. You can test this on the example below:

<label for="fullname">Name</label> <input type="text" id="fullname" name="fullname" placeholder="your name" style="border:1px solid black;padding:5px;">

The required attribute on line 4 helps us alert the user when they try to submit the form without filling out their name.

Let's fill in the rest of our inputs.

```html
<!-- Contact Form -->
<form action="#" method="post">
  <label for="fullname">Name</label>
  <input type="text" id="fullname" name="fullname" placeholder="your name" required>
  <label for="email">Email</label>
  <input type="email" id="email" name="email" placeholder="your email" required>
  <label for="phone">Phone</label>
  <input type="tel" id="phone" name="phone" placeholder="your phone (optional)">
  <label for="message">Message</label>
  <textarea id="message" name="message" rows="10"></textarea>
  <input type="submit" value="send">
</form>
```

The `type` attribute (e.g., "text" vs "email") will be recognized by the browser so that when type email is required, the form will validate that the input matches the format of an email address, including the "@". This is a feature brought to us as part of HTML version 5. Additonally, the type "tel" will bring up the numeric pad on mobile devices, whereas the type "text" will bring up the alphabet keypad. Support varies from device to device, though.

Again, the `for` attribute value when matching an `id` attribute value will link them so that clicking on a label will select the cursor into its related input.

As discussed in the previous lesson, the `name` attribute is important as it stores the users input under that name (variable). This comes in handy for making use of the users input server-side.

The `placeholder` value will appear inside the form input until the user starts typing in their own content.

The `required` attribute will prevent the browser from submitting the form until all required fields are filled in properly. Again this is functionality is baked into HTML5 for us automatically.

The last input on line 11 has a type of "submit" this gives us a submit button to submit the form. The value attribute in this case displays the text that will appear on our submit button.

Next, save the file and refresh the page in the browser to see your form appear. The following code should create a form that displays like the following example below,

<form>
    <label for="fullname">Name</label>
    <input type="text" id="fullname" name="fullname" placeholder="your name" required style="border:1px solid black; display:block; padding:5px;">
    <label for="email">Email</label>
    <input type="email" id="email" name="email" placeholder="your email" required style="border:1px solid black; display:block; padding:5px;">
    <label for="phone">Phone</label>
    <input type="tel" id="phon" name="phone" placeholder="your phone (optional)" style="border:1px solid black; display:block; padding:5px;">
    <label for="message">Message</label>
    <textarea id="message" name="message" rows="10"></textarea>
    <input type="submit" value="send" style="border:1px solid black; display:block; padding:5px;" disabled onClick="function(){ alert('Submit has been disabled to prevent interference with Learn!') }">
</form>

Ok, looks good! Now stage and commit your code. In Terminal type `git add contact.html` and press return, then type `git commit -m "add contact form to contact page"` and press return. Then type `git push origin contact-page`.

Since we are satisfied with our work on our contact page and we feel this feature is publishable we can include the work in our master branch. To do so in Terminal type `git checkout master` and press return to switch to your master branch then type `git merge contact-page` and press return to merge in your commits from the contact-page branch. Then to update our remote type `git push origin master` and press return.

After you're finished, submit a pull request on Github by typing "learn submit" in the terminal and move on to the next lesson!

<p class='util--hide'>View <a href='https://learn.co/lessons/html-map-contact-form-code-along'>HTML Map Contact Form Code-along</a> on Learn.co and start learning to code for free.</p>
**Note: If you are using the Learn IDE, you do not need iTerm or Sublime. Please run all commands and perform all actions in the IDE terminal and text editor. To add images, right click on the directory you'd like to add them to (in the tree) and select 'Import'.**

<iframe width="640" height="480" src="//www.youtube.com/embed/i61lTJ6OpDE?rel=0&modestbranding=1" frameborder="0" allowfullscreen></iframe>

[Alternate video link.](https://www.youtube.com/watch?v=i61lTJ6OpDE)

[Click here to save the intro pic used in this code along.](http://ironboard-curriculum-content.s3.amazonaws.com/front-end/lab-assets/intro-pic.jpg)

[Here is a direct link to the gitignore code referenced in the video.](https://gist.githubusercontent.com/octocat/9257657/raw/3f9569e65df83a7b328b39a091f0ce9c6efc6429/.gitignore)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/setting-up-a-new-site' title='Setting up a New Site'>Setting up a New Site</a> on Learn.co and start learning to code for free.</p>
