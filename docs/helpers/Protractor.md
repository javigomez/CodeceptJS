# Protractor

[docs/build/Protractor.js:47-261](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L47-L261 "Source code on GitHub")

**Extends SeleniumWebdriver**

Protractor helper is based on [Protractor library](http://www.protractortest.org) and used for testing AngularJS applications.

#### Selenium Installation

1.  Download [Selenium Server](http://docs.seleniumhq.org/download/)
2.  Launch the daemon: `java -jar selenium-server-standalone-2.xx.xxx.jar`

#### PhantomJS Installation

PhantomJS is a headless alternative to Selenium Server that implements [the WebDriver protocol](https://code.google.com/p/selenium/wiki/JsonWireProtocol).
It allows you to run Selenium tests on a server without a GUI installed.

1.  Download [PhantomJS](http://phantomjs.org/download.html)
2.  Run PhantomJS in WebDriver mode: `phantomjs --webdriver=4444`

### Configuration

This helper should be configured in codecept.json

-   `url` - base url of website to be tested
-   `browser` - browser in which perform testing
-   `driver` - which protrator driver to use (local, direct, session, hosted, sauce, browserstack). By default set to 'hosted' which requires selenium server to be started.
-   `seleniumAddress` - Selenium address to connect (default: <http://localhost:4444/wd/hub>)

other options are the same as in [Protractor config](https://github.com/angular/protractor/blob/master/docs/referenceConf.js).

## amInsideAngularApp

[docs/build/Protractor.js:157-170](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L157-L170 "Source code on GitHub")

Enters Angular mode (switched on by default)
Should be used after "amOutsideAngularApp"

## amOutsideAngularApp

[docs/build/Protractor.js:146-151](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L146-L151 "Source code on GitHub")

Switch to non-Angular mode,
start using WebDriver instead of Protractor in this session

## waitForClickable

[docs/build/Protractor.js:193-197](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L193-L197 "Source code on GitHub")

Waits for element to become clickable for number of seconds.

**Parameters**

-   `locator`  
-   `sec`  

## waitForElement

[docs/build/Protractor.js:184-188](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L184-L188 "Source code on GitHub")

Waits for element to be present on page (by default waits for 1sec).
Element can be located by CSS or XPath.

```js
I.waitForElement('.btn.continue');
I.waitForElement('.btn.continue', 5); // wait for 5 secs
```

**Parameters**

-   `element`  located by CSS|XPath|strict locator
-   `time`  seconds to wait, 1 by default
-   `locator`  
-   `sec`  

## waitForText

[docs/build/Protractor.js:230-237](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L230-L237 "Source code on GitHub")

Waits for a text to appear (by default waits for 1sec).
Element can be located by CSS or XPath.
Narrow down search results by providing context.

```js
I.waitForText('Thank you, form has been submitted');
I.waitForText('Thank you, form has been submitted', 5, '#modal');
```

**Parameters**

-   `text`  to wait for
-   `time`  seconds to wait, 1 by default
-   `sec`  
-   `context`  element located by CSS|XPath|strict locator

## waitForVisible

[docs/build/Protractor.js:210-214](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L210-L214 "Source code on GitHub")

Waits for an element to become visible on a page (by default waits for 1sec).
Element can be located by CSS or XPath.

    I.waitForVisible('#popup');

**Parameters**

-   `element`  located by CSS|XPath|strict locator
-   `time`  seconds to wait, 1 by default
-   `locator`  
-   `sec`  

## amOnPage

[docs/build/Protractor.js:452-452](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L452-L452 "Source code on GitHub")

Opens a web page in a browser. Requires relative or absolute url.
If url starts with `/`, opens a web page of a site defined in `url` config parameter.

```js
I.amOnPage('/'); // opens main page of website
I.amOnPage('https://github.com'); // opens github
I.amOnPage('/login'); // opens a login page
```

**Parameters**

-   `url`  url path or global url

## appendField

[docs/build/Protractor.js:469-469](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L469-L469 "Source code on GitHub")

Appends text to a input field or textarea.
Field is located by name, label, CSS or XPath

```js
I.appendField('#myTextField', 'appended');
```

**Parameters**

-   `field`  located by label|name|CSS|XPath|strict locator
-   `value`  text value

## attachFile

[docs/build/Protractor.js:488-488](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L488-L488 "Source code on GitHub")

Attaches a file to element located by label, name, CSS or XPath
Path to file is relative current codecept directory (where codecept.json is located).
File will be uploaded to remove system (if tests are running remotely).

```js
I.attachFile('Avatar', 'data/avatar.jpg');
I.attachFile('form input[name=avatar]', 'data/avatar.jpg');
```

**Parameters**

-   `field`  located by label|name|CSS|XPath|strict locator
-   `file`  local file path relative to codecept.json config file

## checkOption

[docs/build/Protractor.js:509-509](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L509-L509 "Source code on GitHub")

Selects a checkbox or radio button.
Element is located by label or name or CSS or XPath.

The second parameter is a context (CSS or XPath locator) to narrow the search.

```js
I.checkOption('#agree');
I.checkOption('I Agree to Terms and Conditions');
I.checkOption('agree', '//form');
```

**Parameters**

-   `field`  located by label|name|CSS|XPath|strict locator
-   `context`  (optional) element located by CSS|XPath|strict locator

## clearCookie

[docs/build/Protractor.js:526-526](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L526-L526 "Source code on GitHub")

Clears a cookie by name,
if none provided clears all cookies

```js
I.clearCookie();
I.clearCookie('test');
```

**Parameters**

-   `cookieName`  (optional)

## click

[docs/build/Protractor.js:557-557](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L557-L557 "Source code on GitHub")

Perform a click on a link or a button, given by a locator.
If a fuzzy locator is given, the page will be searched for a button, link, or image matching the locator string.
For buttons, the "value" attribute, "name" attribute, and inner text are searched. For links, the link text is searched.
For images, the "alt" attribute and inner text of any parent links are searched.

The second parameter is a context (CSS or XPath locator) to narrow the search.

```js
// simple link
I.click('Logout');
// button of form
I.click('Submit');
// CSS button
I.click('#form input[type=submit]');
// XPath
I.click('//form/*[@type=submit]');
// link in context
I.click('Logout', '#nav');
// using strict locator
I.click({css: 'nav a.login'});
```

**Parameters**

-   `locator`  link or button located by text, or any element located by CSS|XPath|strict locator

## dontSee

[docs/build/Protractor.js:673-673](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L673-L673 "Source code on GitHub")

Opposite to `see`. Checks that a text is not present on a page.
Use context parameter to narrow down the search.

```js
I.dontSee('Login'); // assume we are already logged in
```

**Parameters**

-   `text`  is not present
-   `context`  (optional) element located by CSS|XPath|strict locator in which to perfrom search

## dontSeeCheckboxIsChecked

[docs/build/Protractor.js:569-569](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L569-L569 "Source code on GitHub")

Verifies that the specified checkbox is not checked.

**Parameters**

-   `field`  located by label|name|CSS|XPath|strict locator

## dontSeeCookie

[docs/build/Protractor.js:581-581](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L581-L581 "Source code on GitHub")

Checks that cookie with given name does not exist.

**Parameters**

-   `name`  

## dontSeeCurrentUrlEquals

[docs/build/Protractor.js:594-594](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L594-L594 "Source code on GitHub")

Checks that current url is not equal to provided one.
If a relative url provided, a configured url will be prepended to it.

**Parameters**

-   `url`  

## dontSeeElement

[docs/build/Protractor.js:606-606](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L606-L606 "Source code on GitHub")

Opposite to `seeElement`. Checks that element is not visible

**Parameters**

-   `element`  located by CSS|XPath|Strict locator

## dontSeeInCurrentUrl

[docs/build/Protractor.js:618-618](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L618-L618 "Source code on GitHub")

Checks that current url does not contain a provided fragment.

**Parameters**

-   `url`  

## dontSeeInField

[docs/build/Protractor.js:632-632](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L632-L632 "Source code on GitHub")

Checks that value of input field or textare doesn't equal to given value
Opposite to `seeInField`.

**Parameters**

-   `field`  located by label|name|CSS|XPath|strict locator
-   `value`  is not expected to be a field value

## dontSeeInSource

[docs/build/Protractor.js:644-644](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L644-L644 "Source code on GitHub")

Checks that the current page contains the given string in its raw source code

**Parameters**

-   `string`  

## dontSeeInTitle

[docs/build/Protractor.js:656-656](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L656-L656 "Source code on GitHub")

Checks that title does not contain text.

**Parameters**

-   `text`  

## executeAsyncScript

[docs/build/Protractor.js:686-686](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L686-L686 "Source code on GitHub")

Executes async script on page.
Provided function should execute a passed callback (as first argument) to signal it is finished.

**Parameters**

-   `script`  

## executeScript

[docs/build/Protractor.js:701-701](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L701-L701 "Source code on GitHub")

Executes sync script on a page.
Pass arguments to function as additional parameters.
Will return execution result to a test.
In this case you should use generator and yield to receive results.

**Parameters**

-   `script`  

## fillField

[docs/build/Protractor.js:725-725](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L725-L725 "Source code on GitHub")

Fills a text field or textarea, after clearing its value,  with the given string.
Field is located by name, label, CSS, or XPath.

```js
// by label
I.fillField('Email', 'hello@world.com');
// by name
I.fillField('password', '123456');
// by CSS
I.fillField('form#login input[name=username]', 'John');
// or by strict locator
I.fillField({css: 'form#login input[name=username]'}, 'John');
```

**Parameters**

-   `field`  located by label|name|CSS|XPath|strict locator
-   `value`  

## grabAttributeFrom

[docs/build/Protractor.js:742-742](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L742-L742 "Source code on GitHub")

Retrieves an attribute from an element located by CSS or XPath and returns it to test.
Resumes test execution, so **should be used inside a generator with `yield`** operator.

```js
let hint = yield I.grabAttributeFrom('#tooltip', 'title');
```

**Parameters**

-   `element`  located by CSS|XPath|strict locator
-   `attribute`  

## grabCookie

[docs/build/Protractor.js:759-759](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L759-L759 "Source code on GitHub")

Gets a cookie object by name
Resumes test execution, so **should be used inside a generator with `yield`** operator.

```js
let cookie = I.grabCookie('auth');
assert(cookie.value, '123456');
```

**Parameters**

-   `cookie`  

## grabTextFrom

[docs/build/Protractor.js:775-775](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L775-L775 "Source code on GitHub")

Retrieves a text from an element located by CSS or XPath and returns it to test.
Resumes test execution, so **should be used inside a generator with `yield`** operator.

```js
let pin = yield I.grabTextFrom('#pin');
```

**Parameters**

-   `element`  located by CSS|XPath|strict locator

## grabTitle

[docs/build/Protractor.js:790-790](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L790-L790 "Source code on GitHub")

Retrieves a page title and returns it to test.
Resumes test execution, so **should be used inside a generator with `yield`** operator.

```js
let title = yield I.grabTitle();
```

## grabValueFrom

[docs/build/Protractor.js:806-806](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L806-L806 "Source code on GitHub")

Retrieves a value from a form element located by CSS or XPath and returns it to test.
Resumes test execution, so **should be used inside a generator with `yield`** operator.

```js
let email = yield I.grabValueFrom('input[name=email]');
```

**Parameters**

-   `field`  located by label|name|CSS|XPath|strict locator

## pressKey

[docs/build/Protractor.js:824-824](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L824-L824 "Source code on GitHub")

Presses a key on a focused element.
Speical keys like 'Enter', 'Control', [etc](https://code.google.com/p/selenium/wiki/JsonWireProtocol#/session/:sessionId/element/:id/value)
will be replaced with corresponding unicode.
If modiferier key is used (Control, Command, Alt, Shift) in array, it will be released afterwards.

```js
I.pressKey('Enter');
I.pressKey(['Control','a']);
```

**Parameters**

-   `key`  

## resizeWindow

[docs/build/Protractor.js:838-838](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L838-L838 "Source code on GitHub")

Resize the current window to provided width and height.
First parameter can be set to `maximize`

**Parameters**

-   `height`  

## saveScreenshot

[docs/build/Protractor.js:854-854](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L854-L854 "Source code on GitHub")

Saves a screenshot to ouput folder (set in codecept.json).
Filename is relative to output folder.

```js
I.saveScreenshot('debug.png');
```

**Parameters**

-   `filename`  

## see

[docs/build/Protractor.js:1001-1001](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L1001-L1001 "Source code on GitHub")

Checks that a page contains a visible text.
Use context parameter to narrow down the search.

```js
I.see('Welcome'); // text welcome on a page
I.see('Welcome', '.content'); // text inside .content div
I.see('Register', {css: 'form.register'}); // use strict locator
```

**Parameters**

-   `text`  expected on page
-   `context`  (optional) element located by CSS|Xpath|strict locator in which to search for text

## seeCheckboxIsChecked

[docs/build/Protractor.js:871-871](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L871-L871 "Source code on GitHub")

Verifies that the specified checkbox is checked.

```js
I.seeCheckboxIsChecked('Agree');
I.seeCheckboxIsChecked('#agree'); // I suppose user agreed to terms
I.seeCheckboxIsChecked({css: '#signup_form input[type=checkbox]'});
```

**Parameters**

-   `field`  located by label|name|CSS|XPath|strict locator

## seeCookie

[docs/build/Protractor.js:886-886](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L886-L886 "Source code on GitHub")

Checks that cookie with given name exists.

```js
I.seeCookie('Auth');
```

**Parameters**

-   `name`  

## seeCurrentUrlEquals

[docs/build/Protractor.js:904-904](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L904-L904 "Source code on GitHub")

Checks that current url is equal to provided one.
If a relative url provided, a configured url will be prepended to it.
So both examples will work:

```js
I.seeCurrentUrlEquals('/register');
I.seeCurrentUrlEquals('http://my.site.com/register');
```

**Parameters**

-   `url`  

## seeElement

[docs/build/Protractor.js:920-920](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L920-L920 "Source code on GitHub")

Checks that a given Element is visible
Element is located by CSS or XPath.

```js
I.seeElement('#modal');
```

**Parameters**

-   `located`  by CSS|XPath|strict locator

## seeInCurrentUrl

[docs/build/Protractor.js:935-935](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L935-L935 "Source code on GitHub")

Checks that current url contains a provided fragment.

```js
I.seeInCurrentUrl('/register'); // we are on registration page
```

**Parameters**

-   `url`  

## seeInField

[docs/build/Protractor.js:955-955](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L955-L955 "Source code on GitHub")

Checks that the given input field or textarea equals to given value.
For fuzzy locators, fields are matched by label text, the "name" attribute, CSS, and XPath.

```js
I.seeInField('Username', 'davert');
I.seeInField({css: 'form textarea'},'Type your comment here');
I.seeInField('form input[type=hidden]','hidden_value');
I.seeInField('#searchform input','Search');
```

**Parameters**

-   `field`  located by label|name|CSS|XPath|strict locator
-   `value`  

## seeInSource

[docs/build/Protractor.js:970-970](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L970-L970 "Source code on GitHub")

Checks that the current page contains the given string in its raw source code.

```js
I.seeInSource('<h1>Green eggs &amp; ham</h1>');
```

**Parameters**

-   `html`  

## seeInTitle

[docs/build/Protractor.js:982-982](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L982-L982 "Source code on GitHub")

Checks that title contains text.

**Parameters**

-   `text`  

## selectOption

[docs/build/Protractor.js:1030-1030](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L1030-L1030 "Source code on GitHub")

Selects an option in a drop-down select.
Field is siearched by label | name | CSS | XPath.
Option is selected by visible text or by value.

```js
I.selectOption('Choose Plan', 'Monthly'); // select by label
I.selectOption('subscription', 'Monthly'); // match option by text
I.selectOption('subscription', '0'); // or by value
I.selectOption('//form/select[@name=account]','Permium');
I.selectOption('form select[name=account]', 'Premium');
I.selectOption({css: 'form select[name=account]'}, 'Premium');
```

Provide an array for the second argument to select multiple options.

```js
I.selectOption('Which OS do you use?', ['Andriod', 'OSX']);
```

**Parameters**

-   `field`  located by label|name|CSS|XPath|strict locator
-   `value`  

## setCookie

[docs/build/Protractor.js:1045-1045](https://github.com/Codeception/CodeceptJS/blob/6e124db3371850a45323ea9b87f41ad1ed148371/docs/build/Protractor.js#L1045-L1045 "Source code on GitHub")

Sets a cookie

```js
I.setCookie({name: 'auth', value: true});
```

**Parameters**

-   `cookie`  