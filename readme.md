
#How to make an expandable fact box for news articles#

You need three pieces of code: javascript, html and css. Off we go!

##HTML##

You have your text which you want to expand and collapse - let's say you're writing about cats and it's an explainer box about the science of the cat meow.

`<h3>Fact box</h3>`
`<p> Cat meows are loud and annoying or sweet and endearing Lorem ipsum dolor sit amet, usu ea elit intellegebat, his nostro discere cu. Eam eu lorem velit, te sea elitr putant. Per paulo nostrum adversarium no. Eu eos autem libris commodo, at per tation voluptua omittantur. Noluisse recteque vituperata id qui, et esse partem timeam vim, ipsum deleniti delicata id cum.</p>`

You've got to put this text in a new `<div>` so the function can operate on it. We'll call it `<div class="more-less-box"`

We then want to give the specific paragraph you want to expand/collapse two classes `<p class= "more-less-area collapsed"> This lets the javascript and the CSS know that to operate on. 

We've then got to build a button so that the user can actually operate the toggle! 

We write a link element, but instead of linking to a URL, it will link to the javascript function which operates the toggle. 

So we use `<a>` for link element, `href=` which tells the element where to link to and `onclick=` which instructs what to do when the button is clicked. We can also include a string of text which is what will show on the button. 

`onclick=` is important. We want to tell paragraph to toggle between its two classes, `more-less-area` and `collapsed`, when the button is clicked. The show/hide function works because when `more-less-area` is toggled OFF, leaving `collapsed`, we have set the CSS for `collapsed` to make it look like the box has collapsed. So the `onclick=` looks like:

`onclick="toggleMoreLess('.more-less-area')"`

And the whole element looks like:

`<a class="more-less-button" href="javascript:void(0);" onclick="toggleMoreLess('.more-less-area')">Show/Hide Box</a>`

Your finished piece of html for your new `<div class="more-less-box">` should look like this:

`<div class="more-less-box">`
` <h3>`
 ` Fact Box `
` </h3>`
` <p class="more-less-area collapsed">`
 `Cat meows are loud and annoying or sweet and endearing Lorem ipsum dolor sit amet, usu ea elit intellegebat, his nostro discere cu. Eam eu lorem velit, te sea elitr putant. Per paulo nostrum adversarium no. Eu eos autem libris commodo, at per tation voluptua omittantur. Noluisse recteque vituperata id qui, et esse partem timeam vim, ipsum deleniti delicata id cum.`
` </p>`
 `<a class="more-less-button" href="javascript:void(0);" onclick="toggleMoreLess('.more-less-area')">Show/Hide Box</a>`
`</div>`

You're all done - great job!

##Javascript##

Now you need to create the function which instructs the html to toggle.
You need the function toggleMoreLess, followed by the parameter areaClass. This lets the function know what class the expandable box should apply to. You should then open curly brackets, in which you tell the function the specific selector on which to operate. 

  `function toggleMoreLess(areaClass) {}`

$ in javascript is a shorter way of writing getElementById, a command which tells the function which element the function should operate on. You want to tell it to operate on `areaClass` so you write

`function toggleMoreLess(areaClass) {$(areaClass)}`

Next you need to tell the function what you the area to look like when the function operates, that is - what it toggles to. This javascript for this toggle setting is `.toggleClass` So you write

`function toggleMoreLess(areaClass) {$(areaClass).toggleClass}`

But the function now needs to know what the area should look like when the toggleClass operates. So you need to give the function some CSS instructions to tell it how the box should appear when toggleClass is operated. We'll call this CSS selector 'collapsed'. Altogether:

`function toggleMoreLess(areaClass) {
$(areaClass).toggleClass ('collapsed');
}`

Remember, the last command in a function must always have a semi-colon. 

Function written! 

##CSS##

Now you need to write the CSS for the `'collapsed'` selector. 
We want the box to shrink in height so we'll make it `max-height: 20px;`. We also want to make sure that when the box shrinks, only the text that fits inside its new shrunken size is visible, which means we need to make the rest of the text - the overflow - hidden. So we write `overflow: hidden;` Altogether:

`.collapsed {
max-height: 20px;
overflow: hidden;
}`

Way to go! Remember, each of these github code files must be saved separately, in their respective formats. 



