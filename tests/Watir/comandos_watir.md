http://watir.com/guides/wysiwyg/

##Installing Ruby
   
Introduction
In order to run Ruby code you need to install a Ruby interpreter.

Installing a Ruby interpreter for Windows is straightforward, but for Mac and Linux it is slightly more complicated. The default Ruby interpreters normally supplied on Mac and Linux are not adequate for running Watir and related Ruby technologies without making significant alterations to them.

There are different options for properly maintaining a Ruby interpreter, but we have chosen rbenv as the most suitable Ruby interpreter for Mac and chruby for Linux.

Note that RVM is an acceptable (if more complicated) way to maintain a Ruby interpreter if you prefer to use it, but if you choose to use rbenv or chruby, be sure to uninstall RVM completely.

Windows
Download and install the latest version from rubyinstaller
Mac
Hold down the Command key and press the spacebar to open Spotlight search Type Terminal and hit enter

Install XCode command-line tools

Copy and paste this into the terminal and hit enter:

xcode-select --install
Install HomeBrew

Copy and paste this into the terminal and hit enter:

/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
Install rbenv

Copy and paste this into the terminal:

brew install rbenv
rbenv init
touch ~/.bash_profile
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
source ~/.bash_profile
Copy and paste this into the terminal:

rbenv install 2.5.1
rbenv local 2.5.1
Linux
Install git Copy and paste this into the terminal:

sudo apt-get install git
Install ruby-install Copy and paste this into the terminal:

wget -O ruby-install-0.6.0.tar.gz https://github.com/postmodern/ruby-install/archive/v0.6.0.tar.gz
tar -xzvf ruby-install-0.6.0.tar.gz
cd ruby-install-0.6.0/
sudo make install
ruby-install ruby 2.5.1
Install chruby Copy and paste this into the terminal:

cd ../
wget -O chruby-0.3.9.tar.gz https://github.com/postmodern/chruby/archive/v0.3.9.tar.gz
tar -xzvf chruby-0.3.9.tar.gz
cd chruby-0.3.9/
sudo make install
sudo ./scripts/setup.sh
xed ~/.bash_profile
Copy and paste this into the bash_profile file that opened in TextEdit:

source /usr/local/share/chruby/chruby.sh
source /usr/local/share/chruby/auto.sh
Save file and Close TextEdit

Copy and paste this into the terminal and hit enter:

source ~/.bash_profile
chruby 2.5.1
--------------------------------------------------------------------------------

##Installing Watir
   
Once you have installed Ruby, installing and using Watir is easy.

From the command line, install the gem, which Ruby’s way of packaging code:

gem install watir
Now you can try it out by opening up an Interactive Ruby (irb) session.

If you’re using Mac OS X open up Terminal and type irb, then hit enter.
If you’re using Linux, open up a shell and type irb and hit enter.
If you’re using Windows, open Interactive Ruby.
Now you only need to require the gem to start using it.

--------------------------------------------------------------------------------
##Automation Pipeline
   
Watir is a user focused way to test your websites. It mostly uses Selenium for browser automation, but it provides many more high level features that make it easy to write stable, maintainable tests.

The typical flow of information looks like this:

Test Runner –> 
      Test code –> 
           PageObject code –> 
                Watir library–> 
                     Selenium library –> 
                          Selenium Server(s) (optional) –> 
                               Browser Driver –> 
                                    Browser

Test Runner. In Ruby this can be MiniTest, RSpec or Cucumber. Most Watir users use RSpec by default, but Cucumber is popular for teams that are working in a Behavior Driven Development environment.

Test Code. Whether Cucumber Steps or RSpec “it” blocks, the code here should be focused on succinctly representing the business requirement for the test. This is the higher level “what” code that references other objects (like page objects) for the actual implementation. Ruby is more readable than most languages, so name page objects and methods well and a quick skim will allow to the purpose of the test to be easily understood.

Page Object. This is where the implementation (“how”) code belongs. Page objects can represent an entire page, a modal, or a subset of a page (like a sidebar or a footer). Page objects are typically comprised of two things, the elements with their applicable locators, and the methods that represent the actions that a user can take on the page. Most of this code will be references to Watir objects.

Watir Code. Watir is designed for “Test Automation.” It takes the code in a page object and translates it into the series of applicable Selenium and JavaScript calls to accomplish the desired functionality. Watir attempts to understand the intention of the code in a test suite and tries to follow a “Do What I Mean” philosophy to accomplish it. Continue reading through the documentation to see how Watir makes writing tests fun and easy.

Selenium Code. Selenium is designed for “Browser Automation.” It takes the higher focuses on the specific low level actions that can be taken on a browser. It implements a small number of locators and takes a “Do What I Say” approach. It translates idiomatic Ruby code into serialized json blobs to send along for further processing.

Selenium Server. This isn’t necessary when driving browsers on the same computer as the code. To drive browsers on a remote computer, though, the commands need to be sent to one or more intermediary servers. The Selenium server can be set to act in a standalone mode, or can be set up as a grid with a server acting as a “hub” on one computer, and a server acting as a “node” on another computer.

Browser Drivers. Because of the progress on the W3C WebDriver Specification, each major browser vendor (Google, Microsoft, Apple, and Mozilla) has committed to implementing their own driver for their respective browser. The driver is an executable file that lives on the same machine as the browser that is being automated. Read the Drivers documentation to see how to download and store the driver so that Selenium can find and use it. The driver accepts the standardized information from Selenium code and translates it into code needed by the particular browser to take the action specified.

Browser. The browser of your choice executes each command sent by the driver, and sends the results or errors back down this path to the test code.
--------------------------------------------------------------------------
##Drivers
   
As described in the Automation Pipeline document, a driver must be present on the same machine as the browser you are automating.

If you are running locally, you can use the webdrivers gem to automatically ensure that the latest driver is downloaded, and placed in a location where Selenium can access it.

Otherwise, you can download the drivers for the browser of your choice:

Google Chrome: chromedriver
Mozilla Firefox: geckodriver
Microsoft Edge: Microsoft WebDriver
Microsoft Internet Explorer: IEDriver
Apple Safari: safaridriver (no download needed, it’s pre-installed if you have Safari 10)
For all browsers except for Safari, you then need to move the driver onto your PATH. This can be especially tricky in Windows.

Alternately, you can avoid dealing with drivers entirely and use an online service provider to manage everything for you.

Sauce Labs
Browser Stack

==============================================================================

##Starting a Session
   
Opening a Browser
Once you’ve installed Watir, and your desired drivers, and have an open irb session, you can try out opening a browser with:

require 'watir'
Watir::Browser.new
By default Watir will open a Chrome Browser.

To open other browsers:

Watir::Browser.new :firefox
Watir::Browser.new :internet_explorer
Watir::Browser.new :edge
Watir::Browser.new :safari
To open a browser on a remote machine, specify the url:

Watir::Browser.new :firefox, url: "http://#{the_grid_url}:4444/wd/hub"
There are many settings that can be customized on each browsers:

Chrome
Firefox
Internet Explorer
Safari
Edge

------------------------------------------------------------------------------
#navegadores

##Chrome
   
ChromeDriver
To use Chrome, ensure you’re using the appropriate driver

Starting Chrome
Chrome is the default, so you don’t even have to specify it unless you need to add capabilities.

b = Watir::Browser.new
b = Watir::Browser.new :chrome, opts
Headless
Chrome has a new headless feature that can be accessed directly with:

b = Watir::Browser.new :chrome, headless: true
It is still under active development so not all features work yet (alerts, window switching, etc)

Chrome Options
The options hash can be created with the following parameters:

:args - an Array of command-line arguments to use when starting Chrome
:binary - a String representing the Path to the Chrome Browser executable to use
:prefs - a Hash with each entry consisting of the name of the preference and its value
:extensions - an Array of Strings listing the paths to (.crx) Chrome extensions to install on startup
:options - a Hash for raw options
:emulation - A Hash for raw emulation options
Preferences
Information on configuring preferences can be found here

prefs = {
  download: {
    prompt_for_download: false,
    default_directory: '/path/to/dir'
  }
}

b = Watir::Browser.new :chrome, options: {prefs: prefs}
Switches
See the full list of switches here

args = ['--ignore-certificate-errors', '--disable-popup-blocking', '--disable-translate']
b = Watir::Browser.new :chrome, options: {args: args}
Raw Options
See the full list of options here

b = Watir::Browser.new :chrome, options: {options: {detach: true}}
Using chrome on Heroku
You can drive the chrome browser on heroku with a cedar-14 stack. Check out this sample repo for more information on how to do this: https://github.com/jormon/minimal-chrome-on-heroku-xvfb

You can also run using a headless chrome on the heroku-16 stack. Here’s an example of that working: https://github.com/jormon/minimal-chrome-on-heroku

##Firefox
   
GeckoDriver
To use Firefox, ensure you’re using the appropriate driver Geckodriver is attempting to be 100% compliant with the soon to be released W3C WebDriver Specification, so it is not yet feature complete. It is recommended that you use the latest browser version available to have the most complete feature set.

Starting Firefox
b = Watir::Browser.new :firefox
Firefox Options
All options are explained on the geckodriver page

:args - an Array of command-line arguments to use when starting Firefox
:binary - a String representing the Path to the Firefox Browser executable to use
:profile - an encoded profile string or Firefox::Profile instance
:log_level - the String or Symbol representing the desired log level for geckodriver
:prefs - a Hash with each entry consisting of the key of the preference and its value
Firefox Profiles
You can specify an existing profile to use, such as your ‘default’ profile:

b = Watir::Browser.new :firefox, profile: 'default'
You can also create a new Firefox profile each test run using any of the options that you can configure in the about:config pane of Firefox

For example:

profile = Selenium::WebDriver::Firefox::Profile.new
profile['browser.download.dir'] = '/tmp/webdriver-downloads'
profile['browser.download.folderList'] = 2
profile['browser.helperApps.neverAsk.saveToDisk'] = 'application/pdf'

b = Watir::Browser.new :firefox, profile: profile

##Internet Explorer
   
IEDriverServer
To use Internet Explorer, ensure you’re using the appropriate driver. Note that for technical reasons it is recommended to always use the 32 bit version of the driver, regardless of your operating system.

Starting IE
b = Watir::Browser.new :ie
Configuring IE
Internet Explorer is Windows only and only works if you ensure that Protected Mode settings for each zone are set to the same value. Additional set up suggestions can be found here

Internet Explorer Options
Watir uses your standard IE settings and config, so you can manually adjust IE to how you want it before running your tests, and it will pick up these settings.

If you want to customize it in your code here are valid options:

:args
:browser_attach_timeout
:element_scroll_behavior
:full_page_screenshot
:ensure_clean_session
:file_upload_dialog_timeout
:force_create_process_api
:force_shell_windows_api
:ignore_protected_mode_settings
:ignore_zoom_level
:initial_browser_url
:native_events
:persistent_hover
:require_window_focus
:use_per_process_proxy
:validate_cookie_document_type
args = ["--log-level=DEBUG", "--log-file=/foo"]
Watir::Browser.new :ie, options: {args: args}
Last Updated: August 03, 2018

##Safari
   
SafariDriver
To use Safari, ensure you’re using the appropriate driver

safaridriver requires using Safari 10 on either El Capitan or Sierra.

Apple’s safari driver is still under active development, so there are a number of things that aren’t implemented relative to what is available on other browsers.

Since the driver that ships with MacOS Sierra does not get updated very often, it is recommended that you download and use the Safari Technology Preview. Note that this is only an option on MacOS.

Before using safaridriver, turn on the Developer Menu by opening Safari preferences from the Menu Bar, going to the Advanced tab, and ensuring that the Show Develop menu in menu bar checkbox is checked.

Enable Remote Automation by selecting “Allow Remote Automation” in the Develop Menu in the Menu Bar.

Authorize safaridriver to launch the webdriverd service which hosts the local web server. To permit this, run /usr/bin/safaridriver once manually and complete the authentication prompt.

Starting Safari
b = Watir::Browser.new :safari, technology_preview: true

##Microsoft Edge
   
Microsoft WebDriver
To use Edge, ensure you’re using the appropriate driver

Microsoft’s WebDriver is still under active development, so there are a number of things that aren’t implemented relative to what is available on other browsers.

If you are using a Windows 10 Insider Edition, ensure that your driver version matches your Windows Build number

Starting Edge
b = Watir::Browser.new :edge
--------------------------------------------------------------------------
##working elements

##Web Elements
   
Watir automatically generates classes and methods for all HTML5.1 and SVG2 supported elements and their associated attributes. These classes are encapsulated to give easier access to their specific attributes, making it easier to locate them, and providing custom features unique to them.

Here are some basic examples for interacting with elements:

Text Fields
b = Watir::Browser.start 'bit.ly/watir-webdriver-demo'
t = b.text_field id: 'entry_1000000'
t.exists?
t.set 'your name'
t.value
Select Lists – Combos
b = Watir::Browser.start 'bit.ly/watir-webdriver-demo'
s = b.select_list id: 'entry_1000001'
s.select 'Ruby'
s.selected_options
Radios
b = Watir::Browser.start 'bit.ly/watir-webdriver-demo'
r = b.radio value: 'A gem'
r.exists?
r.set
r.set?
Checkboxes
b = Watir::Browser.start 'bit.ly/watir-webdriver-demo'
c = b.checkbox value: '1.9.2'
c.exists?
c.set
c.set?
Buttons
b = Watir::Browser.start 'bit.ly/watir-webdriver-demo'
btn = b.button value: 'Submit'
btn.exists?
btn.click
Links
b = Watir::Browser.start 'bit.ly/watir-webdriver-demo'
l = b.link text: 'Google Forms'
l.exists?
l.click
Divs & Spans
b = Watir::Browser.start 'bit.ly/watir-webdriver-demo'
d = b.div class: 'ss-form-desc ss-no-ignore-whitespace'
d.exists?
d.text
s = b.span class: 'powered-by-text'
s.exists?
s.text
WYSIWYG Editors
See: WYSIWYG Editors page

##Locating Elements
   
One of the most important features of Watir is the many varied ways it allows users to locate elements. The Watir location API is designed to be easily read and understood by users (humans). Elements are located by creating a Selector Hash, which Watir translates into the potentially complicated information the driver needs to know to identify the element.

The special cases will be highlighted below, but Watir Locators:

Accept String values for exact matching
Accept RegExp values for partial matching
Can be mixed with any other Watir Locator
Can be used to find the first matching element, or all matching elements as part of a collection
Firstly, like Selenium, Watir supports the full power of directly using :css & :xpath selectors. When either of these are used, they must be the only one provided in the Selector Hash. Watir’s goal, however, is to minimize the need to rely on these powerful locators. XPath in particular can be difficult to read and can be easy to write in a brittle fashion, so Watir encourages the approach of “No More XPath!”

Additionally, it is worth noting that there are two locators defined in the WebDriver specification that Watir does not directly support because it provides the same functionality by alternate means.
These are :link_text and :partial_link_text. With Watir you can locate any element by its text, not just links, and Watir already supports partial matches for all of its locators with Regular Expressions.

Standard Watir Locators
ID
browser.div(id: "header")
browser.div(id: /header/)
Name
browser.text_field(name: 'new_user_email')
browser.text_field(name: /new_user_email/)
Tag Name
# while this works:
browser.element(tag_name: 'div')
 
# it is highly recommended to leverage this locator by using the element's associated method:
browser.div
Class Name
# This is for locating with a single class only
browser.text_field(class: 'name')
browser.text_field(class: /name/)
Text
# evaluates what is in the DOM, not what a user can see on the page
browser.button(text: "Button 2")
browser.button(text: /Button/)
Visible Text
# attempts to evaluate based on what a user can see on the page
browser.button(visible_text: "Button 2")
browser.button(visible_text: /Button/)
Data Attributes
browser.p(data_type: "ruby-library")
browser.p(data_type: /ruby-library/)
Aria Attributes
browser.p(aria_label: "ruby-library")
browser.p(aria_label: /ruby-library/)
Valid or Custom Attributes
browser.link(href: 'non_control_elements.html')
browser.link(href: /non_control_elements.html/)
browser.div(custom_attribute: "foo")
browser.div(custom_attribute: /foo/)
Label
# locate based on the value of the associated label element (not attribute)
browser.text_field(label: 'With text'))
browser.text_field(label: /With text/))
Index
this can not be used to locate an element collection
when combined with other locators, index is the last filter to be applied)
browser.div(index: 2)
Presence/Absence/Multiple Classes
this takes an Array of String or RegExp values
browser.text_field(class: ['order', 'should', 'matter', 'not'])
browser.text_field(class: ['this', '!notthis'])
Presence/Absence Attributes
this takes a Boolean value
browser.div(data_bar: false)
browser.div(data_foo: true)        
Visible
this takes a Boolean value
browser.div(visible: true)
browser.div(visible: false)
Adjacent Nodes
these are not locators in the Selector Hash
these are methods that accept a Selector Hash
anchor_element.parent(selectors)

anchor_element.previous_sibling(selectors)
anchor_element.following_sibling(selectors)
anchor_element.siblings(selectors)

anchor_element.child(selectors)
anchor_element.children(selectors)
Implementation Details
Most of the time Watir can translate the Selector Hash into a single XPath expression to quickly identify the element. You can get a sense for what this looks like by checking out our sample app XPathify. Instances where this can not be done include when the usage of :visible, :visible_text or :index locators, or (sometimes) when there are Regular Expressions in the locator values. In that case Watir locates potentially matching elements and iterates over them to provide the requested result.

#Frames
   
Think of an IFrame as a page of HTML inside of another page of HTML. They will look like this, with a src attribute that includes the inserted html:

<body>
    <h1>Iframes</h1>
    <iframe src="iframe_1.html" id="iframe_1" name="iframe1"></iframe>
    <iframe src="frame_2.html" id="iframe_2" name="iframe2"></iframe>
</body>
By default the browser driver only looks for elements in the top level browsing context. If an element exists inside of an iframe, it must be told to look there. Browser Context switching is handled for you in Watir. The only requirement is that when defining an element, it must include the full address to that element including a reference to any iframes it is nested inside. Recognize that it is possilbe for iframes to be nested inside of iframes.

b.iframe(id: 'outside').iframe(id: 'inside').div.text
b.iframe(id: 'second').text_field.set 'foo"
b.iframe(id: 'outside').button.click
As of Watir 6.9, if an element can not be located, Watir will check to see if the page has iframes and will advise the user to check to see if the element is inside of an IFrame.
-------------------------------------------------------------------------------
##Advanced Interactions

##Waiting
   
Properly synchronizing your code with the state of the browser has long been the biggest issue testers face when testing a dynamic website.

Sleeps
It is often discussed that hard coding #sleep is a bad practice. Besides being an indication that your test suite doesn’t have sufficient maturity, there are specific technical frustrations that come with hard coding sleeps. The biggest issue is that you are having to balance the concern of how long is long enough with having an additional and typically unnecessary set of 30 second sleeps scattered everywhere throughout your code.

Selenium Waits - Implicit & Explicit
Selenium has two approaches to synchronization. The first is “implicit wait.” Presumably this feature was inspired by the early versions of Watir which did a better job of automatically waiting for elements. Using implicit waits means telling the driver to apply a global value for how long to wait when attempting to locate an element if it can’t find the element. The idea behind implicit waits is good, but there are two main issues with this form of implementation, so Watir does not recommend and does not provide direct access for setting them.

The wait happens during the locate instead of when trying to act on the element. This makes it impossible to immediately query the state of an element before it is there.
Implicit waits by themselves will not be sufficient to handle all of the synchronization issues in your code. The combination of delegating waiting responsibilities to the driver and leveraging polling in the code (explicit waits) can cause weirdness that is difficult to debug.
The second and recommended approach to waiting in Selenium is to use explicit waits. This retains responsibility for synchronization with your code. In this approach your code will continuously check to see if the supplied condition is met, and continue with the next piece of the code when so. Watir waiting approaches all leverage this idea of polling for the desired output from a supplied condition

When Present and When Enabled
Prior to Watir 6.0, the best way to ensure that the code waited for the browser to be ready was to insert a  #when_present or #when_enabled method before the action.

browser.text_field(title: 'Search').when_present.set 'Hello World!'
The problem here is that you should never be using #set if you aren’t sure the element will be there or enabled, so these #when_present calls are philosophically redundant.

As such, Watir 6.0 deprecated #when_present and #when_enabled and every action call on an element effectively executes this logic by default.

Note that Watir does its automatic waiting when taking actions, not when attempting to locate. This provides additional flexibility for querying the state of an element without needing unnecessary waits.

Watir Wait and Waitable Modules
Waitable is the module that is included by Browser, Alert, Window and Element. This module provides access to two main methods: #wait_until and #wait_while. As of Watir 6, both of these methods accept :timeout, :message keyword parameters. Note that the :interval keyword was added in Watir 6.1 to allow reducing how often the condition is polled, and as of Watir 6.12 you can use a Proc instance value for :message if that is preferred to a String). Then as always, a block is passed in to establish what condition needs to be met. #wait_until will execute the block until a truthy result is returned, and #wait_while will execute the block until a falsy result is returned.

browser.wait_until { |b| b.title == "Foo" }
browser.window(title: "Foo")wait_while(&:exists?)
browser.alert.wait_until { |a| a.text == "foo" }
browser.button(name: 'submit').wait_until(&:enabled?)
Note that it is encouraged to use #to_proc syntax when possible:

# Good
browser.text_field(title: 'Search').wait_until(message: "Can't find it" &:present?)

# Less Good
browser.text_field(title: 'Search').wait_until(message: "Can't find it") { |el| el.present? }
The default timeout for Watir’s Waits is 30 seconds. You can pass in the :timeout keyword parameter to any of the wait methods, or you can change the global default with:

Watir.default_timeout = 60
Wait Until Present and Wait While Present
There are two special waiting methods that apply only to Elements. As of Watir 6.2 for #wait_while_present and Watir 6.12 for #wait_until_present, these methods have subtly changed from their previous implementation.

Most of the time you do not want to use these methods. In most circumstances you should use:

browser.div(id: 'foo').wait_until(&:present?)
browser.div(id: 'bar').wait_while(&:present?)
But what if you have this element:

<div class="here">Foo</div>
and you locate it with this code:

element = browser.div(class: "here")
and then some dynamic event caused the element class to change:

<div class="not-here">Foo</div>
The element is still there, it just no longer corresponds to the selector Watir used to locate it. Because of how Watir caches elements for performance reasons, the following code will time out (Watir will just keep verifying that the cached element is still there):

element.wait_while(&:present?)
In this case we want the element to be looked up from scratch during the polling, which is what this does:

element.wait_while_present
Similarly for #wait_until_present, the scenario is when an element is located, then goes away, and you want to wait for it to come back.

This will throw a Stale Element exception:

element.wait_until(&:present?)
This will return when the element has come back:

element.wait_until_present

##Headless
   
There are several options for running your tests headlessly. The first thing to consider is whether you actually need to run headless. Most options for this have limitations and require trade-offs.

Traditionally PhantomJS has been an option for running headlessly. The driver for this virtual browser has been deprecated, though, so it is no longer supported in Watir.

Perhaps the best option for running headlessly is using the Headless gem. The biggest limitation for this is that it only works on Unix based systems. It is the actual browser run in a virtual GUI. This is a great option for using a real world browser, albeit on a minimally used platform.

Headless gem
Code for the before hook:

require 'watir'
require 'headless'

headless = Headless.new
headless.start
Code for the after hook:

headless.destroy
Browser specific options
Both Chrome and Firefox have implemented headless modes for their browsers that work on all platforms. Recognize that this option does not include all of the browser code, so not all of the browser features are implemented, and this will not be an exact replication of what a user will see in a real browser.

Headless on Chrome

Headless on Firefox

##Basic Browser Authentication
   
The easiest and most elegant way to handle basic browser authentication is to supply the username and password in the URL, bypassing the dialog altogether.

b = Watir::Browser.start 'http://admin:password@yourwebsite.com'
Proxy Authentication
If the above method doesn’t work, eg. you are authenticating against a NTLM proxy, you may have find using the AutoAuth Firefox extension will enable you to automatically dismiss this dialog with your credentials. See this blog post for full details.

##Browser Certificates
   
Firefox
The Firefox driver properly handles untrusted certificates by default.

If you have a trusted certificate, but there is some other certificate error such as a hostname mismatch (eg. using a production certificate in test), you should do the following:

profile = Selenium::WebDriver::Firefox::Profile.new
profile.assume_untrusted_certificate_issuer = false
b = Watir::Browser.new :firefox, profile: profile
The reason this is needed is explained here.

Chrome
It is easy to ignore invalid Browser certificates in Google Chrome by passing a command line switch:

Watir::Browser.new :chrome, switches: ['--ignore-certificate-errors']


##Browser Downloads
   
Downloads are problematic in Watir because they require interacting with the Operating System, and Watir automates a Browser, not an OS. As such if any file dialog boxes are displayed, Watir will be unable to handle them. Especially if you are executing your tests on a remote machine, realize that downloads will be sent to that machine, not the machine executing your Ruby code, which makes retrieving the file effectively impossible. Additionally, actually validating the content of a file is not trivial, especially for something like a PDF.

So, before we get into strategies for dealing with downloads, consider carefully whether you need to actually download files in the first place.

Is it sufficient to validate that the link is present?
Can you download the file with a an HTTP Library instead of going through the browser?
Can you test what you need to in a lower level unit or integration test rather than in the browser?
For more thoughts on this, read this article. It is older and focused on Selenium, but the points are still relevant.

If your manager insists you absolutely must test the download via the browser, you can initialize the Browser object with parameters telling the browser to automatically download files to a particular directory rather than prompting the Operating System.

Firefox
download_directory = "#{Dir.pwd}/downloads"
download_directory.tr!('/', '\\') if Selenium::WebDriver::Platform.windows?

profile = Selenium::WebDriver::Firefox::Profile.new
profile['browser.download.folderList'] = 2 # custom location
profile['browser.download.dir'] = download_directory
profile['browser.helperApps.neverAsk.saveToDisk'] = 'text/csv,application/pdf'

b = Watir::Browser.new :firefox, profile: profile
A full list of these Firefox options are available in firefox by typing ‘about:config‘ in the address bar.

If you want to know a way to work out the file types (eg. application/pdf) then you can read the following blog post for an step by step guide.

Chrome
prefs = {
  download: {
    prompt_for_download: false,
    default_directory: '/path/to/dir'
  }
}

b = Watir::Browser.new :chrome, options: {prefs: prefs}
--------------------------------------------------------------------------------

##Browser Popups
   
When a new browser window is opened, you can then ‘use’ the new window.

browser.window(title: 'annoying popup').use do
  browser.button(id: 'close').click
end
See the Window Switching Spec for more examples.
------------------------------------------------------------------------------

##Browser Proxies
   
In many cases, you can specify a proxy to use with the proxy: {} option. While each browser driver handles this slightly differently, the following format works in Chrome or Firefox.

Example: using a proxy in Chrome or Firefox
proxy = {
  http: 'my.proxy.com:8080',
  ssl:  'my.proxy.com:8080'
}

firefox_browser = Watir::Browser.new :firefox, proxy: proxy

remote_firefox  = Watir::Browser.new :firefox, url: REMOTE_SELENIUM, proxy: proxy

chrome_browser  = Watir::Browser.new :chrome, proxy: proxy

remote_chrome   = Watir::Browser.new :chrome, url: REMOTE_SELENIUM, proxy: proxy
Be sure to specify both :http and :ssl to route both types of traffic through your proxy.

Under the hood, this is passing options to create a Selenium::WebDriver::Proxy object.

Example: setting a http and https proxy for Remote Chrome
proxy = 'my.proxy.com:8080'
browser = Watir::Browser.new :chrome, url: REMOTE_URL, proxy: {http: proxy, ssl: proxy}
-------------------------------------------------------------------------------

##Javascript Popups
   
JavaScript dialogs are fairly common in web applications.

Watir has an inbuilt library for handling these dialogs, and capturing values.

Javascript Alerts
# Check if alert is shown
browser.alert.exists?

# Get text of alert
browser.alert.text

# Close alert
browser.alert.ok
browser.alert.close
Javascript Confirms
# Accept confirm
browser.alert.ok

# Cancel confirm
browser.alert.close
Javascript Prompt
# Enter text to prompt
browser.alert.set 'Prompt answer'

# Accept prompt
browser.alert.ok

# Cancel prompt
browser.alert.close
Alternative Method
If you’re having trouble using the above method, you can override the JavaScript functions to return the value you want, so when they’re meant to show, they don’t!

# don't return anything for alert
browser.execute_script('window.alert = function() {}')

# return some string for prompt to simulate user entering it
browser.execute_script("window.prompt = function() {return 'my name'}")

# return null for prompt to simulate clicking Cancel
browser.execute_script('window.prompt = function() {return null}')

# return true for confirm to simulate clicking OK
browser.execute_script('window.confirm = function() {return true}')

# return false for confirm to simulate clicking Cancel
browser.execute_script('window.confirm = function() {return false}')

# don't return anything for leave page popup
browser.execute_script('window.onbeforeunload = null')
-----------------------------------------------------------------------------

##Measure Page Performance
   
The Watir-Performance gem aims to provide a set of navigation timing metrics for Watir actions using a W3C page performance standard. This is a perfect solution to capture response time metrics, and it’s very straightforward to do. Works in Chrome, Firefox, Edge and IE9 and up. Currently no Safari support.

require 'watir'
require 'watir-performance'

10.times do
  b = Watir::Browser.new :chrome
  b.goto 'http://watir.com'
  load_secs = b.performance.summary[:response_time] / 1000
  puts "Load Time: #{load_secs} seconds."
  b.close
end
This produces something like:

Load Time: 3.701 seconds.
Load Time: 0.694 seconds.
Load Time: 1.874 seconds.
Load Time: 1.721 seconds.
Load Time: 2.096 seconds.
Load Time: 0.823 seconds.
Load Time: 2.362 seconds.
Load Time: 1.008 seconds.
Load Time: 1.761 seconds.
Load Time: 2.066 seconds.
List of available metric groupings

:summary
:navigation
:memory
:timing
-------------------------------------------------------------------------------

##Page Objects
   
The Page Object pattern is a way to represent pages and their elements in reusable classes. Page Objects eliminate duplication by building an abstraction that allows you to write browser tests for maximum maintainability and robustness.

The Page Object pattern originated in WebDriver, and a great explanation (with examples in Java) can be found here.

You create a Page object for each page of your application, which has methods that represent the services available on a given page. You should encapsulate all the implementation details of the system (i.e. HTML elements, waiting for the DOM to update etc) in these objects. Your test code (i.e. RSpec code blocks, Cucumber step definitions) should never access the underlying Browser instance or deal with HTML elements directly.

In essence, you should have the mindset that your test code should not need to change if your web app was rewritten as a desktop app - you would simply need another implementation of the page object layer. Although strictly speaking a set of pages isn’t necessarily a good way to model a desktop application, having this in mind makes it easy to decide what should go where.

The examples below assumes you are familiar with RSpec way of doing test assertions.

Consider this script:

  browser = Watir::Browser.new
  browser.goto "http://example.com/login"

  browser.text_field(:name => "user").set "Mom"
  browser.text_field(:name => "pass").set "s3cr3t"
  browser.button(:id => "login").click

  Watir::Wait.until { browser.title == "Your Profile" }
  browser.div(:id => "logged-in").should exist
With page objects, this could become:

  site = Site.new(Watir::Browser.new)

  login_page = site.login_page.open
  user_page = login_page.login_as "Mom", "s3cr3t"

  user_page.should be_logged_in
An implementation of this could be:

 
  class BrowserContainer
    def initialize(browser)
      @browser = browser
    end
  end

  class Site < BrowserContainer
    def login_page
      @login_page = LoginPage.new(@browser)
    end

    def user_page
      @user_page = UserPage.new(@browser)
    end

    def close
      @browser.close
    end
  end # Site

  class LoginPage < BrowserContainer
    URL = "http://example.com/login"

    def open
      @browser.goto URL
      self
    end

    def login_as(user, pass)
      user_field.set user
      password_field.set pass

      login_button.click

      next_page = UserPage.new(@browser)
      Watir::Wait.until { next_page.loaded? }

      next_page
    end

    private

    def user_field
      @browser.text_field(:name => "user")
    end

    def password_field
      @browser.text_field(:name => "pass")
    end

    def login_button
      @browser.button(:id => "login")
    end
  end # LoginPage

  class UserPage < BrowserContainer
    def logged_in?
      logged_in_element.exists?
    end

    def loaded?
      @browser.title == "Your Profile"
    end

    private

    def logged_in_element
      @browser.div(:id => "logged-in")
    end
  end # UserPage
This can then be integrated with other tools. For example, using Cucumber you could have this in env.rb:

 
require "watir-webdriver"
require "/path/to/site"

module SiteHelper
  def site
    @site ||= (
      Site.new(Watir::Browser.new(:firefox))
    )
  end
end

World(SiteHelper)
And this step definition:

 
 Given /I have successfully logged in/ do
   login_page = site.login_page.open

   user_page = login_page.login_as "Mom", "s3cr3t"
   user_page.should be_logged_in
 end
Assertions/expectations should be kept in your test code. Don’t use assertions in your page objects; instead ask them about their state, and assert on the result. E.g.:

 

  #
  # bad example
  #

  class SomePage
    def assert_loaded
      raise "not loaded" unless some_element.exists?
    end
  end

  it "should be loaded" do
    page.assert_loaded
  end

  #
  # good example
  #

  class SomePage
    def loaded?
      some_element.exists?
    end
  end

  it "should be loaded" do
    page.should be_loaded
  end
See also:

Page Object gems that work with Watir-webdriver

Cheezy’s Page Object gem for Watir-webdriver and Selenium
The rSmart Test-Factory gem for Page & Data objects using Watir-webdriver
Watir Page Helper
LoadableComponent
Blog postings related to Page Objects and Watir-webdriver

cheezyworld’s series on UI testing part 1, part 2, part 3, part 4, part 5
Watermelon blog article on ‘roll your own’ page objects
Blog postings related to Page Objects and webdriver/Selenium

Page Objects on the Selenium Wiki
Page Objects in Python
Automated Testing using Page Objects and WebDriver
Acceptance tests with JBehave, Selenium and Page Objects
Using the Page Object pattern
Selenium 2/Web Driver - the land where Page Objects are king!
------------------------------------------------------------------------------
##Screenshots
   
Watir has a pretty awesome screenshot capability, built right in.

# Save screenshot to file
browser.screenshot.save 'screenshot.png'

# Represent screenshot as PNG image string
browser.screenshot.png

# Represent screenshot as Base64 encoded string
browser.screenshot.base64
The great thing about this is it gives you a screen shot of the entire page, not just above the fold.

If you’re using Cucumber also, you can easily embed this in your html report output by adding the following to your env.rb file:

After do |_scenario|
  browser.screenshot.save 'screenshot.png'
  embed 'screenshot.png', 'image/png'
end
-----------------------------------------------------------------------------
##Sending Special Keys
   
To send special keys to an element or browser page, you use the #send_keys method, with a symbolic representation of what you would like to send.

b.send_keys :enter
You can also do things like this:

b.element.send_keys [:control, 'a'], :backspace
You can also modify the click behaviour with keys:

b.element.click(:shift, :control)
The full list of keys are available from here:

:null
:cancel
:help
:backspace
:tab
:clear
:return
:enter
:shift
:left_shift
:control
:left_control
:alt
:left_alt
:pause
:escape
:space
:page_up
:page_down
:end
:home
:left
:arrow_left
:up
:arrow_up
:right
:arrow_right
:down
:arrow_down
:insert
:delete
:semicolon
:equals
:numpad0
:numpad1
:numpad2
:numpad3
:numpad4
:numpad5
:numpad6
:numpad7
:numpad8
:numpad9
:multiply
:add
:separator
:subtract
:decimal
:divide
:f1
:f2
:f3
:f4
:f5
:f6
:f7
:f8
:f9
:f10
:f11
:f12
:meta
:command
----------------------------------------------------------------------------
##WYSIWYG Editors
   
The recommended way to enter text into a WYSIWYG editor using Watir is to locate the iFrame, then find the and use the #send_keys method.

Alternately you can execute javascript on the browser object that sets the value of the WYSIWYG editor.

CKEditor
Recommended:

b = Watir::Browser.new
b.goto 'http://nightly.ckeditor.com/18-08-02-06-04/standard/samples/'
b.iframe.body.wd.clear
b.iframe.body.send_keys "foo"
Note that this example no longer works. If anyone has a working example, please update this code

b = Watir::Browser.new :firefox
b.goto 'http://nightly.ckeditor.com/18-08-02-06-04/standard/samples/'
b.execute_script("CKEDITOR.instances['editor1'].setData('hello world');")
f = b.frame(title: 'Rich text editor, editor1, press ALT 0 for help.')
f.send_keys 'hello world again'
TinyMCE Editor
Recommended:

b = Watir::Browser.new
b.goto 'http://tinymce.moxiecode.com/tryit/full.php'
f = b.iframe(id: 'cp_embed_NGegZK').iframe(id: 'result-iframe')
wysiwg = f.iframe.body
wysiwg.wd.clear
wysiwg.send_keys "hello world"
Note that this example no longer works. If anyone has a working example, please update this code

b = Watir::Browser.new
b.goto 'http://tinymce.moxiecode.com/tryit/full.php'
b.execute_script("tinyMCE.get('content').execCommand('mceSetContent',false, 'hello world' );")
b.frame(id: 'content_ifr').send_keys 'hello world again'
-------------------------------------------------------------------------------