# Reading 14a&b

## What Google Learned About Teams

The main theme of this article is a really intuitive point, but one that in practice becomes very difficult to implement.

Essentially, teams need to get better at allowing every member of a team to speak out. When we have access to everyone's thoughts, we increase collective mental horsepower.

In practice it's easy to let one or two strong members dominate, and often people are willing to go along with it, content with strong leadership within a group.

However, I definitely agree that a variety of experiences is one of the best parts of a diverse group.

> As long as everyone got a chance to talk, the team did well. But if only one person or a small group spoke all the time, the collective intelligence declined.

However, I also like the personal touch exhibited by Matt Sakaguchi. I don't think the data that Google analyzed really pointed to systematic ways to use a personal touch, which is where I think intuition and attempting to understand your team really needs to come into play.

## CSS Transforms, Transitions, and Animations

### Transforms

So a new version of CSS, CSS3, came out with the transform property, which added additional techniques to tweaking elements.

*Note*: the transform property does not have 100% browswer support (need to check the dating on this article)

Vendor Prefixes: help add specificity, with a no vendor prefix transform used to help browsers that don't support (I assume similar to a reset css or *{})

### 2D Transforms

Makes changes on a 2d Axis

- Rotate
- Scale
- Translate
- Skew

These techniques can be combined to create different effects.

### 3D Transforms

2D affects elements on horizontal and vertical axes, while 3D transforms using a z-axis.

## Transitions and Animations

> As mentioned, for a transition to take place, an element must have a change in state, and different styles must be identified for each state. The easiest way for determining styles for different states is by using the :hover, :focus, :active, and :target pseudo-classes.

Properties must have a halfway point to be transitioned.

The following properties are able to be transitioned. 

- background-colorbackground
- positionborder
- colorborder
- widthborder
- spacingbottomclipcolorcropfont
- sizefont
- weightheightleftletter
- spacingline-heightmarginmax
- heightmax
- widthmin
- heightmin
- widthopacityoutline
- coloroutline
- offsetoutline
- widthpaddingrighttext
- indenttext
- shadowtopvertical
- alignvisibilitywidthword
- spacingz
- index

## 8 Simple CSS Transitions

1. Fade in: emphasizes funtionality or a CTA
2. Change color
3. Grow & Shrink
4. Rotate elements
5. Square to circle
6. 3D shadow
7. Swing
8. Inset border