# Automatic Release notes plugin & website using GitHub milestones

Lets be real, creating release notes by hand is tedious, this jQuery plugin create release notes automatically from your github milestones repository.  It comes with a nice one page layout, but you can also integrate it in any website.

It's a nice middleground where you can show what your team is doing without having to give github access to all your company.

It support public and private repositories.  

* Since this plugin use ajax funcionalities, to view the demo your code need to be on a web server.
** The documentation is also available online at : http://posabsolute.github.com/releasenotes/


## Options

By default your last 10 milestones will ne shown. It use jsonp for fetching the data from github, this is perfect for  public repos.

			$("#releaseNotesContainer").releaseNotes({
				milestonesShown			: 10,
				// If you want to show private repo
				// You need to add repo credentials in api.php
				phpApi 				: false,
					phpApiPath		: '/',
				showDescription 			: true,
				showComments 			: true,
				// Used if phpAPI is false
	     			repo		            		: 'rails',
	     			username       			: 'rails'
			});

### milestonesShown (int)

The number of milestone the plugin will show.

### phpApi (boolean)

If set to true, the release notes will be fetch in php, perfect for private repos.

### phpApiPath (string) (required only if phpApi is set to true)

Path to the api.php file, without the good path and the phpApi option active the plugin will fail.

### showDescription (boolean)

Show an issue complete description when you click on it.

### showComments (boolean)

When an issue description is shown, if this issue has comments, a Show Comments button will appear enabling the users to see this issue comments.

### repo (string)

Your github repo name, the plugin will fetch data from this repository.

### username (string)

The github username that is attached to your repo.



## Integration in other websites

You want to integrate this plugin in your website, no problem. First you need to add to your document head a couple of js and one css file. This plugin has 2 javascript dependencies, marked.js and jQuery.

Include Depencies & the plugin

	<script src="jquery/1.4.4/jquery.js" type="text/javascript"></script>
	<script src="js/libs/marked.js"></script>
	<script src="js/releasenotes.js"></script>

Next include the plugin stylesheet

	<link rel="stylesheet" href="css/releasenotes.plugin.css">

Finally extenciate and define your options in the document.ready. 

	<script>
		$(document).ready(function() {
			$("#releaseNotesContainer").releaseNotes({
				milestonesShown			: 10,
				// If you want to show private repo
				// You need to add repo credentials in api.php
				phpApi 				: true,
					phpApiPath		: '/',
				showDescription 			: true,
				showComments 			: true,
				// Used if phpAPI is false
	     			repo		            		: 'rails',
	     			username       			: 'rails'
			});
		});
	</script>

In this example releaseNotesContainer is the div id where the plugin will be created.

## Private Repository

To show release notes from a private repo, first you need to set your phpApi option to true, and to set the good phpApiPath path.

Next, open api.php, there is a variable $config at the top where you will need to put your github credential.

	$configs = array(
	    "username" => "posabsolute",  // Github user
	    "password" => "tamere12",	// Github user password
	    "repo"     => "knoters-app"	// Github Repositoty
	);

Since we use a bridge to get the github data, your credential will never be expose to your users.


## Limitation

The plugin works on 
Firefox 3.6+,
Safari,
Chrome,
IE7+


## Copyright

Copyright(c) 2011 [Cedric Dugas](https://github.com/posabsolute) [http://www.position-absolute.com](http://www.position-absolute.com)
