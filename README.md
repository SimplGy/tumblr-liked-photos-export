tumblr-liked-photos-export
=============

Export the images from your [liked posts](https://www.tumblr.com/likes) in Tumblr.

## How to use it

1. Clone the repo:  

        $ git clone git@github.com:javierarce/tumblr-liked-photos-export.git

2. Install dependencies:

        $ gem install httparty

3. Enable the option "Share posts you like" in the settings page of your blog.
 
4. Register a new app:  

        https://www.tumblr.com/settings/apps

5. Copy the `OAuth Consumer Key` of the app.  
6. Add two keys to your bash/zsh…  

        export TUMBLR_USERNAME="MY_FANTASTIC_TUMBLR_USERNAME"  
        export TUMBLR_API_KEY="MY_DAUNTING_OAUTH_CONSUMER_KEY"  
               
7. … or simply update the `export.rb` file with your credentials:
        
        # Configuration
        username = "MY_COOL_TUMBLR_USERNAME"
        api_key  = "MY_OH_SO_NICE_OAUTH_CONSUMER_KEY"

PS: also don't forget to remove `ENV[ ]` from the variable assignment. 

8. Go to the app directory and run:  

        ruby export.rb

9. Your favorite images from Tumblr will be downloaded to the `image` folder.

You can specify two params (`username` & `name` of the download directory) directly from the command line like this:

         ruby export.rb username download_dir

## Output

This is what it looks like when it runs:

```
$ ruby export.rb your-username
URL
http://api.tumblr.com/v2/blog/your-username.tumblr.com/likes?api_key=ASDF

USERNAME
your-username

DIR
images

Downloading 1234 posts
blog-a
   https://66.media.tumblr.com/8262342342318fcaaae94770923093/tumblr_klmsadflkldsk1_500.jpg
blog-b
	https://66.media.tumblr.com/8262342342318fcaaae94770923093/tumblr_klmsadflkldsk1_500.jpg
	https://66.media.tumblr.com/8262342342318fcaaae94770923093/tumblr_klmsadflkldsk1_500.jpg
blog-c
  https://66.media.tumblr.com/8262342342318fcaaae94770923093/tumblr_klmsadflkldsk1_500.jpg
...
```

## Troubleshoot

If you get the an "Unauthorized" error message, open the URL http://api.tumblr.com/v2/blog/USERNAME.tumblr.com/likes?api_key=API_KEY in your browser (replacing USERNAME and API_KEY with your own values). You should see a list of posts.

If you get the error `cannot load such file -- httparty`, use `gem` to install dependencies.

## Contributors

[Javier Arce](https://github.com/javierarce)  
[Sergi Meseguer](https://github.com/zigotica)

## More

Hey there, digital Diogenes, do you need to export more? Then check out the [tumblr-full-backup](https://github.com/zigotica/tumblr-full-backup) repo by [zigotica](https://github.com/zigotica).
