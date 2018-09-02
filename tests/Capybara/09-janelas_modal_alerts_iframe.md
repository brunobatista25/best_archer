
## Janelas,Modal,Alerts e Iframe
------------------------------------------------------------------------------

## Janela

## become_closed

Aguarde a janela ficar fechada.

```ruby
```
#close_window(handle) ⇒ Object

#current_window ⇒ Capybara::Window
Current window.
#maximize_window(handle) ⇒ Object
#open_new_window ⇒ Object
#refresh ⇒ Object
#go_back ⇒ Object
Move back a single entry in the browser's history.
#go_forward ⇒ Object
Move forward a single entry in the browser's history.
#resize_window_to(handle, width, height) ⇒ Object
#window_handles ⇒ Object
#window_size(handle) ⇒ Object
#open_new_window ⇒ Capybara::Window
Open new window.
#window_opened_by(**options, &block) ⇒ Capybara::Window
Get the window that has been opened by the passed block.
#windows ⇒ Array<Capybara::Window>
Get all opened windows.
#switch_to_window(window = nil, **options, &window_locator) ⇒ Capybara::Window
Window that has been switched to.
#within_window(window_or_proc) ⇒ Object
This method does the following:.
------------------------------------------------------------------------------

## Modal

#within(*args) ⇒ Object (also: #within_element)
Executes the given block within the context of a node.

#accept_modal(type, **options, &blk) ⇒ String
Execute the block, and then accept the modal opened.

#dismiss_modal(type, **options, &blk) ⇒ String
Execute the block, and then dismiss the modal opened.

------------------------------------------------------------------------------
## Iframe

#switch_to_frame(frame) ⇒ Object
Switch to the given frame.

#within_frame(*args) ⇒ Object
Execute the given block within the given iframe using given frame, frame name/id or index.

------------------------------------------------------------------------------
## Alerts

#accept_alert(text = nil, **options, &blk) ⇒ String
Execute the block, accepting a alert.
#accept_confirm(text = nil, **options, &blk) ⇒ String
Execute the block, accepting a confirm.
#accept_prompt(text = nil, **options, &blk) ⇒ String
Execute the block, accepting a prompt, optionally responding to the prompt.
#dismiss_confirm(text = nil, **options, &blk) ⇒ String
Execute the block, dismissing a confirm.
#dismiss_prompt(text = nil, **options, &blk) ⇒ String
Execute the block, dismissing a prompt.

------------------------------------------------------------------------------

## Outros

#within_fieldset(locator) ⇒ Object
Execute the given block within the a specific fieldset given the id or legend of that fieldset.

#within_table(locator) ⇒ Object
Execute the given block within the a specific table given the id or caption of that table.