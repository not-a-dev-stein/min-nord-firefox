![Screenshot of the theme](https://github.com/not-a-dev-stein/min-nord-firefox/blob/master/chrome/firefox-sweet-theme/minimal-nord2.png)
![Screenshot of the theme](https://github.com/not-a-dev-stein/min-nord-firefox/blob/master/chrome/firefox-sweet-theme/minimal-nord1.png)
## minimalist-nord-firefox
A minimalist startpage for Firefox with the Nord color pallette.

Okay, first things first, this is the first time I do anything other than cloning and dowloading stuff on GitHub, and I have literally zero experience with programming and coding, so please have that in mind.
I really wanted to have my Firefox matching the rest of the GNOME shell I use (https://github.com/EliverLara/Nordic), but I didn't really find anything that fit the style I was looking for, so I tried messing up with EliverLara's Firefox Sweet theme (https://github.com/EliverLara/firefox-sweet-theme) to the best of my abilities, in order to create it. 

About the startpage, I based mine entirely on AnubisZ9's PixelFox (https://github.com/AnubisZ9/PixelFox), but  also with the Nord color scheme, and I did remove the search bar button and the categories' icons for a more simple look and switched the Firefox logo for alternative Developer Version from vinceliuice's VimixBlack GNOME icon pack (https://github.com/vinceliuice/vimix-icon-theme), which I think suited the theme better then the stock Firefox logo.

So what I did first for the CSS theme was to change the color pallette from the sweet theme she used to a Nord one, more specifically the Polar Night one (https://github.com/arcticicestudio/nord). After that I changed the tabbar size from 30px to 25px, to make it as compact as possible without felling way too cramped. After that I changed the Container indicator to make it small enough so it wouldn't conflict with the new tab bar size. Sounds simple, right? Yeah, it took me an entire night to do this, and thanks to her amazing instructions in the files, it didn't take any longer.

The only issue I still have is that I couldn't find for the life of me a way to stop using the sweet color accents around the tabbar text.

Since I had basically no idea of what I was doing, I messed with the original files as little as possible, but decided to make it available here so that maybe someone that knows their stuff can make it actually good.

From here on the rest is taken directly from EliverLara's and AnubisZ9's pages, for the proper instructions:

## Installation of the CSS theme:



### Installation script

```sh

git clone https://github.com/not-a-dev-stein/min-nord-firefox && cd firefox-sweet-theme

./scripts/install.sh

```



#### Script options

- -f `<firefox_folder>` *optional*

        - Set custom Firefox folder path, for example `~/.mozilla/icecat/`.

        - Default: `~/.mozilla/firefox/`



- -p `<profile_folder>` *optional*

        - Set custom profile folder name, for example `e0j6yb0p.default-nightly`

        - Default: `*.default` (standard default profile)



- -g *optional*

        - Auto enable GNOMISH extra features `hide-single-tab.css` & `matching-autocomplete-width.css`





### Manual installation

1. Go to `about:support` in Firefox.



2. Application Basics > Profile Directory > Open Directory.



3. Open directory in a terminal.



4. Create a `chrome` directory if it doesn't exist.



        ```sh

        mkdir -p chrome

        cd chrome

        ```



5. Clone this repo to a subdirectory:



        ```sh

        git clone https://github.com/EliverLara/firefox-sweet-theme.git

        ```



6. Create single-line user CSS files if non-existent or empty (at least one line is needed for `sed`):


        ```sh

        [[ -s userChrome.css ]] || echo >> userChrome.css

        ```



7. Import this theme at the beginning of the CSS files (all `@import`s must come before any existing `@namespace` declarations):



        ```sh

        sed -i '1s/^/@import "firefox-sweet-theme\/userChrome.css";\n/' userChrome.css

        ```



8. Symlink preferences file:



        ```sh

        ln -s chrome/firefox-sweet-theme/configuration/user.js ../user.js

        ```



9. Restart Firefox.



10. Open Firefox customization panel and move the new tab button to headerbar.



11. Enjoy your new Nord Firefox.



## Enabling optional features

Open `chrome/firefox-sweet-theme/userChrome.css` with a text editor and follow instructions to enable extra features. Keep in mind this file might change in future versions and your configuration will be lost. You can copy the @imports you want to enable to a new file named `customChrome.css` directly in your `chrome/firefox-sweet-theme` directory if you want it to survive updates. Remember all @imports must be at the top of the file, before other statements.



Alternatively you can run installation script with `-g` flag to auto install GNOMISH features.



```sh

./scripts/install.sh -g

```



*Those features are not included by default, because can introduce bugs or Firefox functionalities lost.*



- **hide-single-tab.css** *GNOMISH*



        Hide the tab bar when only one tab is open.



        You should move the new tab button somewhere else for this to work, because by default it is on the tab bar too.



- **matching-autocomplete-width.css** *GNOMISH*



        Limit the URL bar's autocompletion popup's width to the URL bar's width.



- **system-icons.css**



        Use system theme icons instead of Adwaita icons included by theme.



- **symbolic-tab-icons.css**



        Make all tab icons look kinda like symbolic icons.






## Installation of the startpage:

Place both chrome and startpage_alt in 
.mozilla/firefox/PROFILE/ to use them. You can get the location of your 
PROFILE dir in about:profiles. Set the startpage for Home in preferences
 and restart.


the chrome dir contains 2 types of files.


userChrome.css and userContent.css for the UI and the default homepage respectively.




userChrome.xml and userChrome.js for setting the New tab page to a custom page.




If you are using FF 69+ you need to enable it first:
about:config > toolkit.legacyUserProfileCustomizations.stylesheets > true


For the startpage:
To enable the newtab startpage functionality open userChrome.js and then
 change  const mypage = 
"file:///home/stein/.mozilla/firefox/im4l8tp9.default-release/chrome/firefox-sweet-theme/startpage_alt/index.html" to the proper path in your PC (Put the path of your index.html in the quotation)



Note:

You can uncomment the commnted lines in /startpage_alt/style.css to get some shadow effects.


### To edit the search engine and the links:

Open the index.html with a text editor and it's pretty easy to find the 'form action="https://www.qwant.com/" method="get"'. and the links to everything under the 'div class="category"'


Thats it. Enjoy.

## Credits:

All the credits for properly creating everything go to these amazing people:

EliverLara (https://github.com/EliverLara) for the original theme.
AnubisZ9 (https://github.com/AnubisZ9) for the original startpage.
vinceliuice (https://github.com/vinceliuice) for the Firefox logo.


