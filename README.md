# UIScrollView and Autolayout

Just follow these steps and you can easily use auto layout with `UIScrollView`. 

1. Add the scroll view to the storyboard and pin its 4 sides to its superview

2. Add a content view (`UIView`) to the scroll view. Pin its 4 edges to the scroll view.

3. Now, let's say, we want the content in the `UIScrollView` to scroll vertically. We need to set an equal width constraint for the content view and scroll view.

   > For horizontal scrolling, set an equal height constraint for the content view and scroll view. Then the width will be automatically calculated based on the content.

4. Add the scroll view content as subviews to the content view. Add the necessary constraints so that the storyboard isn't complaining.

That's it! Run you code and you have a perfectly autolayed out `UIScrollView`.

# *'Elastic'* Header Image View

Have you ever seen those apps where the image at the top seems to zoom in when scrolled down and snap back to its original state when released? Here is a way to implement that with just a couple of layout constraint changes.

1. Add an `UIImageView` at the top of the `UIScrollView`'s content view. Pin its leading and training edges to the parent view.

2. Add a constraint from the top of the image view to the top of the *Top Layout Guide*. Set the constant to 0. Do <u>**not**</u> add a height constraint to the image view.

   > If Xcode doesn't allow you to add this constraint, check the  image view's origin.y. Set it to 0 and retry adding the constraint.

3. Add a constraint from the top of the subview below the image view to the top of the superview. Set the constant to the image view's height.

4. You could try changing the content mode of the image view to get the best possible effect. I have set it to 'Aspect Fill'.

Happy coding!
