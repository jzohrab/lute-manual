# Parent terms

Lute lets you define "Parent Terms", which is helpful for things like verb infinites, adjectives, etc.  For example, "to have" could be the parent term for "has".  This is useful because you only need to define things like root term meanings at the root level.

Here's the popup for a term with a parent term:

![image](https://user-images.githubusercontent.com/1637133/229640544-029d191c-053c-4316-9142-9baca523ab35.png)


# Setting an existing term as a parent

In the example below, you've already defined the term "have", and you're now creating a new term for "has".  In the "parent term" text box, if you type "ha", Lute then suggests the predefined term "have" as the parent:

![image](https://user-images.githubusercontent.com/1637133/229640120-4e367e18-07b5-4571-83a5-77f90e0c9919.png)

# Defining a term and a new parent

> Note the UI has changed slightly since this was written, but the idea is still the same.

In the example below, you're defining the term "dogs", and creating the parent term "dog" at the same time ("dog" wasn't defined previously):

![image](https://user-images.githubusercontent.com/1637133/229640878-92306b06-5121-42e0-bf3e-924ef3a2df42.png)

Here's the popup for the "dogs" term:

![image](https://user-images.githubusercontent.com/1637133/229641026-f71effa1-efc8-468a-9aab-29fffa10b420.png)

And for "dog":

![image](https://user-images.githubusercontent.com/1637133/229641104-d9d2fd2a-ff32-4b86-a365-d14884fdc565.png)

Note that the new parent term ("dog") gets the exact same information as the new term ("dogs"):

| term | details |
| --- | --- |
| dogs | ![image](https://user-images.githubusercontent.com/1637133/229641279-d9a619a2-cc93-4853-a211-adb78abd57d4.png) |
| dog | ![image](https://user-images.githubusercontent.com/1637133/229641457-426a3d65-efe1-42dd-83d7-eac42689b66c.png) |

While this might feel counter-intuitive, I've found that it provides the fastest input and term definition for Lute as I'm reading.  If I need, I can go back to the parent term later and clean things up.

# Click a Parent tag to edit the parent Term

When you click on a Term with parents, the parent tags are clickable, so you can quickly move to the parent Term.

For example, I've clicked on the term "existing" to show its form:

<img width="600" alt="image" src="https://github.com/jzohrab/lute/assets/1637133/e06db240-0ac1-40d4-9160-d79b909bf95c">

If I click on the parent tag "exist", the form moves to that Term:

<img width="754" alt="image" src="https://github.com/jzohrab/lute/assets/1637133/07fb9721-0ae6-4c03-8a5b-bfc5e0d0188a">

I can then edit and save that parent term normally.

# Multiple parents

Sometimes, a word might have multiple parents.  For example, in Czech, "hoře" is a declension of "hora", the regular form of "hoře", and a conjugation of "hořet".  In Spanish, "se sienta" could be a conjugation of "sentarse" or "sentirse".  Each parent is entered as a separate tag.  You can add multiple parents by typing them and hitting space or return.

# Bulk assigning parents

You can bulk assign terms to a *pre-defined* parent from the Terms screen (Home > Terms).  Below shows how it's done:

![image](https://user-images.githubusercontent.com/1637133/229642496-dd836882-4c6b-4f3a-90d2-7e254ef07ae7.png)

I had several terms which should be mapped to the *pre-defined* parent term "to have" (the infinitive).

## 1. Search for the terms you want

Filter for terms with the Search box in the top right.

In that box, I entered "^ha".  "^" is a special search character that says "the start of a word", so "^ha" means "show every term that starts with "ha".  If I had entered just "ha", terms such as "chat", "that", and "shorthair" would have been included.

## 2. Check the boxes next to the terms you want to assign

I clicked "has", "had", etc.

## 2. Set the parent

In the "Set parent" box, I typed "to" and Lute showed "to have".  When I click "go", those terms will be assigned to the parent:

![image](https://user-images.githubusercontent.com/1637133/229644031-7caf5b7b-001c-42d2-9a38-1d206c15b3d4.png)
