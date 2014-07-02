# Headerbar for Firefox

Here is complete tutorial of Firefox GNOME integration

1. Install all software from this list(don't restart after installing each one):
 * [GNOME 3 theme for Firefox](https://addons.mozilla.org/firefox/addon/adwaita/)
 * [GNOME 3 Theme Tweak extension](https://addons.mozilla.org/firefox/addon/gnome-theme-tweak/)
 * [Hide Tab Bar With One Tab](https://addons.mozilla.org/en-US/firefox/addon/hide-tab-bar-with-one-tab/)
 * [HTitle](https://addons.mozilla.org/firefox/addon/htitle/) - for hiding titlebar
 * [GNotifier](https://addons.mozilla.org/firefox/addon/gnotifier/) - for native notifications
 * [Stylish](https://addons.mozilla.org/firefox/addon/stylish/) - for applying userstyle below
 * [Simple bookmarks menu](https://addons.mozilla.org/firefox/addon/simple-bookmarks-menu/)(optionally) - for hiding unnecessary items in the bookmarks menu
 * [DarkWDec](https://addons.mozilla.org/firefox/addon/darkwdec/)(optionally) - for dark theme

2. Restart your browser, go to <code>about:addons</code>, find GNOME Theme Tweak options and enable options you like, find HTitle options and select hide titlebar "Always" option

![Screenshot of Theme Tweak options](Theme Tweak.png)

3. Go to "User Styles" section of <code>about:addons</code>, select "Write New Style" button, pick a name and paste userstyle below, then click "Save" button.
```css
@namespace url("http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul");

@-moz-document url("chrome://browser/content/browser.xul") {

    :-moz-any(
        #main-window[htitlemode="always"],
        #main-window:not([sizemode="normal"])[htitlemode="auto"],
        #main-window:not([sizemode="normal"])[htitlemode="legacy"]
    ) #toolbar-menubar:not(:-moz-lwtheme) {
        -moz-appearance: none;
    }

    #main-window:not([customize-entered]):not([sizemode="normal"]) #navigator-toolbox:not(:-moz-lwtheme),
    #main-window:not([customize-entered])[sizemode="normal"][htitlemode="always"] #navigator-toolbox:not(:-moz-lwtheme) {
        background-image: linear-gradient(to bottom, #ffffff, #ededed 37px);
    }

    #main-window[darkwdec="true"]:not([customize-entered]):not([sizemode="normal"]) #navigator-toolbox:not(:-moz-lwtheme),
    #main-window[darkwdec="true"]:not([customize-entered])[sizemode="normal"][htitlemode="always"] #navigator-toolbox:not(:-moz-lwtheme){
        background-image: linear-gradient(to bottom, #4e5a5a, #363b3b 37px);
    }

    #main-window:not([customize-entered]):not([sizemode="normal"]) #navigator-toolbox:not(:-moz-lwtheme) #nav-bar,
    #main-window:not([customize-entered])[sizemode="normal"][htitlemode="always"] #navigator-toolbox:not(:-moz-lwtheme) #nav-bar {
        padding: 3px 3px 6px 3px !important;
    }

    #main-window:not([customize-entered]):not([sizemode="normal"]) #navigator-toolbox:not(:-moz-lwtheme) #urlbar,
    #main-window:not([customize-entered])[sizemode="normal"][htitlemode="always"] #navigator-toolbox:not(:-moz-lwtheme) #urlbar {
        margin: 0 36px !important;
    }
}
```

4. Press "Download ZIP" on the right of this page, copy "Headerbar" and "Headerbar-new" theme folders from downloaded archive into <code>~/.local/share/themes/</code> - if this folder does not exist - create it

5. Switch window theme to "Headerbar"(GNOME 3.x-alike) or "Headerbar-new"(GNOME 3.1x-alike) using GNOME Tweak Tool
