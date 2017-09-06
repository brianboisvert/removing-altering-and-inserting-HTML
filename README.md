Removing, Altering, and Inserting HTML
---

## Objectives

By the end of this lesson, you'll be able to

1. Removing elements from the DOM
2. Alter DOM elements programmatically
3. Insert elements into the DOM


## Removing Elements from the DOM

So now that we have spent some time seeing how we can select elements.  This is important because once we select the elements we then can manipulate the selected elements.  Let's get started with removing some elements.

For this readme, you can code along by opening the `index.html` file.

So if we want to remove the `h1` from the DOM, we first need to select the proper element and then we can remove it.  So let's open up the `index.html` in a web browser, open up a console, and type the following:

```js
  document.querySelector('h1')
  // <h1> Ada LoveLace </h1>

  document.querySelector('h1').remove()
```

In the first line, we just concentrate on selecting the correct element.  Once we saw that we got that far, we chain on the JavaScript method `remove` to remove the element.  

### Altering Elements

One problem with removing elements, is that we may want the element to reappear without re-rendering the page.  So instead of actually removing the element from the Document Object Model, we can simply set the element to hidden, and then change the element back to being visible for the element to re-appear.  This way, we never lose the element, we just change whether or not the user can see the element.  

Let's get showing and hiding our `h1`.  First refresh the `index.html` page so that we reload our HTML.  Ok, now we once again, select the element, and then let's call the `style` method.


```js
  document.querySelector('h1').style
  // CSSStyleDeclaration {alignContent: "", alignItems: "", alignSelf: "", alignmentBaseline: "", all: "", …}
  document.querySelector('h1').style.constructor
  // ƒ CSSStyleDeclaration() { [native code] }

  // We call the constructor method to better understand type of object is returned
```

As you can see, when we select a DOM element we then can access all of the styles associated with that element by calling the `style` method.  If you're coding along you can see that there are a lot of style attributes associated with each element.  But beyond viewing these attributes we can also alter them.  Let's try the following to method calls.

```js
  document.querySelector('h1').style.visibility = 'hidden'
  // our element disappears!

  document.querySelector('h1').style.visibility = 'visible'
  // our element comes back!
```

Now we are getting somewhere.  Many of the JavaScript features you see in a website involve simple hiding and displaying of elements.  And as you may have guessed, we can change not just visibility but any attribute of our element.  Let's see that:

``` javascript
let ada = document.querySelector('h1')
ada.style.backgroundColor = '#f9f9f9';
ada.innerHTML = 'Hello, DOM!'
```

Feel free to set as many properties as you'd like — this is a good chance to look around and explore different properties of DOM elements!

## Adding new HTML

Now that we have seen how to alter and remove existing elements, we can also add elements from scratch.  The easiest way to do this is with the `insertAdjacentHTML` method.  This method takes two arguments: the position of the new element, and what that new element is.  Let's insert an element directly after our the our `h1`.

```js
let ada = document.querySelector('h1')
ada.insertAdjacentHTML('afterend', '<li> Nice words</li>')
```

You can see that with the above code we first selected our `h1` and then after the element appended a new `li` DOM element.  With a quick glance at the documentation you can see all of the other ways that you can add elements to your html document.

### Summary

In this lesson, we went beyond selecting pieces of our HTML to altering our HTML as well.  In each of the sections, we first select a target element and then use that element to change our HTML.  We saw that we can remove a target element with the `remove` method, alter properties of the target by setting attributes of the target, or add in a new element using the `insertAdjacentHTML` method.

## Resources

- [remove()](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/remove)
- [insertAdjacentHTML()](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML)

<p class='util--hide'>View <a href='https://learn.co/lessons/removing-altering-and-inserting-HTML'>Removing, Altering, and Inserting HTML</a> on Learn.co and start learning to code for free.</p>
