# Help us translate Tortuba in your language

Tortuba is logbook to identify and record marine life encounters, available on [iOS](https://tortuba.com/ios), [Android](https://tortuba.com/android) and the [web](https://tortuba.com/).

We want to help everyone spread the word that ocean creatures are cool and deserve to be protected, and we build tools just for that.

It's a bootstraped company (ie we didn't build it to pay dividends), and we always welcome your help to spread the word and improve the apps.

## What can I do to help?

For starters, only the iOS and Android apps texts are open for translation, Web will come later on.

It depends how much time you have, but there are 3 things you can do:
* report typos/grammar errors
* correct typos/errors
* translate in a new language


## How can I help?

### Reporting typos / Improving existing texts

If you don't have/care to create a Github account, just contact us via the messaging tool in the apps (you can find it in the about section).

If you do have an account:
* open a [New issue](https://github.com/tortuba/voice/issues/new)
* write a title, ex: "English - Typo"
* explain below what should be changed:
  * write the exact string that requires a correction (so that we can find it)
  * write your proposed modification
* someone will take care of the rest

### Correcting typos / Modifying existing texts

* Read "Structure of the file" below
* Go to the [strings file](https://github.com/tortuba/voice/blob/master/strings.txt)
* Click on the edit (pencil) button in the top right corner of the file content
* Find and fix the relevant piece(s) of text
* When you're done:
  * head to the bottom of the page, find the "Propose file change" box
  * write a (short) title (eg: "Fix en typo: plaese/please")
  * (optional) add a more detailed explanation below
  * click on "Propose file change"
* We'll review your changes asap, and ship it with the next update

### Translating in a new language

**Get ready**
* Ask to join the team via the Tortuba app messaging system (in the about section) or by creating a [New issue](https://github.com/tortuba/voice/issues/new)
* We'll create a specific branch for the language you want to work on and a specific issue to track any discussion relevante to it
* Read "Structure of the file" below

**Whenever you have time to add some translations**
* Select the proper branch
  * on the [main page](https://github.com/tortuba/voice), there is a dropdown button that reads "Branch: something"
  * change it so that it reads "Branch: language"
* Go to the [strings file](https://github.com/tortuba/voice/blob/master/strings.txt)
* Click on the edit (pencil) button in the top right corner of the file content
* For each keys (in single brackets)
  * add a new ligne with the proper language code and translation
* If you have a doubt about a translation, post your question in the dedicated issue we created (see above)
* When you call it a day:
  * head to the bottom of the page, find the "Commit changes" box
  * write a (short) title (eg: "es: Date section")
  * (optional) add a more detailed explanation below
  * click on "Commit changes"

**When you have translated everything**
* Ping us in the dedicated issue
* We'll review your changes and build a test version for you to play withg
* If everything looks fine, we'll ship it with the next update

## Structure of the file

Important: alignment matters. Make sure you add the proper spaces/tabs

Here's an extract of the file along with explanations

    [[Models - Dive]]
      [dive.number]
        tags = ios,android
        en = Number
        fr = Numéro


And how to read that gibberish.

There are lines that you should not modify:
* [[Models - Dive]]: double brackets are used for sections, it's just used to regroup/organize translations
* [dive.number]: single brackets define the unique key used by the app to know which translation to load, depending on the language of the user
* tags: it indicates on which app the key is used
  * ios: for the iOS app
  * android: for the Android app
  * sb: used in iOS storyboard

That leaves us with the lines you can modify, they all look the same:

    xx = YYYYYYYY

Where xx is the [ISO 639-1 language code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes):
  * en: English
  * fr: French
  * de: German
  * es: Spanish
  * etc…

And YYYYYYYY is the text for the given language

There are some special characters you might see, use for dynamic texts (ie when part of the text is calculated by the app)
  * %@: to insert a string (eg: "More infos about %@")
  * %i: to insert a number (eg: "%i species found")
  * dates follow a [specific pattern](http://www.unicode.org/reports/tr35/tr35-31/tr35-dates.html#Date_Format_Patterns) (eg: HH:mm, MM/dd/YYYY)
