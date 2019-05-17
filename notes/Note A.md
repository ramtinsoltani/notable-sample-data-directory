---
title: Note A
created: '2019-05-17T11:28:20.240Z'
modified: '2019-05-17T11:53:13.410Z'
tags: [Notebooks/Some Notebook/Category A]
pinned: true
---

# Note A

Attempting to link to the Note B in the Category B of the same Notebook:

  1. Using `..` in the relative link: [Note B](@note/../Category B/Note B.md)
  2. Using semi-absolute link: [Note B](@note/Some Notebook/Category B/Note B.md)
  3. Using the normal (documented) link: [Note B](@note/Note B.md)

# Expectations

I'm expecting attempt #1 to work the way it is, attempt #2 to work but using a different syntax to mark the link as absolute (maybe `//`?), and attempt #3 to work and link to **Note B** in **Category A**.

# Current Behavior

Current behavior is the exact opposite of my expectations! Attempts #1 and #2 fail and result in the **Note not found** dialog, while the third attempt is working but linking to **Note B** in **Category B** (I created it before **Note A** in **Category A**.)

# Possible Solution

This is based on my understanding before facing this issue (I guess you can call it user instincts). All links to other notes should be relative, since `@note/Sibling.md` links to [Sibling Note](@note/Sibling.md). Therefore, `..` should refer to the parent directory/category/notebook where using it would allow navigating through the data directory to link to notes at any depths (not just forward.)

It would also be helpful to have the ability to use absolute links since having a complex nesting structure in the data directory could make it hard for the user to write relative links with many `..`s.

# Taking It Further

This might be an overkill, but defining aliases for paths could also solve the complex nesting structure problem. For instance, I can define an alias to the **Category B** as `CatB` which would make it easy to link to **Note B** inside **Category B** from any notebook or category at any depth using `@CatB/Note B.md` instead of `@note/../Category B/Note B.md` from this note.
