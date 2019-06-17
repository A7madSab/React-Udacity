# Data-Binding

## Two-way data binding

In two-way data binding, the data is kept in sync throughout the app no matter where it is updated. If a model changes the data, then the data updates in the view. Alternatively, if the user changes the data in the view, then the data is updated in the model. Two-way data binding sounds really powerful, but it can make the application harder to reason about and know where the data is actually being updated.

    Two-way binding gives your app a way to share data between a component class and its template.

## Unidirectional data flow

Data moves differently in unidirectional data flow. In React, the data flows from the parent component to a child component. The data lives in the parent component and is passed down to the child component. Even though the data lives in the parent component, both the parent and the child components can use the data. However, if the data must be updated, then only the parent component should perform the update. If the child component needs to make a change to the data, then it would send the updated data to the parent component where the change will actually be made. Once the change _is_ made in the parent component, the child component will be passed the data (that has just been updated!).

Now, this might seem like extra work, but having the data flow in one direction and having one place where the data is modified makes it much easier to understand how the application works.

    The component that stores the data should be the one that updates the data.

If data is shared between sibling child components, then the data should be stored in the parent component and passed to both of the child components that need it.
