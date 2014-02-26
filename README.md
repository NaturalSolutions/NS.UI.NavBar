NS.UI.NavBar
============

Navigation bar implementing "Modern UI" guidelines. Features include a context
switcher, contextual actions, a user box and a search box.

## Concepts ##

The idea behind this component is the following: a user is doing one thing at a
time with your application and doing a task involves being focused on a
particular section of your business model.

Some deductions:
- the navigation component should only display options which are valid from the
current context
- a user will usually navigate from one task to another closely related task,
remaining in the same set of mind
- sometimes, though, when a task is over, the user may switch to a completely
different task

That's why the NavBar component provides:
- a context switcher which is not too proeminent because it will not be used
very often
- a reminder of the current context next to the application name
- some contextual actions which are very proeminent and relevant to the current
action.

## How to use ##

Just create an instance of `NS.UI.NavBar` as you would with any `Backbone.View`
and then, render it and attach it to your document (usually at the beginning of
the body).

The init method accept several arguments, the most important being a list of
your contexts. Each context is described with the following properties: a title,
a URL, an optional CSS class string and a list of allowed user profiles. Have
a look at the demo app to get the exact syntax.

After that, you will have to use several NavBar method to keep it up to date.
The `.setaActions()` method will let you control which contextual actions are
displayed. Usually, you will wire up this method into the router logic.

Actions are described by the following properties: a title and a list of allowed
user profiles. The behaviour is given by either a URL (will behave as a link) or
a handler (implement whatever behaviour you want in a callback function).

Some CSS files are provided for an easy and rapid integration in a prototype.
But you will probably need to refine or replace it

## About permission control ##

When you configure the NavBar component, you will have to define for which user
profile an action or tile is allowed.

Consequently, the NavBar will hide tiles or actions not allowed to the current
user. Please keep in mind that this feature only improve usability. *It does not
enforce security at all*.

If you have a look at the demo application, you will notice that the "Admin"
tile disappear for non-moderator profiles. But one can still type `#admin` in
the browser's location bar and the Backbone router will trigger the admin view.

If you need to enforce some king of security, you will have to implement it by
yourself wherever it is relevant.

## Contributors ##

Gilles Bassière, [Natural Solutions](http://natural-solutions.eu/)
