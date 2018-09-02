## FALTA EDITAR


## Driver base

#accept_modal(type, **options, &blk) ⇒ String
Execute the block, and then accept the modal opened.

Parameters:

type (:alert, :confirm, :prompt)
options (Hash) — a customizable set of options
Options Hash (**options):

:wait (Numeric) — How long to wait for the modal to appear after executing the block.
:text (String, Regexp) — Text to verify is in the message shown in the modal
:with (String) — Text to fill in in the case of a prompt
Returns:

(String) — the message shown in the modal

#close_window(handle) ⇒ Object
#current_url ⇒ Object
#current_window_handle ⇒ Object
#dismiss_modal(type, **options, &blk) ⇒ String
Execute the block, and then dismiss the modal opened.

Parameters:

type (:alert, :confirm, :prompt)
options (Hash) — a customizable set of options
Options Hash (**options):

:wait (Numeric) — How long to wait for the modal to appear after executing the block.
:text (String, Regexp) — Text to verify is in the message shown in the modal
Returns:

(String) — the message shown in the modal

#evaluate_async_script(script, *args) ⇒ Object
#evaluate_script(script, *args) ⇒ Object
#execute_script(script, *args) ⇒ Object
#find_css(query) ⇒ Object
#find_xpath(query) ⇒ Object
#frame_title ⇒ Object
#frame_url ⇒ Object
#go_back ⇒ Object
#go_forward ⇒ Object
#html ⇒ Object
#invalid_element_errors ⇒ Object
#maximize_window(handle) ⇒ Object
#needs_server? ⇒ Boolean
#no_such_window_error ⇒ Object
#open_new_window ⇒ Object
#refresh ⇒ Object
#reset! ⇒ Object
#resize_window_to(handle, width, height) ⇒ Object
#response_headers ⇒ Object
#save_screenshot(path, **options) ⇒ Object
#session_options ⇒ Object
#status_code ⇒ Object
#switch_to_frame(frame) ⇒ Object
#switch_to_window(handle) ⇒ Object
#visit(path) ⇒ Object
#wait? ⇒ Boolean
#window_handles ⇒ Object
#window_size(handle) ⇒ Object






##session

#accept_alert(text = nil, **options, &blk) ⇒ String
Execute the block, accepting a alert.
#accept_confirm(text = nil, **options, &blk) ⇒ String
Execute the block, accepting a confirm.
#accept_prompt(text = nil, **options, &blk) ⇒ String
Execute the block, accepting a prompt, optionally responding to the prompt.
#config ⇒ Object
#configure {|config| ... } ⇒ Object
Accepts a block to set the configuration options if Capybara.threadsafe == true.
#current_host ⇒ String
Host of the current page.
#current_path ⇒ String
Path of the current page, without any domain information.
#current_scope ⇒ Object
#current_url ⇒ String
Fully qualified URL of the current page.
#current_window ⇒ Capybara::Window
Current window.
#dismiss_confirm(text = nil, **options, &blk) ⇒ String
Execute the block, dismissing a confirm.
#dismiss_prompt(text = nil, **options, &blk) ⇒ String
Execute the block, dismissing a prompt.
#document ⇒ Object
#driver ⇒ Object
#evaluate_async_script(script, *args) ⇒ Object
Evaluate the given JavaScript and obtain the result from a callback function which will be passed as the last argument to the script.
#evaluate_script(script, *args) ⇒ Object
Evaluate the given JavaScript and return the result.
#execute_script(script, *args) ⇒ Object
Execute the given script, not returning a result.
#go_back ⇒ Object
Move back a single entry in the browser's history.
#go_forward ⇒ Object
Move forward a single entry in the browser's history.
#html ⇒ String (also: #body, #source)
A snapshot of the DOM of the current document, as it looks right now (potentially modified by JavaScript).
#initialize(mode, app = nil) ⇒ Session constructor
A new instance of Session.
#inspect ⇒ Object
#open_new_window ⇒ Capybara::Window
Open new window.
#raise_server_error! ⇒ Object
Raise errors encountered in the server.
#refresh ⇒ Object
Refresh the page.
#reset! ⇒ Object (also: #cleanup!, #reset_session!)
Reset the session (i.e. remove cookies and navigate to blank page).
#response_headers ⇒ Hash{String => String}
Returns a hash of response headers.
#save_and_open_page(path = nil) ⇒ Object
Save a snapshot of the page and open it in a browser for inspection.
#save_and_open_screenshot(path = nil, **options) ⇒ Object
Save a screenshot of the page and open it for inspection.
#save_page(path = nil) ⇒ String
Save a snapshot of the page.
#save_screenshot(path = nil, **options) ⇒ String
Save a screenshot of page.
#status_code ⇒ Integer
Returns the current HTTP status code as an Integer.
#switch_to_frame(frame) ⇒ Object
Switch to the given frame.
#switch_to_window(window = nil, **options, &window_locator) ⇒ Capybara::Window
Window that has been switched to.
#using_wait_time(seconds) ⇒ Object
Yield a block using a specific wait time.
#visit(visit_uri) ⇒ Object
Navigate to the given URL.
#window_opened_by(**options, &block) ⇒ Capybara::Window
Get the window that has been opened by the passed block.
#windows ⇒ Array<Capybara::Window>
Get all opened windows.
#within(*args) ⇒ Object (also: #within_element)
Executes the given block within the context of a node.
#within_fieldset(locator) ⇒ Object
Execute the given block within the a specific fieldset given the id or legend of that fieldset.
#within_frame(*args) ⇒ Object
Execute the given block within the given iframe using given frame, frame name/id or index.
#within_table(locator) ⇒ Object
Execute the given block within the a specific table given the id or caption of that table.
#within_window(window_or_proc) ⇒ Object
This method does the following:.


