# Difference between Imperative & Declarative code

Imperative code instructs JavaScript on how it should perform each step. With declarative code, we tell JavaScript what we want to be done, and let JavaScript take care of performing the steps.

## Imperative Code

A lot of JavaScript is imperative code. If you don't know what "imperative" means here, then you might be scratching your head a bit. According to the dictionary, "imperative" means:

    expressing a command; commanding

When JavaScript code is written imperatively, we tell JavaScript exactly what to do and how to do it. Think of it as if we're giving JavaScript commands on exactly what steps it should take. In imperative code we're **commanding** JavaScript what to do at every single step. Imperative Code is used to manually do multiple steps, it's not always the ideal solution.

## Declarative Code

In contrast to imperative code, we've got declarative code. With declarative code, we don't code up all of the steps to get us to the end result. Instead, we declare what we want done, and JavaScript will take care of doing it. This explanation is a bit abstract, so let's look at an example. Let's take the imperative for loop code we were just looking at and refactor it to be more declarative. In short, Declarative code mainly uses existing functions to reach to the end result without writing every step in the process.

    *React is Declarative*

## Example (Declarative)

    <button onClick={activateTeleporter}>Activate Teleporter</button>

Notice that there's just an onClick attribute on the button; we aren't using .addEventListener() to set up event handling with all of the steps involved to set it up. Instead, we're just declaring that we want the activateTeleporter function to run when the button is clicked.
