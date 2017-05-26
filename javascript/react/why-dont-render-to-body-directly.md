# Don’t Render to Body

Don’t ever render to `document.body`. A lot of React examples do that because 
it’s less typing and looks more clear. 

Don’t. Do. This.

React wants to fully manage DOM tree under its control.
If you append something foreign inside a DOM tree managed by React,
it might seriously freak out, unless you do it very carefully
(e.g. inside a leaf component that has `shouldComponentUpdate` returning false).

What’s the problem with `<body>` ?

Everybody updates it!

Some people have non-React code that attaches modals to it.

Google Font Loader will happily put <span> elements into body for a fraction of second,
and your app will break horribly and inexplicably if it tries to update something on
the top level during that time.

Do you really know what all your third party scripts are doing?

What about ads or that social network SDK?

Finally, consider something you have no control over: browser plugins.
Yes, they can inject stuff into `<body>`. 

Of course they can also mess with the rest of the DOM,
but at least you can fix the most widespread case.

So what do you do?

Always put a root `<div>` into `<body>`, give it an ID and render into it.

Another advantage of doing so is that you can put your scripts at the bottom of 
the `<body>` and you won’t need to wait for DOMContentLoaded before rendering.

-- taken from Dan Abramov's post
