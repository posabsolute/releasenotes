# Automatic Release notes plugin & website using GitHub milestones

Lets be real, creating release notes by hand is tedious, this jQuery plugin creates release notes automatically from your github milestones repository.  It comes with a nice onepage layout, but you can also integrate it in any website.


![Screenshot](http://www.position-absolute.com/big_ad.png)

It's a nice middleground where you can show what your team is doing without having to give github access to all your company.

It supports public and private repositories.  

* Since this plugin uses ajax functionalities, to view the demo your code needs to be on a web server.
** The documentation is also available online at : http://posabsolute.github.com/releasenotes/

*** If you use this plugin in production please consider buying me a good pint of beer!!
<form style="text-align:left;" action="https://www.paypal.com/cgi-bin/webscr" method="post">
<input name="cmd" type="hidden" value="_s-xclick">
<input name="encrypted" type="hidden" value="-----BEGIN PKCS7-----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-----END PKCS7-----">
<input style="align:left" alt="PayPal - The safer, easier way to pay online!" name="submit" src="http://www.position-absolute.com/wp-content/themes/default/images/bg_buy.jpg" type="image">
<img src="https://www.paypal.com/en_US/i/scr/pixel.gif" border="0" alt="" width="1" height="1"><br>
</form>


## Options

By default your last 10 milestones will be shown. It uses jsonp for fetching the data from github, this is perfect for public repos.

		$(document).ready(function() {
			$("#releaseNotesContainer").releaseNotes({
				milestonesShown			: 10,
				// If you want to show private repo
				// You need to add repo credentials in api.php
				phpApi				: true,
					phpApiPath		: '/',
				showDescription			: true,
				showComments			: true,
				// Used if phpAPI is false
	     			repo					: 'rails',
	     			username				: 'rails'
			});
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
				phpApi				: true,
					phpApiPath		: '/',
				showDescription			: true,
				showComments			: true,
				// Used if phpAPI is false
	     			repo					: 'rails',
	     			username				: 'rails'
			});
		});
	</script>

In this example releaseNotesContainer is the div id where the plugin will be created.

## Private Repository

To show release notes from a private repo, first you need to set your phpApi option to true, and to set the good phpApiPath path.

Next, open api.php, there is a variable $config at the top where you will need to put your github credentials.

	$configs = array(
	    "username" => "posabsolute",  // Github user
	    "password" => "tamere12",	// Github user password
	    "repo"     => "knoters-app"	// Github Repositoty
	);

Since we use a bridge to get the github data, your credentials will never be exposed to your users.


## Limitations

The plugin works on 
Firefox 3.6+,
Safari,
Chrome,
IE7+


## Licence

Copyright (c) 2012 Cedric Dugas, http://www.position-absolute.com/

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.