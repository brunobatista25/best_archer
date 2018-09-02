## FALTA EDITAR



## Matchers


#assert_no_title(title, **options) ⇒ true
Asserts that the page doesn't have the given title.

#assert_title(title, **options) ⇒ true
Asserts that the page has the given title.

#has_no_title?(title, **options) ⇒ Boolean
Checks if the page doesn't have the given title.

#has_title?(title, **options) ⇒ Boolean
Checks if the page has the given title.

#==(other) ⇒ Object
#assert_all_of_selectors([kind = Capybara.default_selector], *locators, options = {}) ⇒ Object
Asserts that all of the provided selectors are present on the given page or descendants of the current node.
#assert_matches_selector(*args, &optional_filter_block) ⇒ Object
Asserts that the current_node matches a given selector.
#assert_no_selector(*args, &optional_filter_block) ⇒ Object (also: #refute_selector)
Asserts that a given selector is not on the page or a descendant of the current node.
#assert_no_text(*args) ⇒ true
Asserts that the page or current node doesn't have the given text content, ignoring any HTML tags.
#assert_none_of_selectors([kind = Capybara.default_selector], *locators, options = {}) ⇒ Object
Asserts that none of the provided selectors are present on the given page or descendants of the current node.
#assert_not_matches_selector(*args, &optional_filter_block) ⇒ Object (also: #refute_matches_selector)
#assert_selector(*args, &optional_filter_block) ⇒ Object
Asserts that a given selector is on the page or a descendant of the current node.
#assert_text(*args) ⇒ true
Asserts that the page or current node has the given text content, ignoring any HTML tags.
#has_button?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a button with the given text, value or id.
#has_checked_field?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a radio button or checkbox with the given label, value or id, that is currently checked.
#has_css?(path, **options, &optional_filter_block) ⇒ Boolean
Checks if a given CSS selector is on the page or a descendant of the current node.
#has_field?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a form field with the given label, name or id.
#has_link?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a link with the given text or id.
#has_no_button?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no button with the given text, value or id.
#has_no_checked_field?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no radio button or checkbox with the given label, value or id, that is currently checked.
#has_no_css?(path, **options, &optional_filter_block) ⇒ Boolean
Checks if a given CSS selector is not on the page or a descendant of the current node.
#has_no_field?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no form field with the given label, name or id.
#has_no_link?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no link with the given text or id.
#has_no_select?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no select field with the given label, name or id.
#has_no_selector?(*args, &optional_filter_block) ⇒ Boolean
Checks if a given selector is not on the page or a descendant of the current node.
#has_no_table?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no table with the given id or caption.
#has_no_text?(*args) ⇒ Boolean (also: #has_no_content?)
Checks if the page or current node does not have the given text content, ignoring any HTML tags and normalizing whitespace.
#has_no_unchecked_field?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no radio button or checkbox with the given label, value or id, that is currently unchecked.
#has_no_xpath?(path, **options, &optional_filter_block) ⇒ Boolean
Checks if a given XPath expression is not on the page or a descendant of the current node.
#has_select?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a select field with the given label, name or id.
#has_selector?(*args, &optional_filter_block) ⇒ Boolean
Checks if a given selector is on the page or a descendant of the current node.
#has_table?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a table with the given id or caption:.
#has_text?(*args) ⇒ Boolean (also: #has_content?)
Checks if the page or current node has the given text content, ignoring any HTML tags.
#has_unchecked_field?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a radio button or checkbox with the given label, value or id, that is currently unchecked.
#has_xpath?(path, **options, &optional_filter_block) ⇒ Boolean
Checks if a given XPath expression is on the page or a descendant of the current node.
#matches_css?(css, **options, &optional_filter_block) ⇒ Boolean
Checks if the current node matches given CSS selector.
#matches_selector?(*args, &optional_filter_block) ⇒ Boolean
Checks if the current node matches given selector.
#matches_xpath?(xpath, **options, &optional_filter_block) ⇒ Boolean
Checks if the current node matches given XPath expression.
#not_matches_css?(css, **options, &optional_filter_block) ⇒ Boolean
Checks if the current node does not match given CSS selector.
#not_matches_selector?(*args, &optional_filter_block) ⇒ Boolean
Checks if the current node does not match given selector Usage is identical to Capybara::Node::Matchers#has_selector?.
#not_matches_xpath?(xpath, **options, &optional_filter_block) ⇒ Boolean
Checks if the current node does not match given XPath expression.




## Opçōes para auxiliares para matchers.

** Essas opçōes não são para todos o comandos não, sugiro ir na domcumentação e ver qual comando comando usa as opcōes nesse [Link](https://www.rubydoc.info/github/teamcapybara/capybara/master/Capybara/Node/Matchers)



**:wait** — Tempo máximo que a Capybara esperará pelo título para eq / match dado o argumento string / regexp

**:exact** — Quando passada uma string, a correspondência deve ser exata ou apenas substring