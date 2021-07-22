# JS Mini Challenge: Event Handling (PART 2)

## Instructions

Fork this repo, then run `git clone` to download your fork locally. Then `cd` into the downloaded directory and open it in your text editor with `code .`.

## Submitting

When you’re finished, run the following commands in your terminal to submit:

```
git add .
git commit -m 'Done'
git push
```

To get feedback on your code, make a [pull request from your forked repo](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork). If you worked with a partner, you can tag your partner on the pull request.


## Assignment

In this challenge, we're going to keep working on Raffy's Amazon trip page and give our users the ability to:

- Like an animal sighting
- Delete an animal sighting
- View the update animal sighting description form
- **BONUS**: Update animal sighting description 

We've got some starter code already written for us (this should look somewhat familiar from the previous challenges - a few extra elements are being created inside the `renderAnimalSightingPost` function for today's deliverables). Your job is to add some additional functionality to make our app even more dynamic by handling user interactions.

There's a section in this Readme file for your notes on each deliverable. As you go through the deliverables, write down some notes in this file on how you solved each problem. It'll help reinforce what you learned and give you a head start next time you see a similar problem.

## Deliverable 1: Like an animal sighting

**When a user clicks an animal sighting's like button**, that animal sighting's likes should increase by 1. The likes won't persist (if you refresh the page, they'll reset to their original value) - we'll add persistence in a future challenge.


**YOUR NOTES**
```
Using the nested approach. Added an event listener inside the renderAnimalSightingPost method. Used the predefined likeButton reference to the like button inside the function. The event listener increases the like count of the given object and also updates the displayed number of likes.
```

## Deliverable 2: Delete an animal sighting

**When a user clicks an animal sighting's delete button**, that animal sighting should be removed from the page. This won't persist (if you refresh the page, you'll see the animal sighting is back) - we'll add persistence in a future challenge.

**YOUR NOTES**
```
Using the nested approach as well. Added an event listener inside the renderAnimalSightingPost function. Also used the predefined deleteButton reference to the delete button, which already exists inside the function. The event listener removes a list element which is referenced by the variable "li" (which includes animal sighting to be deleted).
```

## Deliverable 3: View the update animal sighting description form

**When a user clicks an animal sighting's 'Toggle Update Form' button**, the form associated with that animal sighting should toggle between displaying and not displaying on the page. Look into the [display](https://www.w3schools.com/css/css_display_visibility.asp) CSS property to accomplish this task. Think about how we access CSS properties on elements using JavaScript (*hint - `element.style`*).


**YOUR NOTES**
```
Added a nested event listener to the updateButton and checked for the updateForm.style.display's status (i.e. whether it is "none" or "block") through a conditional and changed it accordingly. The display switches from none to block or vice versa depending on its status when the updateButton is clicked.
```


## BONUS: Update animal sighting description

**When a user submits an animal sighting's `form.update-form`**, the `<p></p>` element that displays the description of that animal sighting should be updated with the new description.

The data won't persist (when you refresh the page, the description will reset to its original value) - we'll see how to fix this later on. For now, focus on updating the description of the animal sighting on the page when the form is submitted!


Some things to keep in mind:

- Make sure you're using the form *submit* event, not the *click* event.
- If you see the page refresh, consider adding some code to *prevent* the *default* behavior of a form submitting.
- You can use the `name` attribute of the input elements as an easy way to reference the input fields within the form. For example: `document.querySelector("#new-animal-sighting-form").link` will look inside the `form#new-animal-sighting-form` and return the `input` element with the `name='link'` attribute
- Once you have access to an input field, you still need to retrieve its *value* to see what the user entered in the form!

**YOUR NOTES**
```
Added a nested 'submit' event listener for updateForm. Retrieved the values inputted to the form and assigned them to the description attribute of the animal sighting being updated and also changed the displayed description to the updated description. Called the preventDefault() method on the event at the start in order to prevent the default behavior of a form submitting. Didn't reset the form with updateForm.reset() because that wouldn't allow users to find what they last updated when reupdating. Without the reset, whenever they click on the update toggle button, their most recently updated description is already pre-filled in the text field. Also set the display of the update form to "none" when updating because it makes sense to not show the update form once the users submit the form. If they want to reupdate, they can just click on the toggle update button again and open the form.
```

