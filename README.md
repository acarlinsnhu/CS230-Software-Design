# CS 230 Software Design Portfolio

This repository contains my completed software design document for The Gaming Room's Draw It or Lose It application. The document covers the game's requirements, Java class structure, operating platform comparisons, and recommendations for moving the existing Android game to a browser.

## Project Reflection

### Briefly summarize The Gaming Room client and their software requirements.

The Gaming Room wanted to make Draw It or Lose It available beyond Android devices. The idea was to let people join through a browser without changing how the game itself worked. Players needed to participate in teams, share the same game session, and follow timed rounds where drawings are gradually revealed. Keeping game and team names unique was another requirement, since multiple games could be running at once.

### What did you do particularly well in developing this documentation?

I think the stronger part of my documentation was connecting the Java class design to what the game actually needed. The relationships between GameService, Game, Team, and Player were easier to explain once I considered how information would move through them. I also addressed some less obvious concerns, such as what happens when two players send requests at nearly the same time. Those details seemed worth including because they could cause problems even if the basic game functions correctly.

### What about the process of working through a design document did you find helpful when developing the code?

Having the domain model laid out made the purpose of each class clearer. It was easier to understand why GameService needed to manage the active games and why the other classes shared information through Entity. I could refer to those relationships instead of trying to work everything out while writing code. The document also helped separate what was already present in the Java prototype from the features that would still need to be developed.

### If you could choose one part of your work on these documents to revise, what would you pick? How would you improve it?

I would revisit the section dealing with interrupted connections. I recommended allowing players to reconnect without restarting their game, but the document could explain that process more thoroughly. For example, I would describe how the server identifies someone returning to a session and determines what game information needs to be restored. That would leave fewer unanswered questions for whoever eventually implements the feature.

### How did you interpret the user's needs and implement them into your software design? Why is it so important to consider the user's needs when designing?

Making the game accessible through a browser was only part of what the client needed. Someone playing on a phone should be able to participate in the same round as someone using a computer, and neither player should have a different timer or game state. That influenced my decision to recommend keeping the game logic and timing on the Java server rather than relying on each device. Considering how people actually use the application matters because something can function correctly from a programming standpoint and still be difficult or frustrating to play.

### How did you approach designing software? What techniques or strategies would you use in the future to analyze and design a similar software application?

My approach started with the existing Java prototype and what would need to change for browser access. I examined the class relationships before comparing operating platforms and deciding how the application should manage storage, memory, and communication. Ubuntu Server seemed like a reasonable choice since the game could continue using Java without needing separate applications for different devices. If I worked on another project like this, I would test more situations on paper before settling on the design. Things like a player disconnecting halfway through a round or two requests arriving together deserve attention before they turn into problems during development.
