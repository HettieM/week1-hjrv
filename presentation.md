# The A Team Agency presentation

![Mob](https://i.imgur.com/0AP4oMg.png)

![Desk](https://i.imgur.com/PaEkDON.png)

## Why, What, How


Creating a website for a web development digital agency. We took a mobile first, 8pt grid method approach to desiging the site.

We decided to be some sort of web development agency. We initially called it "Team 3", Vatsal quickly changed it to "THE A TEAM".

## Demo - here's our site and how it conforms to the brief

![Setch](https://i.imgur.com/TpvYXvz.jpg)


---

# What we learned

---

## Using automation in the project boards (R/J).

We created four lists:
- TODO
- In Progress
- Live Pull Requests
- Done

![automation](https://media0.giphy.com/media/1nR6fu93A17vWZbO9c/giphy.gif)

### Automation

Lists in the project board can be automated. The ... menu on each list has a "Manage Automation" item. These options allow you to move things between boards automatically depending on their status e.g. Move new issues to the "Todo" board, closed issues to the "Done" board etc. To get this to work it is vital that isses are assigned to the project, and not just team members, when they are created.

___

## Tab completion in git

Pretty much everything can be tab completed in git i.e. start typing something and then hitting tab will autocomplete it for you. This applies to branch names when checking out, --flags, files that have changed in git add etc. Try it!

---

## Effective issue management
Being clear with issue names and focusing on one at a time.

---

## Having a merge nightmare?
If your merge is going badly and you just want to start again you can use `git merge --abort` 

Make sure to close all you editor windows too.

---

## The difference between * and :root and html in css files (H)

In CSS the asterisk is known as the "Universal Selector". Adding properties using this selector will add them to every element. This can affect your load time and is often not what you want. Where possible it is better to rely on the cascade and add "global" properties to the body or html elements.

---

## IDs and classes - when to use which (J)
IDs are for use by HTML and Javascript (functionality), while classes are for use by CSS (styling).

E.g. when making a form:

``` html=40 
<form class="form">
    <label class="form form__label" for="userEmail">How we find your inbox:</label>
    <input type="email" name="email_address" id="userEmail">
</form>
```

Whilst you *can* style using ID tags, you should *avoid* this where possible - more 'specific' styling should be done using BEM.

``` var s = "JavaScript syntax highlighting";
.photo { }
.photo__image { }
.photo__caption { }
.photo__caption--highlighted { }
```

*NB Don't 'chain' children elements, e.g. ``photo__caption__author`` should just be written ``photo__author``.*

Using BEM for *more specific styling* is different from...

**Specificity**, which is a measure of (unwanted) style-trumping - higher specificity casuses problems, for example an element styled with a class might not behave as expected if its ID is also styled. **Never style using IDs**.

![specific](https://media3.giphy.com/media/iFy7dKuKMFclve5Abu/giphy.gif)

---

## Making corrections after pushing

### Request changes - maybe not?
Several times, after pushing our branches and creating a pull request, our reviewers found errors/issues. We initially thought we <em>had</em> to use github's request changes feature but it turns out that's not mandatory. As we were all sat around the same table, we found it was faster to just communicate the corrections verbally then add, commit and push again.

### Stashing
Often we had started work on another branch by the time we got the reviewers feedback. Rather than having to save our work to a temporary commit, or checking out the previous branch to a new folder to make the corrections you can use `git stash` to save your current working directory and index. You can then check out the previous branch, fix, commit and push it. Afterwards you can change back to your new branch and type `git stash pop` to return to where you were.

---

## Splitting up the work.

We didn't always do well at this. Sometimes the issues we logged weren't very granular and a lot of other issues were blocked while we waited for one team to finish them. This was a big issue at the start of the project where one team was building the site skeleton. We found out later that other teams mobbed this initial stage which was a more efficient way to get started.

![time](https://media3.giphy.com/media/l0MYOUI5XfRk4LLWM/giphy.gif)

[Hettie to review the above]


## We used A LOT of branches.
Initially this slowed us down a lot, but it's helped us all internalize the git workflow.

-- Assigned ourselves to too many issues at once (at beggining) but then learned and decided to assign ourselves to one issue at a time (for flexibility of people working on things). (V)

-- At first we often found ourselves waiting for our requests to be merged before we could proceed. This got better as we got faster at reviewing and merging. We instituted a project list for pull requests and naturally began prioritising each others requests.

---

# What we did well

## In our code review we got several lovely comments...

- "awesome profile photos" - Kin
- "Nav is great - able to tab easily between the different sections on the page" - Kat
- "Semantically great. not many divs used" - Lizzy
- "Great use of grid-template-layout for a responsive design" - Joe
- "Good job on pruning those branches once they're merged in" - Kin

``` css=1
.wrapper{
    display: grid;
    background-color: var(--background-colour);
    color: var(--nav-colour);
    grid-template-areas: 
    "nav"
    "title"
    "about-us"
    "bios"
    "reviews"
    "contact"
    "footer"
    ;
}

@media only screen and (min-width:700px) {
    
    .wrapper {
        display:grid;
        grid-template-areas: 
            "nav title"
            "nav about-us"
            "nav bios"
            "nav reviews"
            "nav contact"
            "footer footer"
        ;
        width:100%;
    }
}
```

## Pair programming challenges

- Our commits weren't very evenly spaced. Worked a lot on one computer (H)
- Accidentally paired off for majority of work on Thursday (H)
- Decided not to use one of the formal pair programming methods (Disadvantage: Often person typing doing a lot of the work and thinking, and the person not typing not having clearly defiend role/more passive). (V)

## Pair programming improvements

### Question? Is pair always better than individual?

When adding trivial features, doing trivial fixes or doing non-coding tasks we think working alone is okay.

### A new method? The co-driver!
One person researching (online), one person coding.

### Swapping pairs more often

Possible alternative: each person works on the same feature (or can be different), then the pair swaps computers and reviews each others code asking questions about each others code...and try to merge the best bits together in the pair. (v)

---

## Time management challenges

### Prioritising issues better 

-- Planning content and design fully on paper before starting to code. The spec we were working to was quite brief, it would have been useful if we had spent more time fleshing it out at the start.

-- Written time frames (by when we achieve what). (v)

--- Improvement: Make time for reflecting for a few minutes as a team. (v)

___

## Doing nice things for others

- What we did well:
-- making tea (V)
-- writing personal learning objectives (and what priority it is) in a HackMD
- Improvement ideas:
-- Everyone should state their main learning objective for the week at the start of the week.
-- Instead of thinking about only how can I achieve my learning objectives? Can think about how can I help other members of team achieve their priority learning objective?
-- Every hour or two think, what can I do for other team members that they would like/make them happy? 
-- Can I give my team mates a nice surprise in some way? (e.g. Jack's tea with suprise at end) (V)
-- Actually review user manuals! (V)

---

## Communication

- What we did well:
-- The chewing gum method (R)
![talking stick](https://media0.giphy.com/media/xT5LMQCAJQJR7GAoWQ/giphy.gif)
- Challenges:
-- Pressure to merge pull requests even if not properly reviewed (due to time constraints).
- Improvement ideas:
-- Using the sociocracy gestures more (instead of talking over each other) 
-- Using thumb temperature check more. (So that everyone's opinion is 'heard' on a matter). (Problem with this method.) (V)
-- Making time for reflecting together as a team (V)

___

## Finding Compromises

- Improvement ideas:
-- Methods of listening to each other?
-- Suggestion: 
[If strong alternative opinons within pair programming team about a feature] 
Then present/code alternative solutions amongst the pair  for the reviewers to give their objective opinion. (If the reviewers don't agree on which alternative is best then discuss as a team).

___

# THE END

Thanks for listening (for so long!)
