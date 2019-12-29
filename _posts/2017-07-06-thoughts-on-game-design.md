---
layout: post
title: Thoughts on Game Design
categories:
- blog
---

This post is going to be less of a standard "progress update" like the other posts on this blog and more of a typical blog post.
It includes some of my thoughts on game design and a broad look at how Alluvial will be designed,
and it's a little bit of a long read.

I have been wanting to make a post like this to address why I have a lot to say about the technology of Alluvial
but have written and said less about the gameplay.
Part of this is simply that I am working on the technology right now, and the gameplay is going to come later.
But this also comes from my philosophy on game design, so I wanted to talk about that here.


## Game Design

Game design is a very flexible process.
One important part of game design is understanding that while the player experience is what we are trying to create,
the rules and procedures of the system are what we actually have control over.
There's a fundamental disconnect there.
This is one reason why it's difficult to create fun games.
It's often difficult to predict how a change in the game rules will effect the experience of the player.
This is why expert game designers and game design teachers have one major piece of advice seen across the board:
iteratively design your games be adding rules, playtesting, and evaluating whether to keep the rules you just added.

So while I have notes, planning documents, and vision about how the gameplay of Alluvial will be implemented,
when it comes to laying down those rules and procedures I am going to make sure that I am trying lots of things and playtesting them.

If you're interested in learning more about game design from this perspective, I recommend
[Game Design Workshop by Tracy Fullerton](http://www.gamedesignworkshop.com/), which is the textbook I teach with in my Game Design class.
I also recommend [Art of Game Design by Jesse Schell](http://www.jesseschell.com/) and [Rules of Play by Tekinbaş and Zimmerman](https://mitpress.mit.edu/rules)
if you're planning to do a whole lot of summer reading :)

---

As such, even when I have a good idea in my head for how I want some gameplay feature to be implemented, I'll be a bit hesitant to write or talk about it.
Part of this is because I wouldn't want to give a false impression of what the game will be like,
since I know that features will be subject to change during the development process.

However, I think there's a fair bit more to it than that.
Like I said before, game design is about creating a player experience.
When it comes to designing Alluvial, I have plans for how to create that player experience, but the plans aren't as important as the intended player experience.
And while the plans can and will likely change, it's the player experience which is the more immutable core of the Alluvial vision.
And player experience is something which is difficult to put into words while still seeming like you know what you're talking about.

This is all a bit abstract so let's go through a motivating example when it comes to Alluvial.


## Inventory Systems

One element of the core Alluvial vision is limited inventory space.
I don't want the player to be able to pick up and hold everything they can find in the world.
There are a number of ways this contributes to interesting gameplay.
For one, it encourages players to create infrastructure to facilitate movement and collection of items.
This can include canals and mine-carts, pack animals that follow roads, and stockpiles and storage rooms.
It also creates potential for an interesting carried storage system, where players can craft belts and backpacks that meet special storage needs.
It places special value on spells of holding and other magical solutions to storage.
And, of course, it forces players to carefully evaluate and choose what they pick up while on the go.

I've always known that I want to explore this inventory and storage mechanic in Alluvial.
However, I've thought of a few ways that I'd consider implementing it.
They more or less fall on a spectrum between a very limited player inventory and a more standard inventory experience.

### The Inventory Spectrum

On the stricter side, let's consider having a standard inventory that only allows the player to pick up small items.
An apple, a stack of gold coins, a twig - these could all be picked up with a click and stored in a manageable inventory space.
However, anything larger than that can't just be tucked away into a mysterious abstract inventory.
It has to be picked up and carried.
This means that collecting wood to build a house is a rather arduous task - taking numerous trips into the woods to bring back logs one at a time.
Or, more hopefully, it means that the player needs a creative solution to something that many games taken for granted.
Perhaps the player enlists the help of friendly villagers in carrying logs for a stockpile.
Maybe the player builds a barge and only chops down trees that are near to a river.

Somewhere in the middle of this inventory spectrum is a [system that allocates a grid for the player](http://tvtropes.org/pmwiki/pmwiki.php/Main/GridInventory)
where larger objects take up more space.
In this way, the player may be able to hold a hundred apples in their backpack, but only fit four or so logs in that same space.

Finally, we could use a somewhat standard stacking inventory that simply enforces a smaller stack size maximum for larger items.
This is the kind of inventory that [Minecraft](https://minecraft.net/) uses but there are a lot of other examples.

---

So when it comes down to it, that is a set of clear player experience goals with a number of different possible systems for achieving those goals.
The big question is - what inventory system is the best choice for Alluvial?
Which system will do the best job of achieving my player experience goals?
There are many ways to answer these kinds of questions.
You can apply past game design experience, or look at other games that have tried similar systems.
But the most approachable technique (at least from my perspective) is to prototype these systems and try them out.


There are also some concerns over practicality - specifically, what it would take to implement any of these systems.
The super strict inventory system would only work well if players were free to employ a wide variety of creative solutions.
This means implementing a robust physics system that can handle interactions between players and physical objects in a way that is not frustrating.

