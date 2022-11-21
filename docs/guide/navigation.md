# Navigation

In the navigation settings, it is possible to change the navigation bar, the footer and the help menu.
It is possible to change the links, add new links or create own pages.

## Attributes

| Attribute                    | Description                                                             |
|------------------------------|-------------------------------------------------------------------------|
| Title                        | Title of navigation link                                                |
| Sublink                      | This allows to create dropdown menus.                                   |
| Enabled                      | Affects the visibility of navigation link                               |
| Required Property            | [Optional] Specify a property which controls the visibility of the link |                                    
| Icon                         | [Optional] Icon prepended to title                                      |
| Type                         | Type of navigation link (link / html content)                           |
| URL (link only)              | Internal link or URL to other website                                   |
| CMS Page (html content only) | Related CMS Page                                                        |

## Enable / Disable Navigation

`Navigation Links` can be enabled / disabled by pressing the `edit` button.  
Set the checkbox `enabled` and confirm.

## Custom Links

External pages can easily be linked by adding a new navigation link with the type of `external link`.

## Update Order of Navigation Links

Drag and drop the `navigation links` in the order you want them to be in.  
Confirm with pressing the `update nav order` button.

# HTML Page

Custom pages can be created by first adding a HTML page. Secondly a new navigation link with the type of `HTML content`
has to be created linking the page.

> JavaScript and other dangerous HTML tags are escaped and not rendered, unless edited by an admin

## Attributes

| Attribute       | Description                                                                        |
|-----------------|------------------------------------------------------------------------------------|
| Title           | Title of the page                                                                  |
| Content         | Content (use only one input field)                                                 |
| Requirement Set | [Optional] A requirement set which can be used to limit the access to the webpage. |
