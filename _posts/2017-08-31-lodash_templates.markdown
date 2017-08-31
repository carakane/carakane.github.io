---
layout: post
title:  "Lodash Templates"
date:   2017-08-31 16:55:08 +0000
---


Templates are, at their core, exactly what they sound like: preset structures into which we can insert data. Lodash, a JavaScript library, allows us to create these templates. You can imagine that the Lodash template at its most basic allows you to interpolate data into a structure, and the first examples of templating in the [Lodash documentation](https://lodash.com/docs/4.17.4#template) do just that. A more complex example is how to collect data from a form and then dynamically append that data.

Say that we want to collect dog data. In our HTML we might have a form like this:

```
<form onsubmit="createDog();return false;">
  Dog Name: <input type="text" id="dogName"><br>
  Dog Breed: <input type="text" id="dogBreed"><br>
  <input type="submit">
</form>
```

This form calls a function, createDog(), when it is submitted. Our createDog() (in a JS file), then, looks like this:

```
function createDog() {
  // the data we're retrieving from our form
  var dogName = document.getElementById("dogName").value;
  var dogBreed = document.getElementById("dogBreed").value;

  // create a Lodash templating function to which we can add our retrieved data; the element retrieved, in this case #dog-template, is located in our HTML, as discussed below. we're interested in the innerHTML because that is where the actual template is located
  var dogTemplate = _.template(document.getElementById("dog-template").innerHTML);

  // call the function with our retrieved data, creating a string of HTML
  var dogHTML = dogTemplate({ 'name': dogName, 'breed': dogBreed });

  // locate where we want to insert this string of HTML
  var dogDiv = document.getElementById("dog");
 
  // append the string of HTML created by our called Lodash function to that element
  dogDiv.innerHTML += dogHTML;
}
```

The template we're sending this to also belongs in the HTML, but it's important to note that this is just the template. It is a structure for the data, but not *where* we will append the data. The values inside the template delimiters (<%= %>), are the location keys specified in our createDog() that indicate where each piece of data belongs. (Of note, other template delimiters are available, i.e., <%- %>, <% %>).

```
<script id="dog-template" type="text/x-lodash-template">
	<div class="dog">
		Name:<%= name %></br>
		Breed:<%= breed %></br>
	</div>
</script>
```

One more thing we need in the HTML is where we're sending our data after the Lodash template function runs:

`<div id="dog"></div>`

In this more complex example of Lodash templates, we retrieve data; process the data, manipulating it so that it follows the structure we've specified in our template; and then append the data, in its new structure, to the HTML. When we first loaded our page, we had a form for entering new dogs, but as we fill in the form and click submit, the dogs we've created appear on the page, using the structure of our template.

A variation on this basic process allows us to replace an element, instead of appending to it (e.g., dogDiv.innerHTML = dogHTML;), in which case each time we hit submit the most recent dog would appear and take the place of the previous dog.

We can also add new elements to the page by appending a Lodash templating function to an element without interpolating any data. In our HTML we might have:

```
<script id="new-template" type="text/x-lodash-template">
		<div class="new">I am a New Dog</div>
</script>
```

And in our JS we can add this to our createDog():

```
  var newTemplate = _.template(document.getElementById("new-template").innerHTML);
  var newDiv = document.getElementById("dog");
  newDiv.innerHTML += newTemplate();
```

Using this, every time a new dog is submitted "I am a New Dog" would be added underneath that entry. Running newTemplate() results in an HTML string, which in this case appends a div with the class of new every time a new dog element is created. Lodash templates get far more complex than this, and making them conform exactly to your preferences can be tricky, but these examples are a starting point for understanding the logic underpinning the templating function.



