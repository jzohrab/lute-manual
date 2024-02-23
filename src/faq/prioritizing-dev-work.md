# How is development work prioritized?

_Variations on this:_
 
* where's the roadmap?
* what's the long-term plan?
* can you add feature X?
* why was feature Y added before feature Z?

These are all great questions, and at the moment there's really not a good answer in the normal "product" sense.

The goal is for Lute, or something a lot like it, to become a default viable tool for a large user base.  At the moment, the steps for getting there are not planned or roadmapped like a regular product would be: good planning takes a lot of time and energy.  Lute's free and open source, so I and others work on it as we can[^testing].

Lute's got a big backlog of issues and ideas.  You may be wondering why your small request has been sitting in the queue since like _forever_.  There are some criteria I use to pick what to work on:

* **Relative size of work:** how fast/easy it is to design, code, test, and document.  Sometimes small-seeming things aren't feasible.  E.g., "Couldn't you just query the database and tell me how many unknown words are in my book?"  No, unfortunately, because of the way that Lute stores data.  (It seems like it would be easy, right?  But it's not.)  Some requests are intertwined with others, or fundamentally don't follow Lute's technical design.  All good, but big changes take time.
* **User impact:** when I was coding just for me, this was easy.  But now with many users, I try to take that into account.
* **Fun and usefulness for me personally:** This keeps me motivated, and ensures that Lute doesn't have any obvious jankiness.
* **Code and architecture quality:** Since Lute should be open source and hackable, it should be clear.  Though I've tried to keep things sane, in some places it's tough.  So this kind of work (refactoring: improving the quality of existing code) is important.
* **Differentiators:** there are a few things that could make a big difference to learning.  With Lute, term images and parent terms were two of the initial things that drove me to write it in the first place.  I think that there are others as well: "word families", "sentence notes", and of course AI integration ... all of these might just be personal projects and thoughts though, I'm not sure!

Lute's open source, so anyone is welcome to make forks and tweak it for their own learning and fun.  But most of us want to just _get on with it_.

[^testing]: "Work on it as we can" sounds chaotic.  To counteract this chaos, Lute has a decent set of automated tests and checks to ensure that the code is viable.
