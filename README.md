# Dynamic Menu


## Getting Data from the Server

In a real application, the values in the dropdown menu might not be hardcoded. For example, the image might change depending on which items are advertised more heavily on a given day 

## How to Fetch Values?

For values that come from a server, we usually need JavaScript (note: that’s not always the case. For example, you can fetch an image from an endpoint that serves different images depending on the request or other factors).

### Code 

helper.get(endpoint, data, callback)
What does this line mean?

### helper

This is a library to facilitate making network requests. The native JavaScript way of doing so involves a lot more boilerplate, repetitive code, and is almost always replaced with an open-source solution.

### get

This specifies what method we’ll be calling the endpoint with. Though there a number of HTTP methods, get and post are by far the most popular. So if you’re just starting out, you can get away with just knowing these two. Broadly speaking, get is for getting information, post is for giving information.

### endpoint

This is the URL that our client will get the information from. Web servers need some way of communicating with the various browsers that the corresponding application might run on, so publicly available URLs are exposed to allow this.

### data

This value is like arguments to a method in programming. Servers might use (or might require) certain information to serve your request. For example, if the client is fetching a menu, we might want to specify which menu.

In a get, data is transferred by way of query parameters. What are query parameters? Let’s say our endpoint is server.com/menus, and our data is {menu: fashion}. The request will be formatted to be server.com/menu?menu=fashion.

In a post, data is transferred to the body of a request. This is useful when we want to hide the data. For example, when you login on websites, they (hopefully!) use post requests since the body can be encrypted on the wire, but the URL cannot.

### callback

Finally, a callback is the function that’s called by helper when the response is given. We can’t just do const value = helper.get(...) because a network call is an asynchronous operation. This means it comes back in an uncertain amount of time.

## globally added the property box-sizing: border-box

This means that elements specified dimensions exclude padding and borders. It’s included so we can do calculations correctly. For more information, see https://css-tricks.com/box-sizing/

## Using vertical-align 

I had to add vertical-align: top to elements. This says that when there are two elements in the same row with heights that don’t match, we should align them according to the value in this property. Without this specification, the columns would’ve lined up like so:


## Setting the width using calc

To set the widths of our newly created elements, we use calc. This lets us mix different units, which is useful when we have a ratio in mind but need to use other units. In this case, we’re subtracting some pixels to make the elements line up properly in the same row.


## To set the menu item

menu items don’t actually extend all the way to the end of the menu, so I gave the menu a bit of extra width and set width:90% and centered it on menu__main. Even though it was previously unused, well-planned groupings make it easy to customize in the future!
To have the image contained within the div, I set both width and height to 100%.


## Toggling submenu visibility 

First thing’s first: the submenu shouldn’t be visible when a menu item isn’t hovered over. Let’s set the display: none property to be the default state, and when a menu item is hovered, it toggles back to display: block.