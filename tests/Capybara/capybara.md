
## FALTA EDITAR









## Simple

#[](name) ⇒ String
Retrieve the given attribute.

element[:title] # => HTML title attribute
Parameters:

name (Symbol) — The attribute name to retrieve

#allow_reload! ⇒ Object
#checked? ⇒ Boolean
Whether or not the element is checked.
#disabled? ⇒ Boolean
Whether or not the element is disabled.
#find_css(css) ⇒ Object private
#find_xpath(xpath) ⇒ Object private
#initialize(native) ⇒ Simple constructor
A new instance of Simple.
#inspect ⇒ Object
#path ⇒ String
An XPath expression describing where on the page the element can be found.
#selected? ⇒ Boolean
Whether or not the element is selected.
#session_options ⇒ Object private
#synchronize(_seconds = nil) ⇒ Object
#tag_name ⇒ String
The tag name of the element.
#text(_type = nil) ⇒ String
The text of the element.
#title ⇒ String
The title of the document.
#value ⇒ String
The value of the form element.
#visible?(check_ancestors = true) ⇒ Boolean
Whether or not the element is visible.


## Element

#[](attribute) ⇒ String
Retrieve the given attribute.
#allow_reload! ⇒ Object
#checked? ⇒ Boolean
Whether or not the element is checked.

#disabled? ⇒ Boolean
Whether or not the element is disabled.



#initialize(session, base, query_scope, query) ⇒ Element constructor
A new instance of Element.
#inspect ⇒ Object
#multiple? ⇒ Boolean
Whether or not the element supports multiple results.
#native ⇒ Object
The native element from the driver, this allows access to driver specific methods.
#path ⇒ String
An XPath expression describing where on the page the element can be found.
#readonly? ⇒ Boolean
Whether or not the element is readonly.
#reload ⇒ Object


#selected? ⇒ Boolean
Whether or not the element is selected.


Symbols supported for keys :cancel :help :backspace :tab :clear :return :enter :shift :control :alt :pause :escape :space :page_up :page_down :end :home :left :up :right :down :insert :delete :semicolon :equals :numpad0 :numpad1 :numpad2 :numpad3 :numpad4 :numpad5 :numpad6 :numpad7 :numpad8 :numpad9 :multiply - numeric keypad * :add - numeric keypad + :separator - numeric keypad 'separator' key ?? :subtract - numeric keypad - :decimal - numeric keypad . :divide - numeric keypad / :f1 :f2 :f3 :f4 :f5 :f6 :f7 :f8 :f9 :f10 :f11 :f12 :meta :command - alias of :meta


#tag_name ⇒ String
The tag name of the element.
#text(type = nil) ⇒ String
Retrieve the text of the element.
#trigger(event) ⇒ Capybara::Node::Element
Trigger any event on the current element, for example mouseover or focus events.

#value ⇒ String
The value of the form element.
#visible? ⇒ Boolean
Whether or not the element is visible.