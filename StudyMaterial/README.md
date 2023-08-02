# IntroductoryProgramAltimetrik

## Table of Contents

1. [Git](#git)
2. [Basic commands](#basic-commands)
3. [Branches](#branches)
4. [Merging of branches](#merging-of-branches)
5. [Tags and Commits](#tags-and-commits)
6. [Stash command and Hooks](#stash-command-and-hooks)
7. [Git branching strategies and flows](#git-branching-strategies-and-flows)
8. [Git Merge vs Rebase vs Squash](#git-merge-vs-rebase-vs-squash)
9. [Agiles Methodologies and Scrum](#agiles-methodologies-and-scrum)
10. [JavaScript](#javascript)
11. [Syntax and Basic Constructs](#syntax-and-basic-constructs)
12. [HTML](#html)
13. [Meta-tags](#meta-tags)
14. [Input types](#input-types)
15. [Difference between HTML and XHTML](#difference-between-html-and-xhtml)
16. [Data-attributes](#data-attributes)
17. [Semantic HTML](#semantic-html)
18. [Accessibility](#accessibility)
19. [SEO](#seo)
20. [DOM](#dom)
21. [CSS](#css)
22. [Specificity](#specificity)
23. [Box Model](#box-model)
24. [Hoisting](#hoisting)
25. [Scope](#scope)
26. [Strict](#strict)
27. [Media Queries](#media-queries)
28. [Layouts: How to Make Them and Positioning in CSS](#layouts-how-to-make-them-and-positioning-in-css)
29. [Flexbox Layout & Grid Layout](#flexbox-layout--grid-layout)
30. [Bootstrap and Materialize CSS](#bootstrap-and-materialize-css)
31. [OOCSS | BEM | SMACSS](#oocss--bem--smacss)
32. [What are CSS Preprocessors | SASS](#what-are-css-preprocessors--sass)
33. [Fetch API | Ajax (XHR)](#fetch-api--ajax-xhr)
34. [HTTP Methods | Response Codes | Session Management](#http-methods--response-codes--session-management)
35. [HTTP 2.0 | 3.0](#http-20--30)
36. [Cookies, Local Storage & Session Storage](#cookies-local-storage--session-storage)
37. [CORS | JSONP](#cors--jsonp)
38. [JSON Web Token](#json-web-token)
39. [SSO | OAuth 2.0](#sso--oauth-20)
40. [Events | Event Bubbling](#events--event-bubbling)
41. [SOLID Principles](#solid-principles)
42. [OOP Concept](#oop-concept)
43. [Class | Inheritance | Prototype | Prototype Inheritance](#class--inheritance--prototype--prototype-inheritance)
44. [Encapsulation | Polymorphism](#encapsulation--polymorphism)
45. [Closures](#closures)
46. [OWASP and Top 10 Guidelines](#owasp-and-top-10-guidelines)
47. [DoS](#dos)
48. [XSS](#xss)
49. [Brute Force](#brute-force)
50. [Validation](#validation)
51. [MFA](#mfa)
52. [Prototype](#prototype)
53. [Promises](#promises)
54. [ES6+](#es6)
55. [Async Await](#async-await)
56. [Bibliography](#bibliography)

<!--What is git?-->

## Git

<em> What is git? </em>

Git is a version control system. What is "version control"? It is a system that records changes made to a project over time.

Imagine you are writing an essay in a Word document and you want to have a record of all the changes you make. Every time you make a major modification to the essay, instead of saving the file under a different name, such as "essay_v1.doc", "essay_v2.doc", and so on, you use Git.

With Git, you create a repository for your test...but What is a repository? A repository is like a secure repository where all the versions and changes you've made to your files are stored. So every time you make changes, Git saves a "snapshot" of the current state of the test. Let's say you made changes and saved a snapshot called "Rehearsal_v1".

After that, you can continue editing the test and make more changes. When you are satisfied with the new changes, Git will save the differences between the current version and the previous snapshot. This way, you can keep track of the changes without duplicating the entire file.

If at some point you want to go back and see what your test looked like in version "Test_v1", Git allows you to do that easily. Also, if you are working with other people on the test, Git allows you to merge the changes that each person makes, avoiding conflicts whenever possible.

<!--Most common commands -->

## Basic commands

Some basic Git commands are:

```
git init
git status
git add
git commit
git push
git pull
git log
```
Use `git init` to create a new Git repository in a directory. It's like telling Git that you're starting to track changes in that directory and you want to make it a Git repository.

Use `git status` when you want to know what is going on in your Git repository. It's like asking Git: "What has changed since the last time I checked out?" With this command, you can get information about the current state of your repository.

Use `git add` to add files. By running `git add`, you tell Git that you want to add changes to specific files so that they are ready to be saved. It's like putting those files in a special box called a "staging area" before saving them permanently.

Use `git commit` when you want to save your changes to the Git repository permanently. It's like taking a "snapshot" of your modifications and with a descriptive message, you save that version in your project history.

Use `git push` to push your local changes to a remote repository. It is useful for sharing your changes with other collaborators, collaborating on a project or backing up your work to an external server.

Use `git pull` when you want to get the latest changes from a remote repository and merge them with your local version of the project. It's like synchronizing your work with updates made by other contributors.

Use `git log` to view the history of commits in a Git repository. It provides a detailed list of commits made, including information such as author, date, commit message and a unique identifier.

<!--Branches and Merging of branches-->

## Branches

<em> What are branches? </em>

Branches are independent lines of development that allow you to work on different features or solutions in parallel. Each branch represents a different version of the repository, and changes made in one branch do not directly affect the other branches.

To create a new branch, use the command `git branch <branch name>`. For example, if you want to create a branch named "develop", run the following command:

```
git branch develop
```

This will create the new branch, but will not change your current location. You will still be in the same branch you are currently in.

To start working on the new branch, you must switch to it. You can use the `git checkout <branch name>` command to do this. For example, if you want to switch to the "develop" branch, run:

```
git checkout develop
```

You will now be in the new branch and will be able to start making changes and commits specific to that branch.

**It is a good practice to keep the main branch stable and create separate branches to work on new features. This facilitates team collaboration and tracking of changes in the repository.**

## Merging of branches 

<em> What does branch merging mean? </em>

Branch merging is the process of combining changes made in one branch with another. Merging is useful when you want to incorporate changes from a secondary branch into the main branch of the project.

<em> How do I make a branch merger? </em>

1. Make sure you are on the target branch: Before merging a branch, switch to the branch where you want to incorporate the changes. For example, if you want to merge the "develop" branch into the "main" branch, make sure you are on the "main" branch.

```
git checkout main
```

2. Start the merge process: Use the command `git merge <merge branch name>` to start the merge. For example, to merge the branch "develop" into the current branch, run the following command:

```
git merge develop
```

**No further action is required after Git has completed the merge without conflicts but what do I do if a conflict happens?**

Then we can continue with these steps :

3.  If Git finds conflicts during the merge, it will notify you and show you the affected files. You will need to open those files and manually resolve the conflicts. The conflicts are indicated by special markers in the files, and you will have to choose which changes to keep or merge.

Once you have resolved the conflicts, you must mark them as resolved by running `git add <filename>` for each file with conflicts.

4. Once you have resolved all conflicts, you can complete the merge by running the `git commit` command. Git will automatically create a commit message for the merge.

After the merge is complete, the changes from the merged branch will be incorporated into the target branch and will be available there.

It is important to note that it is advisable to merge branches in a stable state, which means that there should be no pending changes or errors in the target branch. In addition, it is a good practice to perform extensive testing after the merge to make sure that everything works correctly.

<!--Etiquetas y confirmaciones-->

## Tags and Commits 

Both tags and commits are essential elements in Git for change tracking and version control in a repository.

Tags are static pointers used to mark specific points in the repository history.

There are two main types of tags in Git:

Annotated Tags: Annotated tags contain additional information, such as the author's name, creation date, and a descriptive message. They are created using the command `git tag -a <tag name> -m "<message>" <commit identifier>`.

Lightweight Tags: Lightweight tags are simply names for a specific commit, with no additional information. They are created using the command `git tag <tag name> <commit identifier>`.

Commits are snapshots of changes made to a repository. Each commit represents a point in the repository's history and contains information about changes made, such as file additions, modifications or deletions.

Use the command `git commit -m "<commit message>"`. Be sure to replace `<commit message>` with a clear and concise description of the changes made in this commit.

<!--Comando stash y ganchos-->

## Stash command and Hooks

The "stash" command in Git allows you to temporarily save changes that are not yet ready to be committed.

When you run `git stash`, Git saves your modified files and staged changes in a hidden area, allowing you to revert your working directory to a clean state. You can then switch branches or perform other operations. Later, you can reapply the saved changes using `git stash apply` or `git stash pop`. However, there is an important difference between them:

git stash apply: This command applies the changes from the most recent stash without removing it from the stash stack. The changes are applied in your working directory and are reflected in your changed files and in the staged changes you had before you stashed.

```
git stash apply
```

git stash pop: This command also applies the changes from the most recent stash, but unlike git stash apply, it removes that stash from the stack after applying it. When you run this command, the changes are applied to your working directory and are reflected in your modified files and staged changes. In addition, the corresponding stash is removed from the stash stack.

```
git stash pop
```

<!--Git branching strategies and flows.-->

## Git branching strategies and flows.

<em> What are the branching strategies in git? </em>

Refer to the different approaches and workflows that teams and developers can use when working with Git repositories and managing branches.

The most commonly used Git branching strategies:

+ Feature branches: In this strategy, every time you work on a new feature or task, you create a separate branch in Git. This branch is like a copy of your project where you can make changes without affecting the main version. Once you finish working on the feature, you can merge it back to the main branch.

+ Gitflow: It uses two main branches called "master" and "develop". The "develop" branch is where the main development happens. When you work on a new feature, you create a feature branch from "develop". Once the feature is ready, you merge it back to develop. When everything in "develop" is tested and ready to be released, you create a "release" branch to do the last tests and bug fixes before merging it back to "master".

+ Trunk-based development: This strategy is based on maintaining a single main branch, called "master", which is always ready to be released. Instead of working on separate branches for a long time, changes are made directly on the master branch. This promotes continuous integration and requires a focus on automated testing and constant stability.

+ Forking flow: This strategy is commonly used in open source projects. Instead of working directly in the main repository, each developer makes an independent copy of the project called a "fork". Then, they create branches in their own fork to work on features or bug fixes. When they are done, they request to merge their changes to the main repository through a pull request.

<!--Git rebase and squash | merge vs rebase.-->

## Git Merge vs Rebase vs Squash

Choosing the right operation depends on your needs and preferences, as well as the workflow and structure of your project.

+ Git Merge: The merge operation in Git combines changes from two different branches. When merging one branch into another, Git creates a new commit that contains all the changes from both branches. The merge commit has two parents, one from each merged branch. This operation preserves the history of each branch and clearly shows where and how the merges were performed.

+ Git Rebase: Rebase is an operation that moves or reposts commits from one branch to another. Instead of merging branches, rebasing takes the changes from one branch and applies them on top of another branch, as if the changes had been made directly on that branch. This rewrites the commit history and gives the appearance that the changes were made sequentially on a single branch. Rebasing is useful for maintaining a clean, linear commit history, especially when working with feature branches or updating one branch with the most recent changes from another.

+ Git Squash: Squash is a technique that combines several commits into one. Instead of keeping all the individual commits, Git takes the changes from selected commits and joins them into a new commit. This is useful when you want to reduce the number of commits and have a more consistent and easier to understand change history. Squashing is especially useful before merging a feature branch into the main branch, to avoid a messy commit history.

<!--Agiles Methodologies | Scrum-->

## Agiles Methodologies and Scrum

Agile methodologies are project management approaches that focus on flexibility, adaptability and collaboration. These methodologies are based on principles and values that value early and continuous delivery of functional software, effective communication, customer collaboration, and responsiveness to change.

Scrum is one of the most popular and widely used agile methodologies. It focuses on the management and organization of software development teams, especially in complex environments with changing requirements. It is designed to facilitate the rapid and regular delivery of software increments, and is based on an iterative and incremental approach.

+ Roles: Scrum defines three main roles: the Product Owner, the Scrum Master and the Development Team. The Product Owner represents the interests of the customer and manages the product backlog. The Scrum Master ensures that Scrum principles and practices are followed and helps the team to be efficient. The Development Team is responsible for delivering work in product increments.

+ Sprints: Sprints are fixed-time iterations in which product development takes place. Typically, a sprint lasts from 1 to 4 weeks. During each sprint, the team selects a set of items from the product backlog and commits to deliver them by the end of the sprint.

+ Product backlog: The product backlog is a prioritized list of all desired features, requirements and enhancements for the product. It is managed by the Product Owner and is refined and adjusted as more information is obtained.

+ Scrum Meetings: Scrum establishes different meetings to facilitate collaboration and communication. Some of these meetings include sprint planning, daily standup, sprint review and sprint retrospective.

Scrum encourages transparency, inspection and continuous adaptation. It focuses on delivering value to the customer quickly and consistently, and allows for the incorporation of changes and feedback throughout the development process.

<!--JavaScript-->

## JavaScript

JavaScript is a high-level, interpreted programming language that allows you to add interactivity and dynamic behavior to web pages. Here are some of the basic syntax and constructs used in JavaScript:

## Syntax and Basic Constructs

1. Variables are containers for storing data. In JavaScript, variables can be declared using `var`, `let`, or `const`. `var` was used prior to ES6, while `let` and `const` were introduced in ES6 and have block scope.

Example:
```
let name = "Ariadna";
const age = 22;
```

2. Data Types: JavaScript is a dynamically typed programming language, which means you don't need to declare the data type of a variable. Basic data types include:

- `string`: `"Hello"`, `'World'`
- `number`: `42`, `3.14`
- `boolean`: `true`, `false`
- `null`: `null`
- `undefined`: `undefined`
- `object`: `{}` or `new Object()`
- `array`: `[]` or `new Array()`

Example:
```
let name = "Ariadna";
let age = 22;
let isAdult = true;
let numberList = [1, 2, 3, 4, 5];
```

3. Operators: JavaScript has a variety of operators for performing calculations and comparisons. Some common examples include:

- Arithmetic Operators: `+` (addition), `-` (subtraction), `*` (multiplication), `/` (division), `%` (modulo)
- Assignment Operators: `=` (assignment), `+=` (addition assignment), `-=` (subtraction assignment), `*=` (multiplication assignment), `/=` (division assignment)
- Comparison Operators: `==` (equality), `===` (strict equality), `!=` (inequality), `!==` (strict inequality), `>` (greater than), `<` (less than), `>=` (greater than or equal to), `<=` (less than or equal to)
- Logical Operators: `&&` (logical AND), `||` (logical OR), `!` (logical NOT)

Example:
```
let x = 5;
let y = 10;
let sum = x + y;
let isGreater = x > y;
```

4. Conditions: Are used to make decisions and control the flow of your program. 

- `if` statement: executes a block of code if a condition is true.
- `else if` statement: specifies a new condition if the previous condition is false.
- `else` statement: specifies a block of code to be executed if the condition is false.

Example:
```
let hour = 12;

if (hour < 12) {
    console.log("Good morning");
} else if (hour < 18) {
    console.log("Good afternoon");
} else {
    console.log("Good evening");
}
```

5. Functions: 
   - Declaring a function using the `function` keyword.
   - Parameters: placeholders for values passed into a function.
   - Return statement: specifies the value to be returned from the function.

Example:
```
function add(x, y) {
    return x + y;
}

//the add function is called with the values 9 and 5 as arguments

let result = add(9, 5);
console.log(result); // Output: 14
```

6. Loops:
   - `for` loop: iterates a block of code a fixed number of times.
   - `while` loop: iterates a block of code while a condition is true.
   - `do...while` loop: similar to `while` loop, but the block of code is executed at least once.

```
for (let i = 0; i < 5; i++) {
    console.log(i);
}

let i = 0;
while (i < 5) {
    console.log(i);
    i++;
}
```

7. Arrays:
   - Creating an array using square brackets `[]`.
   - Accessing elements using index (starting from 0).
   - Array methods: `push()`, `pop()`, `shift()`, `unshift()`, `slice()`, `splice()`, etc.

```
let fruits = ["apple", "banana", "orange"];
console.log(fruits[0]); // Output: "apple"
fruits.push("mango"); // Add an element to the end
fruits.pop(); // Remove the last element
```

## HTML

<em> What is html? </em>

HTML (HyperText Markup Language) is the language used to create web pages. Imagine you are building a house, HTML would be the language you use to define the structure and content of the house.

Instead of bricks and mortar, in HTML you use tags and elements. Tags are like instructions that tell the web browser how to display your page. For example, the `<h1>` tag is used to create a large heading, while the `<p>` tag is used to create a paragraph.

Each tag has an opening tag and a closing tag. The opening tag looks like this: `<tag>` and the closing tag looks like this: `</tag>`. Everything between the opening and closing tags is considered content and will be displayed on the web page.

In addition to the basic content, you can also add links, images, lists, and many other elements to your web page using special tags. For example, the `<a>` tag is used to create a link, the `<img>` tag is used to insert an image, and the `<ul>` tag creates an unordered list.

## Meta-tags

Meta-tags are special tags that are used in the HTML code of a web page to provide additional information about the content of that page. Imagine you are preparing a dish of food, the meta-tags would be like the ingredients and instructions you give to the chef.

These tags are placed in the head section of the HTML code and are not visible on the web page, but provide important information for search engines and other online services.

Meta Description: The meta description provides a brief, relevant summary of the page content. It is used by search engines to display a description in search results. In the example, the meta description indicates that the page contains delicious recipes to prepare at home.

```
<meta name="description" content="Discover delicious recipes to prepare at home and surprise your family and friends.">
```

Meta Title: The meta title defines the title of the page, which is displayed in the title bar of the browser and in search results. In this case, the page title is "Home Cooking Recipes."

```
<title>Home cooking recipes</title>.
```

Meta Keywords: Although nowadays keywords have less weight in search engines, they can still be used to indicate keywords related to the content of the page. In this example, some relevant keywords are mentioned, such as ``recipes'', ``home cooking'', ``dishes'' and ``food''.

```
<meta name="keywords" content="recipes, home cooking, dishes, food">
```

Meta Author:
The meta author allows you to indicate the name of the author or creator of the page. In this case, the author of the page is "John Smith".

```
<meta name="author" content="John Smith">
```

Meta Robots:
The meta robots tell search engines what to do with the page. In this example, they are told that the page should be indexed (included in search results) and that they should follow the links it contains.

```
<meta name="robots" content="index, follow">
```

Charset:
The charset defines the character encoding used on the page. UTF-8 is a common encoding that supports a wide range of characters, including international characters. It is important to set the charset correctly to ensure that characters are displayed correctly on the page.

```
<meta charset="UTF-8">
```

## Input types

Input types in HTML are attributes used to define the type of data expected to be entered into a form input field. They are like instructions to the browser on what type of information the user should expect when interacting with the form.

Text: This input type is used to enter simple text, such as a name or address. The user can type any text in the field.

```
<input type="text" name="name">
```

Number: This input type is used to enter numbers. The browser displays a numeric keypad on mobile devices and can add restrictions to accept only numbers.

```
<input type="number" name="age">
```

3. Email: This input type is used to enter a valid email address. The browser can perform some basic checks, such as making sure an "@" symbol is included.

```
<input type="email" name="mail">
```

4. Password: This input type is used to enter passwords. The entered text is displayed as asterisks or other hidden characters to protect the user's privacy.

```
<input type="password" name="password">
```

5. Checkbox: This input type allows you to select one or more options from a list of choices. It is useful for "yes" or "no" questions or for accepting terms and conditions. The value is sent if the box is checked.

```
<input type="checkbox" name="accept" value="1">
```

6. Radius: This input type allows you to select a single option from a list of options. Only one option can be selected from the group.

```
<input type="radio" name="gender" value="male"> Male
<input type="radio" name="sex" value="female"> Female
```

7. File: This type of entry allows a file to be selected for uploading from the user's device. It is useful to allow users to upload images, documents, etc.

```
<input type="file" name="file">
```

8. Date: This input type allows you to select a date using a drop-down calendar. The date format may vary depending on the browser.

```
<input type="date" name="date">
```

9. Time: This input type allows you to select a specific time using a digital clock. The time format may vary depending on the browser.

```
<input type="time" name="time">
```

10. URL: This input type is used to enter a valid URL, such as "https://www.ejemplo.com". The browser can perform some basic checks to make sure the URL is correctly formed.

```
<input type="url" name="sitio-web">
```

11. Range: This input type displays a slider bar that allows you to select a value within a specific range. In the example, the range is from 0 to 100, with increments of 1.

```
<input type="range" name="value" min="0" max="100" step="1">
```

12. Select: This input type creates a drop-down menu that allows you to select an option from a list. Cada opción se define dentro de las etiquetas `<option>`. El valor seleccionado se enviará cuando se envíe el formulario.

```
<select name="options">
  <option value="option1">Option 1</option>
  <option value="option2">Option 2</option>
  <option value="option3">Option 3</option>
</select>
```

## Difference between HTML and XHTML

HTML (HyperText Markup Language) and XHTML (Extensible HyperText Markup Language) are two different versions of the language used to create web pages. The main difference between HTML and XHTML is the way in which documents are written and interpreted.

HTML is more flexible and allows certain irregularities in the writing of the code, such as unclosed tags or malformed elements. This means that there can be some variations in how HTML code is written and still function correctly.

On the other hand, XHTML follows a stricter syntax and is based on XML. This means that all tags must be properly closed and nested, and documents must be well-formed. In XHTML, stricter rules must be followed in writing the code and any error can cause the document to not function correctly.

Syntax: The main difference between HTML and XHTML lies in their syntax. HTML has a more flexible syntax and allows certain irregularities, such as unclosed tags or malformed elements. XHTML, on the other hand, follows a stricter syntax and is based on XML, which means that all tags must be properly closed and nested, and documents must be well-formed.

Document structure: In HTML, it is common to find more relaxed document structures, where certain optional elements and attributes are omitted. En XHTML, se requiere una estructura más rigurosa y bien definida, incluyendo la declaración de tipo de documento (doctype) y el uso de etiquetas de cierre para todos los elementos.

XML compatibility: XHTML is a version of HTML that complies with XML rules, which means that it can also be interpreted by XML parsers. This facilitates the interoperability and processing of XHTML documents on different platforms and tools that support XML.

Typing rules: XHTML requires the use of strict typing rules, such as the use of lower case for tags and attributes, the use of double quotes for attribute values and the specification of all attributes with values. HTML is more permissive in terms of these typing rules.

## Data-attributes

Data attributes in HTML are custom attributes that begin with the word "data-". They allow additional information to be stored in HTML elements for use in JavaScript or CSS.

Suppose you have a list element `<li>` and you want to store an additional value associated with that element. You can use a data attribute to do it. For example:

```
<ul>
  <li data-id="1">Element 1</li>
  <li data-id="2">Element 2</li>
  <li data-id="3">Element 3</li>
</ul>
```

In this example, data attributes have been added to each list element (`<li>`) using the prefix "data-" followed by a meaningful name, in this case "id". The values ​​associated with those attributes can be customized to your needs.

Then, in your JavaScript code, you can access these data attributes to perform some action. For example, you can get the value of the "id" data attribute of a specific element:

```
var element = document.querySelector('li[data-id="2"]');
var id = element.dataset.id;
console. log(id); // Result: 2
```

In this case, we have selected the list item with the data attribute "data-id" equal to "2" using `document.querySelector()`. Next, we have used the `dataset` property to access the value of the "id" data attribute and store it in the `id` variable.

Data attributes allow you to store additional information in HTML elements in a custom way, giving you the flexibility to work with them in your JavaScript or CSS code. You can use them to store identifiers, specific settings or any other type of information relevant to your needs.

<!-- Accessibility | Semantic HTML-->
## Semantic HTML

Semantic in HTML refers to using appropriate elements and attributes to convey the meaning and structure of the content on a web page. By applying proper semantics, we achieve better understanding of the content for both search engines and users, and improve accessibility and code maintenance. 

**Basic HTML Structure with Semantic Best Practices:**
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Page Title</title>
</head>
<body>
    <header>
        <h1>Website Name</h1>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <section>
            <h2>Section 1</h2>
            <p>Content of section 1.</p>
        </section>
        
        <section>
            <h2>Section 2</h2>
            <p>Content of section 2.</p>
        </section>
    </main>
    
    <footer>
        <p>Copyright &copy; 2023. All rights reserved.</p>
    </footer>
</body>
</html>
```

1. `<!DOCTYPE html>`: This declaration defines that you are using HTML5, the latest version of the language.

2. `<html lang="en">`: The `lang` attribute specifies the primary language of the page. This helps search engines and assistive technologies understand the content in different languages.

3. `<head>`: Here, you include metadata and links to external files such as stylesheets and scripts.

4. `<meta charset="UTF-8">`: This meta tag specifies the character encoding of the page. UTF-8 is a widely compatible encoding that supports characters from different languages.

5. `<title>`: The page title displayed in the browser tab and is important for SEO and usability.

6. `<header>`: The `<header>` element is used to group the header or top section of the website, which may include the logo, site title, and navigation.

7. `<nav>`: The `<nav>` element is used to mark a main navigation section on the website.

8. `<main>`: The `<main>` element wraps the main content of the page. It should be used only once in the document structure.

9. `<section>`: The `<section>` element is used to group and separate content into thematic or related sections. Each section should have an `<h2>` or higher heading to indicate its title.

10. `<footer>`: The `<footer>` element is used to group the content of the footer. It can include contact information, additional links, and copyright.

**Best Practices :**

- Using appropriate HTML elements instead of generic elements (like `<div>`) provides a clear semantic structure that helps search engines understand and categorize the content.

- Heading elements (`<h1>` to `<h6>`) indicate the hierarchy and structure of the content. Search engines use this to determine the importance of headings, and users with visual impairments can easily navigate through them.

- Using elements like `<nav>`, `<header>`, `<section>`, `<footer>`, among others, provides a clearer and more understandable structure for users and facilitates navigation for users with disabilities.

- Providing alternative text for images using the `alt` attribute of `<img>` improves accessibility for visually impaired people
and allows search engines to understand the content of the images.

- Proper use of semantic tags makes it easier for developers to understand and maintain the code, which in turn improves code scalability and readability.

## Accessibility 

Accessibility refers to making websites usable for all people, including those with disabilities. Remember that accessibility is an ongoing process and it is important to consider the needs of all users when designing and developing a Web site.

1. Alternative Text for Images: Provide an alternative description for images using the `alt` attribute in the `<img>` tag. This allows visually impaired individuals to understand the content of images through screen readers. Example:

```
<img src="image.jpg" alt="A dog playing in the park">
```

2. Form Labels: Associate descriptive labels with input fields in a form. This helps visually impaired or cognitive impaired individuals understand what information to input. Example:

```
<label for="name">Name:</label>
<input type="text" id="name" name="name">
```

3. Color Contrast: Ensure there is sufficient contrast between text and background so that visually impaired individuals can read the content easily. Use color contrast tools or checkers to ensure compliance with accessibility guidelines. Example:

```
<p style="color: #000000; background-color: #FFFFFF;">This is an example of text with adequate contrast.</p>
```

4. Descriptive Links: Use descriptive text in links instead of simply saying "click here." This helps visually impaired individuals understand where the link is directing them. Example:

```
<a href="https://www.example.com">Visit our website</a>
```

5. Keyboard Accessibility: Ensure that all interactions and functions of your website can be accessed and used through the keyboard. This is important for individuals with motor disabilities who cannot use a mouse. Example:

```
<button type="button" onclick="myFunction()" onkeypress="myFunction()">Click here</button>
```

<!-- SEO | DOM -->
## SEO

SEO (Search Engine Optimization) refers to the set of practices and techniques used to improve the visibility and ranking of a website on search engines such as Google, Bing, and Yahoo. The goal of SEO is to increase the quantity and quality of organic (non-paid) traffic that a website receives.

SEO is based on how search engines function and how they analyze and rank websites. Search engines use algorithms to determine which websites are relevant and most useful for a specific search query. By optimizing a website for SEO, the aim is to meet the criteria that search engines consider important for ranking and displaying results.

There are different aspects of SEO that can be addressed to enhance a website's visibility:

1. On-page optimization: This involves optimizing elements within the website, such as content, meta tags, headings, URLs, and site structure. It entails strategic use of relevant keywords and ensuring that the content is high-quality and well-organized.

2. Off-page optimization: This focuses on external factors that influence a website's ranking, such as link building (obtaining high-quality backlinks from other websites) and social media presence.

3. User experience: An increasingly important factor in SEO is the user experience offered by a website. This includes aspects such as page loading speed, mobile-friendliness, intuitive navigation, and user-friendly design.

4. Keyword research: It is crucial to understand the keywords and phrases used by the target audience when searching for related information. This helps to guide content creation and optimization to make it relevant to search queries.

5. Tracking and analysis: It is essential to monitor the website's performance, use analytical tools like Google Analytics, and make continuous adjustments and improvements based on the data obtained.

The use of SEO is important because:

1. It increases visibility and online presence: Improved search engine ranking helps more people find and visit the website.

2. It generates high-quality organic traffic: By optimizing the website for relevant keywords, it attracts people who have a genuine interest in the products, services, or content offered.

3. It enhances credibility and trust: Users tend to trust websites that appear in the top search results, which can increase brand credibility.

4. It provides a higher return on investment: Organic traffic obtained through SEO does not require direct advertising payments, potentially resulting in a higher return on investment in the long run.

5. It improves the user experience: By optimizing factors like page loading speed and usability, a better user experience is offered, which can increase visitor satisfaction and loyalty.

## DOM

The DOM (Document Object Model) is a structured and hierarchical representation of an HTML, XML, or XHTML document. It is an interface that allows programs to dynamically access and manipulate the elements, attributes, and content of a document. The DOM organizes the document into a tree of nodes, where each node represents an element, attribute, or text of the document.

The DOM is important because it enables web developers to interact with the content of a page dynamically. By using the DOM, it is possible to programmatically modify, add, or remove elements and attributes from the document, making it easier to create interactive and dynamic web applications.

The DOM provides a set of methods and properties that allow developers to efficiently access and manipulate the elements of the document. Some common operations that can be performed with the DOM include modifying the content of an element, manipulating CSS classes, managing events, and creating new elements.

<!--CSS general knowledge | Specificity | Box Model-->
## CSS 

CSS (Cascading Style Sheets) is a style sheet language used to describe the presentation and appearance of a document written in HTML or XML. It controls the layout, style, and formatting of web pages, providing a way to separate content from visual presentation. CSS operates on the principle of cascading, where multiple styles can be applied to an element, with the final result determined by specificity and order.

CSS consists of selectors, properties, and values. Selectors target specific elements in an HTML document, properties define visual aspects, and values specify desired settings. CSS can be applied inline, internally within the HTML document, or externally as separate CSS files. Selectors include element, class, ID, attribute, pseudo-class, and pseudo-element, enabling precise targeting of elements or groups.

CSS offers various properties to control visuals like color, font, size, margin, padding, background, and more. These properties can be combined for unique styles and layouts. CSS3 introduced features such as animations, transitions, responsive design, Flexbox, and CSS Grid.

CSS frameworks like Bootstrap, Foundation, and Bulma provide pre-designed styles and components for efficient creation of responsive and visually appealing websites. Preprocessors like Sass and Less extend CSS with variables, functions, nesting, and more, requiring compilation into CSS before use.

CSS plays a vital role in web development, enhancing the aesthetics, user experience, and consistency across web pages. Understanding CSS allows developers to customize designs, create engaging layouts, and adapt to different screen sizes. It is an essential skill for front-end developers and crucial for building modern, visually appealing, and responsive websites.

## Specificity

Specificity in CSS refers to how conflicts are resolved when multiple styles are applied to the same element. It is an important concept to understand how the final style of an element is determined when there are overlapping style rules.

Specificity is based on a scoring system that assigns values to selectors used in the style rules. Each selector has a specificity value, and when there are multiple styles applied to an element, specificity is used to determine which one will take precedence.

The specificity scoring system consists of four parts:

1. Inline specificity: Inline styles have the highest specificity. They are applied directly to an element using the "style" attribute.

2. ID specificity: ID selectors have a high specificity value. They are represented by the "#" symbol followed by the ID name.

3. Class, attribute, and pseudoclass specificity: Class, attribute, and pseudoclass selectors have a medium specificity value. They are represented by the class, attribute, or pseudoclass name preceded by a dot (.) or square brackets ([]).

4. Element and pseudoelement specificity: Element and pseudoelement selectors have the lowest specificity. They are represented by the element name or pseudoelement name.

When conflicts occur, the principle is followed that the style with the highest specificity will take precedence over styles with lower specificity. In case of a tie, the style that appears later in the code will be applied.

It is important to understand and properly use specificity in CSS to avoid conflicts and ensure styles are applied as intended. By understanding how specificity is calculated, one can write style rules more precisely and predictably, avoiding unexpected surprises in the appearance of a website.

## Box Model

The Box Model is a fundamental concept in CSS that defines how elements are rendered and structured on a web page. It consists of four layers or components that make up the total space occupied by an element: content, padding, border, and margin.

1. Content: It represents the actual content of an element, such as text, images, or other media. The content area is determined by the width and height properties set for the element.

2. Padding: It is the space between the content and the border of an element. Padding can be added to all four sides of an element using the padding property. It helps create space around the content, improving readability and visual separation.

3. Border: It is a line that surrounds the padding and content of an element. The border can be customized in terms of color, style, and thickness using the border property. Borders provide visual boundaries and help distinguish one element from another.

4. Margin: It is the space between the border of an element and other elements around it. Margins create spacing between elements and can be set using the margin property. They are used to control the layout and positioning of elements on a page.

The Box Model allows for precise control over the size, spacing, and positioning of elements on a web page. By adjusting the values of content, padding, border, and margin, designers can create visually appealing and well-structured layouts.

Understanding the Box Model is crucial for properly positioning and aligning elements, ensuring consistent spacing, and creating responsive designs. It is important to consider the total space occupied by an element, including its content, padding, border, and margin, when planning the layout of a web page.

<!--Hoisting | Scope | strict-->
## Hoisting

Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their containing scope during the compilation phase. This means that regardless of where variables and functions are declared in the code, they are conceptually moved to the top of their scope and can be accessed before they are actually defined.

Hoisting applies to both variable declarations (using the var keyword) and function declarations. However, it's important to note that only the declarations are hoisted, not the initializations or assignments.

For example, consider the following code:

```
console.log(x); // Output: undefined
var x = 10;
```

In this case, even though the variable `x` is accessed before it is declared and initialized, it doesn't result in an error. This is because during hoisting, the variable declaration `var x` is moved to the top, making it available throughout the scope. However, at the point of the `console.log` statement, the variable `x` has not been assigned a value, so its value is `undefined`.

Similarly, function declarations are also hoisted. For example:

```
foo(); // Output: "Hello, hoisting!"

function foo() {
  console.log("Hello, hoisting!");
}
```

In this case, the function `foo` is declared after it is called, but hoisting moves the function declaration to the top, allowing it to be invoked before its actual declaration.

However, it's important to note that hoisting does not apply to variable assignments or function expressions. Only declarations are hoisted, not the initializations or assignments. So, it's good practice to declare variables at the top of their scope to avoid any confusion and make the code more readable.

## Scope

Scope in JavaScript and CSS refers to the visibility and accessibility of variables, functions, and styles in different parts of the code.

In JavaScript, scope is divided into global scope and local scope.

- Global scope encompasses the entire program, and variables and functions declared outside any function have global scope. These variables and functions are accessible from anywhere in the code.

- Local scope in JavaScript refers to variables and functions that are only visible within a specific code block, such as a function. These variables and functions have a limited scope and are only available within their local scope. This helps avoid name collisions and maintain better control over variables used in a specific context.

In CSS, scope is simpler and is based on the structure of the HTML document. CSS styles are applied to HTML elements following a descendant approach, where styles are inherited from parent elements to child elements.

- Scope in CSS is determined by the structure of the HTML document. Styles defined for an element apply to that element and all its descendants unless overridden by more specific styles.

- CSS also uses selectors to specify which elements will be affected by a particular style. Selectors can target specific elements such as classes, IDs, tags, or attributes, and styles will be applied only to those selected elements.

## Strict

The strict mode, also known as "use strict", is a feature in JavaScript introduced in ECMAScript 5 (ES5) that allows for writing safer code, eliminates ambiguous behaviors, and avoids certain common errors. By enabling strict mode, the JavaScript interpreter performs stricter interpretation of the code, applying stricter rules and generating errors in situations that were previously overlooked.

To enable strict mode, you need to add the following statement at the beginning of the JavaScript file or at the beginning of a function:

```
"use strict";
```

If you place this statement at the beginning of the file, it will apply to the entire file. If you place it at the beginning of a function, it will only apply to the scope of that function.

Strict mode introduces several features and behaviors:

1. Prevents the use of undeclared variables: In strict mode, all variables must be declared before they are used. Otherwise, an error will be generated.

2. Disallows the reassignment of read-only variables: In strict mode, it is not allowed to reassign values to variables that have been declared as constants or are part of read-only objects (e.g., properties of built-in objects like `Math` or `console`).

3. Prohibits the use of invalid octals: In strict mode, octal literals that start with a zero followed by digits (e.g., `0123`) are not valid and will generate an error.

4. Does not allow variable and function deletion: In strict mode, it is not allowed to delete variables and functions using the `delete` operator. This prevents potential issues and errors in the code.

5. Enforces the use of unique parameters in functions: In strict mode, it is not allowed to have multiple parameters with the same name in a function.

6. Prohibits the use of reserved words as variable names: In strict mode, using JavaScript reserved words (such as `eval`, `arguments`, or `implements`) as variable names or function arguments is not allowed.

Keep in mind that if you're using JavaScript modules (for example, in a Node.js environment or with ES6 modules), strict mode is automatically enabled in each module without needing to add the "use strict" declaration.

<!--Media Queries | em, rem, px-->
## Media Queries

Media Queries are used in CSS to apply specific styles based on the characteristics of the device or medium in which a web page is being viewed. This allows for the creation of responsive and adaptive designs that adjust to different screen sizes and devices.

Media Queries are primarily used when you want to apply different styles or layouts depending on device conditions such as screen width, orientation (landscape or portrait), pixel density, color capabilities, and more.

To use Media Queries, you use the `@media` rule in CSS, followed by a condition that determines when the styles will be applied. This condition is based on device characteristics and is defined using logical operators and unit values.

There are different units of measurement that can be used in Media Queries, such as em, rem, and px:

- **em**: The em unit is relative to the font size of the parent element. For example, `@media (min-width: 30em)` will apply the styles when the screen width is equal to or greater than 30 times the font size of the parent element.

- **rem**: The rem unit is similar to em but is based on the font size of the root element (typically the `<html>` element). For example, `@media (max-width: 40rem)` will apply the styles when the screen width is equal to or less than 40 times the font size of the root element.

- **px**: The px unit represents pixels and is an absolute unit. For example, `@media (min-width: 768px)` will apply the styles when the screen width is equal to or greater than 768 pixels.

Media Queries using different units of measurement:

```
/* Media Query using em */
@media (max-width: 30em) {
  /* Styles for screens with a width equal to or less than 30 times the font size of the parent element */
}

/* Media Query using rem */
@media (min-width: 40rem) {
  /* Styles for screens with a width equal to or greater than 40 times the font size of the root element */
}

/* Media Query using px */
@media (max-width: 768px) {
  /* Styles for screens with a width equal to or less than 768 pixels */
}
```

Remember that you can combine multiple conditions using logical operators like `and` and `or`, and you can also apply different styles for different device characteristics within a single Media Query.

```
@media (max-width: 600px) and (orientation: landscape) {
  /* Styles for screens with a maximum width of 600 pixels and landscape orientation */
  body {
    background-color: lightblue;
  }
}

@media (min-width: 768px) and (max-width: 1024px) {
  /* Styles for screens with a width between 768 and 1024 pixels */
  .container {
    width: 80%;
    margin: 0 auto;
  }
}

@media (min-width: 1200px) {
  /* Styles for screens with a minimum width of 1200 pixels */
  .container {
    width: 1000px;
    margin: 0 auto;
  }
}
```

In the first Media Query, the styles will be applied when the screen has a maximum width of 600 pixels and is in landscape orientation. The background color of the body element will be set to light blue.

In the second Media Query, the styles will be applied when the screen width is between 768 and 1024 pixels. The container element will have a width of 80% and be horizontally centered using margin.

In the third Media Query, the styles will be applied when the screen has a minimum width of 1200 pixels. The container element will have a fixed width of 1000 pixels and be horizontally centered using margin.

The choice of using units of measurement like em, rem, and px in Media Queries depends on the design requirements and desired user experience. em and rem units provide more flexibility and adaptability to fluid designs and variable font sizes, while the px unit allows for precise breakpoints based on exact pixel values.

It's important to consider browser and device compatibility when using Media Queries, as some features may not be supported by older browser versions. Additionally, it is recommended to adopt a responsive design approach from the start of a project to ensure an optimal experience across different devices.


## Layouts how to make them and positioning in css

1. Box Model:
The box model is fundamental in CSS and applies to all elements of a web page. Each HTML element is considered a rectangular box consisting of four main areas: content, padding, border, and margin. These areas are described with the following properties:

- Content: Represents the area where the actual content of the element is displayed, such as text, images, etc. You can control the size of the content using the `width` and `height` properties.

- Padding: It is the space between the content and the border. You can set the internal space of an element using the `padding-top`, `padding-right`, `padding-bottom`, and `padding-left` properties.

- Border: It is the line that surrounds the content and padding. You can specify the style, width, and color of the border using the `border` property.

- Margin: It is the space that surrounds the element and separates it from other adjacent elements. You can set the external space of an element using the `margin-top`, `margin-right`, `margin-bottom`, and `margin-left` properties.

The box model is used to control the structure and design of elements on a web page.

2. Flow Based Layout:
Flow-based layout is the default behavior of elements in a web page. Elements are placed in the order they appear in the HTML document flow, from top to bottom and left to right.

Block-level elements (e.g., `<div>`, `<p>`, `<h1>`) are placed one below the other, occupying the full available width. By default, their width is 100% of the parent container.

Inline elements (e.g., `<span>`, `<a>`, `<strong>`) are placed side by side on the same line until the available width ends, then they wrap to the next line.

In flow-based layout, you can control the design using properties like `display`, `float`, and `position`. I will now explain CSS positioning in detail.

3. CSS Positioning:
CSS positioning allows you to control the placement of elements on a web page. There are several values for the `position` property that can be used:

- `static`: This is the default value and follows the normal document flow.

- `relative`: Allows you to move an element relative to its original position. You can use the `top`, `right`, `bottom`, and `left` properties to specify the amount of offset.

- `absolute`: Positions an element precisely relative to its nearest positioned ancestor. If there is no positioned ancestor, it is positioned relative to the document.

- `fixed`: Positions an element fixed relative to the browser window, meaning it remains in the same position even when scrolling.

- `sticky`: Allows an element to behave as `relative` until it reaches a certain scroll position, at which point it becomes `fixed`.

In addition to the `position` property, there are other properties related to positioning, such as `z-index` (for controlling element stacking), `display` (for changing the behavior of an element), and `float` (for floating an element to the left or right of its container).

4. Grid Based Layout:
Grid-based layout is an advanced way of creating layouts in CSS using a grid structure with rows and columns. You define a container (e.g., a `<div>`) as a grid and place elements in different cells of the grid.

Properties to create a grid-based layout:

- `display: grid;`: Sets the container as a grid.

- `grid-template-columns`: Defines the width of columns in the grid.

- `grid-template-rows`: Defines the height of rows in the grid.

- `grid-gap` or `gap`: Specifies the space between grid cells.

- `grid-column` and `grid-row`: Control the placement of elements within the grid.

## Flexbox layout & Grid Layout

1. Flexbox Layout:
Flexbox is a CSS layout model designed to organize elements in a single direction, either horizontally or vertically. It is particularly useful for creating flexible and responsive layouts. 

- Flex Container: It is the element that wraps the child elements and establishes the flex context. It is defined using the `display` property with the value `flex` or `inline-flex`. All direct child elements of the flex container become flex items.

- Main and Cross Axes: In a flex container, a main axis and a cross axis are established. The main axis determines the direction in which flex items will be aligned, either horizontally (x-axis) or vertically (y-axis). The cross axis is perpendicular to the main axis.

- Flex Items: These are the direct child elements of the flex container. They can be controlled and organized using various flex properties such as `flex-grow`, `flex-shrink`, and `flex-basis`. These properties control the ability of flex items to grow, shrink, and their initial size.

- Alignment: Flexbox provides properties to align and distribute elements within the flex container. Some key properties include `justify-content`, which aligns items along the main axis, and `align-items`, which aligns items along the cross axis.

- Ordering: With Flexbox, you can change the visual order of flex items using the `order` property. This allows rearranging items without changing the order in the HTML.

Flexbox is ideal for simpler and one-dimensional layouts where flexibility in a single dimension (horizontal or vertical) is needed.

2. Grid Layout:
Grid Layout is another CSS layout model that allows creating two-dimensional layouts using rows and columns. It provides more precise and complex control over the positioning of elements compared to Flexbox. Aspects of Grid Layout:

- Grid Container: Similar to Flexbox, you need a container to create a grid. It is defined using the `display` property with the value `grid`. All direct child elements of the grid container become grid items.

- Rows and Columns: In Grid Layout, you can specify the number and size of rows and columns in the grid. You can use units of measurement such as pixels, percentages, or fractions to define the size of rows and columns.

- Item Positioning: You can place items in the grid using properties like `grid-row` and `grid-column`. These properties control which grid cells the items are placed in.

- Spacing and Alignment: Grid Layout provides properties to control spacing and alignment of items in the grid. You can use properties like `grid-gap` to set the spacing between cells, and properties like `justify-items` and `align-items` to align items within the cells.

Grid Layout is particularly useful for more complex and two-dimensional layouts where greater control over the positioning of elements in rows and columns is required.

## Bootstrap and Materialize CSS

Are both popular front-end CSS frameworks that provide a collection of pre-built CSS styles, componentes y plugins. While they share similarities in terms of functionality, they have some differences in terms of design principles and usage. Let's take a closer look at each framework:

Bootstrap:
Bootstrap is one of the most widely used CSS frameworks developed by Twitter. It offers a comprehensive set of components, such as navigation bars, buttons, forms, modals, and more. Bootstrap follows a mobile-first approach, meaning it focuses on designing responsive websites that look great on all devices. Key features of Bootstrap include:

1. Responsive Grid System: Bootstrap provides a flexible grid system that allows developers to create responsive layouts easily.

2. Extensive Component Library: It offers a wide range of ready-to-use components and utility classes, making it convenient to build web interfaces.

3. Customization Options: Bootstrap provides a customization option that allows developers to select and modify the components they need, creating a personalized design.

4. JavaScript Plugins: Bootstrap includes JavaScript plugins for various interactive components, such as carousels, tooltips, modals, and more.

Materialize CSS:
Materialize CSS is a modern CSS framework inspired by Google's Material Design language. It aims to provide a visually appealing and consistent user experience across different platforms and devices. Materialize CSS offers a robust set of components and features, including:

1. Material Design Styling: Materialize CSS adheres to the principles of Material Design, which focuses on clean, minimalistic, and visually engaging design elements.

2. Responsive Grid System: Similar to Bootstrap, Materialize CSS provides a responsive grid system for creating flexible layouts.

3. Rich UI Components: It offers a wide range of UI components such as cards, buttons, navigation bars, forms, and more, following the Material Design guidelines.

4. JavaScript Components: Materialize CSS comes with JavaScript components like parallax effects, sliders, modals, and dropdowns to enhance interactivity.

When choosing between Bootstrap and Materialize CSS, consider the design language you prefer (Bootstrap's versatile and customizable approach vs. Materialize CSS's adherence to Material Design), the specific components and features you require, and your familiarity with each framework.

## OOCSS | BEM | SMACSS

OOCSS, BEM, and SMACSS are all CSS methodologies or approaches that provide guidelines and best practices for organizing and structuring CSS code. They aim to improve code maintainability, reusability, and scalability. Let's explore each of them in detail:

1. OOCSS (Object-Oriented CSS):
OOCSS is a CSS methodology that encourages the separation of structure and skin. It promotes the creation of reusable, modular CSS classes that can be applied to different elements on a website. The key principles of OOCSS include:

- Separation of Structure and Skin: OOCSS advocates separating the visual styles (skin) from the structural patterns (structure) in CSS classes, allowing for greater flexibility and reusability.

- Reusable Modules: OOCSS emphasizes creating small, independent CSS modules that can be combined and applied to different elements throughout the website.

- Avoiding Overly Specific Styles: OOCSS discourages using overly specific selectors and encourages using classes that can be applied to multiple elements.

2. BEM (Block, Element, Modifier):
BEM is a CSS naming convention and methodology that provides a clear and consistent way of naming and organizing CSS classes. It helps create a modular and maintainable codebase. The key concepts of BEM are:

- Block: A stand-alone, self-contained component that represents a significant section of the page (e.g., a header, a navigation menu). It is represented by a unique CSS class.

- Element: A part of a block that has no standalone meaning. Elements are always tied to a specific block and are represented by a CSS class that combines the block class and the element name.

- Modifier: A class that represents a variation or state of a block or element. Modifiers are used to modify the appearance or behavior of blocks or elements and are indicated by appending a double underscore or double hyphen to the block or element class.

BEM provides a clear naming structure that improves code readability and reduces the chances of style conflicts.

3. SMACSS (Scalable and Modular Architecture for CSS):
SMACSS is a CSS methodology that focuses on providing a modular, scalable, and flexible architecture for organizing CSS styles. It emphasizes separating CSS rules into five distinct categories:

- Base: Defines the basic styles for elements (e.g., typography, color, etc.).

- Layout: Defines the overall layout and structure of the page (e.g., grids, containers, etc.).

- Module: Contains reusable, independent modules or components (e.g., navigation, sliders, etc.).

- State: Defines the styles for specific states or behaviors (e.g., active, hidden, etc.).

- Theme: Contains styles related to a specific visual theme or variation.

SMACSS encourages a more modular and component-based approach to CSS organization, making it easier to maintain and scale CSS codebases.

Each of these methodologies provides guidelines and best practices for writing structured and maintainable CSS code. The choice between OOCSS, BEM, and SMACSS depends on personal preference, team collaboration, project requirements, and the existing codebase. It's important to select a methodology that aligns with the specific needs and goals of your project.

## What are css preprocessors | SASS

CSS preprocessors, such as SASS (Syntactically Awesome Style Sheets), are tools that extend the capabilities of CSS by introducing additional features and functionalities. They enhance the efficiency and maintainability of CSS code by offering advanced features that are not natively available in regular CSS. Here's a detailed explanation of CSS preprocessors and SASS:

1. CSS Preprocessors:
CSS preprocessors are scripting languages that extend CSS and need to be compiled into standard CSS before being used in web pages. They introduce programming-like features and allow developers to write CSS code in a more efficient, modular, and reusable way. Preprocessors help simplify complex CSS tasks and provide a more structured approach to styling. They offer features such as variables, mixins, nesting, functions, conditionals, loops, and more.

The primary benefits of using CSS preprocessors include:

- Modularity: Preprocessors allow breaking down CSS code into smaller, reusable modules, making it easier to manage and maintain.

- Code Reusability: Preprocessors support the creation of mixins, which are reusable blocks of CSS code. Mixins can be included in multiple styles, reducing duplication and promoting consistency.

- Variables: Preprocessors allow the use of variables, which can hold values such as colors, font sizes, or other CSS properties. Variables enable easy and consistent updates across the entire stylesheet.

- Nesting: Preprocessors support nesting of selectors, which simplifies the code structure and improves readability.

- Functions and Operators: Preprocessors provide built-in functions and operators that can perform calculations, manipulate values, or generate dynamic styles.

2. SASS (Syntactically Awesome Style Sheets):
SASS is one of the most popular and widely used CSS preprocessors. It extends CSS syntax with additional features and provides a more powerful and efficient way of writing CSS. SASS offers two syntaxes:

- SASS (Indented Syntax): This syntax uses indentation instead of curly braces and semi-colons. It has a more concise and expressive syntax, but it requires indentation accuracy.

- SCSS (Sassy CSS): SCSS is a superset of CSS, meaning that all valid CSS code is also valid SCSS code. SCSS syntax uses curly braces and semi-colons, similar to regular CSS. It is more familiar to developers transitioning from regular CSS.

SASS provides several key features:

- Variables: SASS allows the use of variables to store and reuse values throughout the stylesheet, making it easier to manage consistent styles.

- Nesting: SASS allows nested selectors, reducing the need for repetitive parent selectors and improving code organization.

- Mixins: Mixins are reusable blocks of CSS code that can be included in multiple styles. They help reduce code duplication and promote modularization.

- Functions: SASS provides built-in functions and supports custom functions, allowing for dynamic calculations and manipulation of values.

- Control Directives: SASS offers control directives like `@if`, `@for`, and `@each`, which enable conditional statements, loops, and iterations.

- Import and Partials: SASS allows the use of `@import` to include other SASS or CSS files, helping organize styles across multiple files.

- Inheritance: SASS supports class inheritance using the `@extend` directive, which allows one class to inherit styles from another.

Once the SASS code is written, it needs to be compiled into regular CSS using a SASS compiler. The resulting CSS file can then be included in web pages.CSS preprocessors like SASS provide additional features, modularity, and code reusability to CSS. They enhance the efficiency and maintainability of stylesheets, offering benefits such as variables, mixins, nesting, functions, and more. SASS, in particular, is a popular preprocessor with powerful features and two syntax options (

SASS and SCSS) for writing CSS in a more flexible and efficient manner.

## Fetch API | Ajax (XHR)

1. Fetch API:
The Fetch API is a modern JavaScript tool that allows you to make requests to servers and retrieve data asynchronously. It provides an easier way to send and receive data from a server compared to older techniques like Ajax. Here's how it works:

- Promise-based: Fetch API uses promises, which are a way of handling asynchronous operations. Promises make it easier to work with asynchronous code and manage the data returned from the server.

- Simple syntax: Fetch API has a straightforward syntax. You specify the URL you want to request, and optionally, you can configure other parameters like the request method (GET, POST, etc.), headers, and data to send.

- Native JSON support: Fetch API automatically handles JSON responses and converts them into JavaScript objects, making it easier to work with JSON data.

- Error handling: Fetch API provides easy ways to handle errors that might occur during the request, such as invalid responses or network issues.

The Fetch API is widely supported in modern browsers and is considered a preferred choice for making HTTP requests in web applications.

2. Ajax (XHR):
Ajax stands for Asynchronous JavaScript and XML. It is a technique that allows you to send and retrieve data from a server without having to reload the entire web page. The key points about Ajax are:

- XMLHttpRequest object: Ajax uses the XMLHttpRequest (XHR) object, which is a JavaScript API. It enables making asynchronous HTTP requests to a server. You can send requests and receive responses without interrupting the user's interaction with the web page.

- DOM manipulation: Ajax enables updating specific parts of a web page without reloading the entire page. This provides a smoother user experience and avoids unnecessary disruptions.

- Events and callbacks: Ajax uses events and callbacks to handle the response received from the server. You can define functions to execute when a successful response is received or in case of an error.

- More complex syntax: Compared to the Fetch API, Ajax tends to have a more complex syntax and requires more code to make a request. You need to set various parameters, such as the request type, URL, headers, and callbacks.

- Wide compatibility: Ajax is compatible with a wide range of browsers, including older ones, making it a viable option for applications that require broader support.

Both the Fetch API and Ajax (XHR) are techniques used to make asynchronous requests in web applications. The Fetch API is more modern, easier to use, and based on promises, while Ajax uses the XMLHttpRequest object and has a slightly more complex syntax. 

## HTTP Methods | Response Codes | Session Management

HTTP, or Hypertext Transfer Protocol, is the baseline for communication on the World Wide Web. It is a set of rules that allows web browsers (such as Chrome or Firefox) and web servers (which host websites) to communicate with each other.

HTTP is a language that browsers and servers use to understand each other. When you type a website's URL into your browser and hit Enter, the browser sends an HTTP request to the server asking for the website's information. The server then responds with an HTTP response containing the requested information. This back-and-forth communication happens behind the scenes and enables you to view websites, submit forms, download files, and perform various online activities.

HTTP Methods:
HTTP methods define the actions that can be performed on a resource. Here's a detailed explanation of the most common methods:

1. GET: Used to request and retrieve information of a specific resource. The server responds by providing the representation of the requested resource.
2. POST: Used to send data to the server for processing. It's commonly used for submitting forms or sending data that will create a new resource on the server.
3. PUT: Used to completely update an existing resource. The client sends a complete representation of the resource to be updated.
4. DELETE: Used to delete a specific resource on the server.
5. PATCH: Used to perform a partial update of a resource. The client sends only the modifications to be made to the resource.
6. HEAD: Used to retrieve only the response headers of a resource without fetching its content.
7. OPTIONS: Used to obtain information about the server's capabilities, such as the supported HTTP methods by a particular resource.
8. TRACE: Used for diagnostic purposes. The server echoes back in the response exactly what it received in the request, allowing the client to see what modifications or additions were made along the way.
9. CONNECT: Used to establish a network connection with a remote server through a proxy.

HTTP Response Codes:
When a server receives an HTTP request, it returns a response code to indicate the status of the request. Here's a detailed explanation of some common response codes:

1. 200 OK: The request has been successfully processed, and the server returns the requested resource.
2. 201 Created: The request has been successfully completed, and a new resource has been created.
3. 204 No Content: The request has been successfully processed, but there is no content to return in the response.
4. 400 Bad Request: The request cannot be processed due to incorrect syntax or a client-side error.
5. 401 Unauthorized: Authentication is required to access the requested resource.
6. 403 Forbidden: The client does not have permission to access the requested resource.
7. 404 Not Found: The requested resource could not be found on the server.
8. 500 Internal Server Error: A generic server error has occurred, indicating an issue on the server side.

Session Management:
HTTP itself is stateless, meaning it doesn't maintain information about previous requests or user sessions. However, session management techniques are used to create and manage stateful interactions. Here are some common session management techniques:

1. Cookies: The server sends a small piece of data (cookie) to the client, which the client includes in subsequent requests to identify itself.
2. URL Rewriting: Session IDs are appended to URLs, allowing the server to associate requests with specific sessions.
3. Hidden Form Fields: Session IDs are stored in HTML forms as hidden fields and submitted along with the form data.
4. Session Tokens: Unique tokens are generated and issued to clients, which are then included in subsequent requests to establish and maintain sessions.
5. JSON Web Tokens (JWT): A token-based authentication mechanism that securely stores session information in a JSON format.

Session management techniques help track user sessions, maintain user-specific data, and enable personalized experiences on the web.

It's important to note that the security aspects of session management, such as preventing session hijacking or ensuring the confidentiality of session data, require additional considerations and practices to protect against potential vulnerabilities.

## HTTP 2.0 | 3.0

HTTP/2 (HTTP 2.0):
HTTP/2 is the upgraded version of the Hypertext Transfer Protocol, designed to improve performance and efficiency compared to its predecessor, HTTP/1.1.

1. Multiplexing: Multiplexing in HTTP/2 allows multiple requests and responses to be sent over a single TCP connection. In HTTP/1.1, each resource required a separate connection, leading to inefficiency and resource blocking. With multiplexing, multiple requests and responses can be sent in parallel over the same TCP connection, improving page load speed.

2. Header Compression: Headers in HTTP/2 are compressed to reduce their size before being sent to the server. This reduces bandwidth overhead and speeds up data transfer, especially on slow network connections.

3. Stream Prioritization: HTTP/2 allows prioritization of data streams, meaning that importance levels can be set for requests. This ensures that critical resources are downloaded first, enhancing the user experience when loading web pages.

4. Server Push: The server push functionality in HTTP/2 allows the server to send additional resources to the client without them explicitly requesting them. This is based on the server's anticipation that the client will need those resources. Server push can improve load speed by reducing the number of required requests.

HTTP/3 (HTTP 3.0):
HTTP/3 is the latest version of the Hypertext Transfer Protocol and is based on the QUIC (Quick UDP Internet Connections) protocol. It introduces additional improvements compared to HTTP/2.

1. UDP-Based Transport: HTTP/3 uses the QUIC protocol, which is based on UDP instead of TCP. UDP is a lighter and faster transport protocol than TCP. By utilizing UDP, HTTP/3 improves latency and data transfer speed.

2. Integrated Multiplexing and Encryption: HTTP/3 incorporates multiplexing and encryption directly into the protocol, unlike HTTP/2 which uses an additional layer called Transport Layer Security (TLS) for encryption. The integration of multiplexing and encryption in HTTP/3 simplifies and speeds up web communications.

3. Improved Error Recovery: HTTP/3 implements a more efficient error recovery mechanism. It employs techniques such as fast retransmit and packet loss handling to ensure reliable data transfer even in unstable networks or with packet loss.

HTTP/2 and HTTP/3 are enhanced versions of the Hypertext Transfer Protocol. HTTP/2 focuses on improving TCP connection efficiency, while HTTP/3 leverages the UDP-based QUIC protocol to achieve higher speed, performance, and security in web communications.

## Cookies, Local Storage & Session Storage

1. Cookies:
Cookies are small pieces of data that websites store on a user's device. They are typically used for session management, personalization, and tracking. Key points about cookies:

- Size and Expiration: Cookies can store a limited amount of data, usually up to 4KB. They have an expiration date, which can be set by the server. Cookies can be persistent, remaining on the user's device even after the browser is closed, or session-based, expiring when the browser session ends.
- Client-Server Communication: Cookies are sent back and forth between the client (browser) and the server with each request and response. This allows the server to recognize and identify the user across multiple requests.
- Accessibility: Cookies can be accessed and modified both by client-side JavaScript and server-side code. This makes them useful for maintaining user sessions, remembering user preferences, and tracking user behavior.

It's important to note that cookies have some limitations. They are vulnerable to security risks, such as cross-site scripting (XSS) and cross-site request forgery (CSRF) attacks. Additionally, the limited storage size can be a constraint for storing large amounts of data.

2. Local Storage:
Local Storage is a web browser feature that allows websites to store larger amounts of data on the client's device. Main characteristics of Local Storage:

- Storage Capacity: Local Storage provides a significantly larger storage capacity compared to cookies. Typically, websites can store up to 5MB or more of data.
- Persistence: Unlike session-based cookies, Local Storage data remains on the user's device even after closing the browser. It is persistent and can be accessed across browser sessions.
- Scope: Local Storage is specific to each domain and is isolated from other websites. Data stored in Local Storage for one website cannot be accessed by another website.

Local Storage is primarily used for client-side data storage, such as caching user preferences, offline data, or temporary data that doesn't need to be transmitted to the server with each request.

3. Session Storage:
Session Storage is similar to Local Storage in terms of capabilities but has a different scope and lifespan. What I need to know about Session Storage?:

- Storage Capacity and Persistence: Session Storage provides a storage capacity similar to Local Storage (around 5MB or more), but it is temporary. The data stored in Session Storage is tied to a specific browsing session and is cleared when the session ends (e.g., when the browser is closed).
- Scope: Like Local Storage, Session Storage is isolated to each domain. It cannot be accessed by other websites.
- Use Cases: Session Storage is commonly used to store temporary session-related data that needs to be accessible across multiple pages within a browsing session.

Session Storage is useful for maintaining stateful data within a user's browsing session, such as storing form data before submission or preserving user interactions within a website.

Cookies, Local Storage, and Session Storage are different mechanisms for storing data on the client-side. Cookies are primarily used for session management and tracking, with limited storage capacity. Local Storage offers a larger storage capacity and persistent storage, while Session Storage provides temporary storage for a browsing session. The choice between these storage options depends on the specific requirements and use cases of a web application.

## CORS | JSONP

CORS is a security feature implemented in web browsers to protect websites from malicious requests and ensure safe data exchange between different web domains (origins). When a web page from one domain (origin) tries to access resources (like data or APIs) hosted on another domain, the browser enforces CORS to check if the other domain allows such access. If the domains are different and CORS is not properly configured on the server, the browser will block the request to protect the user's data and security.

In simple terms, CORS helps in making web applications secure by allowing or blocking cross-origin requests based on the server's configuration.

JSONP is an old way to get data from another website (domain) when the browser doesn't allow normal requests between different domains due to security reasons.

Imagine that you are on a web page hosted on domain "A", and you want to get data from a server on domain "B". This is normally not possible due to browser security measures to protect users.

But with JSONP, you can do it like this:

1. **Special Request:** When you want to get data from "B", you create a special request through a script element in your page's HTML.

2. **Function Name:** In the request, you include the name of a function that you want to be executed when the data is ready.

3. **Server Response:** The server in domain "B" receives your request and sends the data wrapped inside that function you specified.

4. **Auto Execution:** When the data arrives on your page as some kind of "script", the browser executes it automatically, and the function you provided is activated, allowing you to access the data.

It's like asking someone from another place to call you on the phone with the information you need. They call you and tell you what you want to know.

JSONP and CORS are different techniques for allowing web pages to access data on domains (websites) other than the site itself. Both methods allow requests for resources across domain boundaries, but have significant differences in performance and security.

Comparison between JSONP and CORS:

1. **JSONP (JSON with Padding):**
    - It's an older technique.
    - Requires the external domain server to wrap the data in a specific function requested by the client page.
    - Execute the JavaScript code of the response directly on the client page.
    - It can be less secure, since if the external server does not properly validate the data, it could expose itself to Cross-Site Scripting (XSS) vulnerabilities.
    - Only supports GET requests.
    - Does not provide advanced security and configuration controls, which could lead to security issues.

2. **CORS (Cross-Origin Resource Sharing):**
    - It is a more modern and safe technique.
    - Allows the external server to explicitly define which domains are allowed to make requests.
    - Allows more flexible requests (GET, POST, etc.).
    - Provides advanced security and configuration controls to handle requests more securely.
    - The browser imposes stricter restrictions on what data can be accessed and how it can be accessed, which improves information security.

In general, CORS is the recommended solution for handling cross-domain requests in modern web development. It provides a more secure and flexible mechanism to allow websites to interact with resources from other domains, while protecting user security and data integrity. JSONP, while useful in the past, has become less common due to its limitations and security concerns. Therefore, CORS is preferable in most cases.

## JSON Web Token.

JWT is like a key card. Just like a physical access card allows you to enter restricted areas in a building or business, a JWT allows you to access protected areas in a web application or online service in a secure manner.

1. **What is a JWT?** A JSON Web Token (JWT) is an object that contains important information about a user or an entity. It is encrypted in a secure and compact format.

2. **How does it work?** When a user logs into an application, the server creates a JWT and delivers it to the user. The user stores this JWT, usually in local storage or in a cookie.

3. **What does the JWT contain?** The JWT contains information in the form of "claims". These claims are like "tags" that describe the user or indicate what they can do. For example, it can contain the user ID or the token expiration time.

4. **Secure access:** When the user wants to access protected areas of the application, he presents his JWT. The server checks the signature of the JWT and the claims to make sure that it is valid and that the user has the necessary permissions.

5. **Expiration Time:** The JWT usually has an expiration time, after which it will become invalid. This ensures that the user cannot use the JWT indefinitely.

6. **Security:** JWTs are secure because they are digitally signed by the server. This ensures that no one can alter the content of the JWT without being detected.

7. **Advantages:** JWTs are very useful in microservice architectures and distributed applications, since they do not require user state storage on the server, which makes them scalable and efficient.

In short, a JSON Web Token (JWT) is a secure mechanism for authenticating and authorizing users in web applications. It works like a key card, providing information and permissions to users to access protected areas of the application. With JWT, the need to store session information on the server is avoided, making it an efficient and secure solution for many applications.

## SSO | OAuth 2.0

Single Sign-On (SSO) is a method that allows users to log in once and access multiple applications without needing to authenticate again.

1. **Single Sign-On (SSO):**
   - Imagine that SSO is like having a single master key for many doors.
   - With SSO, you can log in once to a system or website and then access multiple systems or applications without having to re-enter your credentials.
   - It's like when you sign in to a Google or Facebook account, and then you can access different apps or services without having to sign in again.
   - SSO improves user convenience and experience by eliminating the need to remember multiple passwords.

OAuth 2.0 is an authorization protocol that allows third-party applications to access authorized resources in user accounts without sharing full credentials. This improves security, convenience and the user experience when using online applications and services in a secure and controlled manner.

2. **OAuth 2.0:**
   - Now OAuth 2.0 as a secure way to share your master key with others without directly revealing it.
   - With OAuth 2.0, you can allow third-party applications or services to access certain information or perform actions on your behalf, without sharing your password with them.
   - It's like giving temporary and controlled access to an app, like allowing an app to post to your social media account without giving you your password.
   - OAuth 2.0 ensures security and protects your personal credentials by only granting limited access to authorized applications.

## Events | Event bubbling.

In web development, events are actions that happen in a web page (e.g., a button click or mouse movement).

Event Bubbling is a behavior where an event triggered on a child element will "bubble up" and trigger the same event on its parent elements. It continues to propagate up the DOM hierarchy until it reaches the root element. This allows you to handle events at different levels in the DOM tree.

Event Bubbling works like layers or levels in the Document Object Model (DOM). When you click on an element, the event starts at that element and then bubbles up through its parent elements, one layer at a time, until it reaches the top-level ancestor in the DOM hierarchy.

Imagine the DOM as a stack of elements, where each element is like a layer on top of another. When you click on an element, the event first triggers the event listener on that element, which is the top layer. Afterward, the event travels up the stack, triggering the event listeners on each successive layer, one by one, until it reaches the bottom layer (the root element or the browser window).

This bubbling-up behavior allows you to handle events at different levels of the DOM without needing to attach separate event listeners to each individual element. Instead, you can attach event listeners to common ancestor elements and capture events from their descendants as well.

For example, if you have a list of items, and you want to handle clicks on any list item, you can add the event listener to the parent element that contains all the list items. When you click on a specific list item, the event will bubble up from the clicked item to the parent container, triggering the event listener you attached.

This concept of "bubbling up" is why it's called Event Bubbling. It's a fundamental part of how event handling works in the browser's DOM and is essential to understand when developing web applications.

HTML:
```html
<div id="outer-container">
  <div id="middle-container">
    <div id="inner-container">Click me!</div>
  </div>
</div>
```

JavaScript:
```javascript
document.getElementById("inner-container").addEventListener("click", function() {
  console.log("You clicked on the inner container");
});
```

When you click on the text "Click me!", you'll see in the browser console:
```
You clicked on the inner container
```

But if you add event listeners to the "middle-container" and "outer-container" as well:

```javascript
document.getElementById("middle-container").addEventListener("click", function() {
  console.log("You clicked on the middle container");
});

document.getElementById("outer-container").addEventListener("click", function() {
  console.log("You clicked on the outer container");
});
```

Now, when you click on the text "Click me!", you'll see in the browser console:

```
You clicked on the inner container
You clicked on the middle container
You clicked on the outer container
```

## SOLID Principles

SOLID is an acronym representing five essential design principles for writing maintainable and scalable software. These principles are:

Single Responsibility Principle (SRP): Each class should have only one reason to change.
Open/Closed Principle (OCP): Classes should be open for extension but closed for modification.
Liskov Substitution Principle (LSP): Subtypes must be substitutable for their base types.
Interface Segregation Principle (ISP): Clients should not be forced to depend on interfaces they do not use.
Dependency Inversion Principle (DIP): High-level modules should not depend on low-level modules. Both should depend on abstractions.

## OOP Concept

Object Oriented Programming (OOP) is a way of writing code in which we organize our program as if it were a set of objects that interact with each other. Think of an object as a "model" or "template" that describes something in real life.

Here are some key OOP concepts:

1. **Class:**
    - A class is like a template or blueprint for creating objects. It defines the characteristics (attributes) and behaviors (methods) that objects based on that class will have.

2. **Object:**
    - An object is a specific instance of a class, created from the template.
    - For example, if you have a class "Dog", an object would be a particular dog with its characteristics and behaviors.

3. **Attributes:**
    - Attributes are the characteristics or properties of an object.
    - For example, in the class "Dog", the attributes could be "name", "age" and "breed".

4. **Methods:**
    - Methods are the actions or behaviors that objects can perform.
    - For example, in the "Dog" class, the methods could be "bark", "run" and "sleep".

5. **Encapsulation:**
    - It is the concept of keeping the attributes and methods of a class protected and hidden, avoiding direct access from outside the class.
    - This is done to maintain data integrity and ensure that only the methods of the class can modify the attributes.

6. **Inheritance:**
    - Inheritance is a mechanism that allows you to create new classes based on existing classes, inheriting their attributes and methods.
    - It's like creating a new more specific template based on a general template.

7. **Polymorphism:**
    - Polymorphism allows different objects to respond to the same method in different ways.
    - For example, in an "Animal" class, the "move" methods can be implemented differently for different types of animals, such as "dog" and "cat".

In short, Object Oriented Programming (OOP) is an approach that organizes code around objects with specific attributes and behaviors. Classes are like templates for creating objects, and code is structured in a way that is easy to understand and maintain. OOP allows you to create more flexible, reusable, and maintainable programs, making it one of the most popular techniques in software development.

## Class | Inheritance | Prototype | Prototype Inheritance.

1. **Class:**
    - A class is like a blueprint or template for creating objects.
    - It is like a model that defines the characteristics and behaviors that the objects created from it will have.
    - For example, if we have a class "Car", we can create multiple car objects with attributes like "color", "make" and methods like "start" and "stop".

2. **Inheritance:**
    - Inheritance is like creating a new class based on another existing class (parent).
    - The new class (child) automatically inherits the attributes and methods of the parent class.
    - This allows you to reuse code and create more specific classes based on a more general class.
    - For example, if we have a class "Animal" and another class "Dog", the class "Dog" would inherit the characteristics of the class "Animal", such as "move" and "eat".

3. **Prototype:**
    - The prototype is like a hidden template that every object in JavaScript has implicitly.
    - When we create an object in JavaScript, it is based on a prototype that defines its properties and methods.
    - This allows us to add properties or methods to all objects of a class without directly modifying the class definition.

4. **Prototype Inheritance:**
    - It is a concept in JavaScript where an object can inherit the properties and methods of another object.
    - When searching for a property or method on an object, if it is not found, JavaScript will search its prototype and its prototype's prototype until it is found (prototype chain).
    - This allows you to create JavaScript objects that share characteristics and behaviors of other objects, forming a chain of inheritance.

So a "Class" is a template for creating objects with specific characteristics and behaviors. "Inheritance" allows you to create new classes based on existing classes to reuse code. "Prototype" is a hidden template for every object in JavaScript that defines its properties and methods. "Prototype Inheritance" is a way in JavaScript of allowing objects to inherit characteristics and behaviors from other objects through a prototype chain.

## Encapsulation | Polymorphism.

1. **Encapsulation:**
    - Encapsulation is like keeping your important things in a locked box.
    - In programming, it is the concept of protecting the data and behavior of an object within a class.
    - The attributes (data) and methods (behavior) of the class are hidden and can only be accessed and modified by the methods of the class itself.
    - This prevents external code from directly accessing the data, ensuring that it is kept in a valid and consistent state.

2. **Polymorphism:**
    - Polymorphism is like having a switch that can turn on different devices.
    - In programming, it is the ability of different objects to respond to the same action in different ways.
    - For example, in an "Animal" class, the "sound" method can be implemented differently for "dog", "cat" and "bird".
    - The code that uses the objects doesn't need to worry about what kind of animal it is, since it can call the "sound" method on all of them and it will get the appropriate result for each case.

Encapsulation is like protecting data and behavior inside a secure box, preventing unauthorized access from the outside. Polymorphism is like having a switch that can work in different ways depending on the object it's applied to. Both concepts are fundamental in Object Oriented Programming and help to create more organized, secure and flexible code.

## Closures.

A closure is like a bubble that captures and stores special information within a function in JavaScript.

Imagine you have a function that creates a bubble around it. This bubble retains special memories, such as variables or references to other functions, even after the original function has finished executing.

Here are some key points about closures:

1. **Capturing Special Data:** When a function is executed, it can create a closure if there is another function defined inside it.

2. **Saving Data:** The closure retains the local data of the enclosing function, even after the function has finished executing.

3. **Private Access:** The data inside the closure is not directly available from outside the function. This makes them private and protected.

4. **Functions Inside Functions:** If you have a function inside another function, the inner function can access the outer function's closure data.

5. **Practical Use:** Closures are useful for holding state, creating specialized functions, and avoiding name conflicts in JavaScript.

A closure in JavaScript allows the inner function to access and use that data, even after the outer function has finished executing. Closures are powerful tools that make JavaScript flexible and versatile for writing more advanced code.

## OWASP and top 10 guidelines.

**OWASP (Open Web Application Security Project):**
OWASP is a non-profit organization focused on improving the security of web applications and software. It provides information and resources to help developers and security professionals identify and mitigate vulnerabilities in web applications.

**OWASP Top 10:**
The OWASP Top 10 is a list that identifies the 10 most critical security vulnerabilities in web applications. These vulnerabilities are widely known and pose significant security risks if not properly addressed. The list is updated periodically to reflect new threats and security trends.

Top 10 guidelines:

1. **Injection:** Occurs when untrusted data is inserted into commands or queries executed in a system, allowing attackers to manipulate or access unauthorized data.

2. **Broken Authentication:** Happens when weaknesses in authentication and access control implementation allow attackers to compromise user accounts.

3. **Sensitive Data Exposure:** Involves storing or transmitting sensitive data, such as passwords or personal information, without adequate protection.

4. **XML External Entity (XXE):** A vulnerability that allows attackers to read files and perform attacks on the server through malicious XML.

5. **Broken Access Control:** Occurs when access controls are not properly implemented, allowing attackers to access unauthorized functions or data.

6. **Security Misconfiguration:** Happens when server, platform, or application configuration is not adequately protected, enabling attackers to find valuable information to compromise the system.

7. **Cross-Site Scripting (XSS):** Refers to the inclusion of malicious scripts in web pages, allowing attackers to steal data or take control of a user's browser.

8. **Insecure Deserialization:** A vulnerability that allows attackers to manipulate data during deserialization, potentially leading to unauthorized code execution.

9. **Insufficient Logging & Monitoring:** Occurs when an application fails to log important events or does not monitor malicious activity, making it difficult to detect and respond to attacks.

10. **Insecure Direct Object References:** Happens when resource identifiers, such as URLs or keys, are not properly validated, enabling unauthorized access to data or functions.

OWASP and the Top 10 guidelines are valuable resources for identifying and mitigating vulnerabilities in web applications. By following these guidelines, developers can significantly improve the security of their applications and protect users from potential security breaches and attacks.

## DoS

A DoS attack is like blocking the entrance of a store with too many people, preventing legitimate customers from entering and making purchases.

In more technical terms:

1. **What is a DoS Attack?** A DoS attack is a malicious attempt to overload or overwhelm a website or online service by sending a large number of requests from multiple sources.

2. **Attack Objective:** The goal of the attack is to make the website or service inaccessible to legitimate users by exhausting its resources, such as bandwidth, memory, or processing power.

3. **Practical Example:** Imagine a website as a store with a single entrance. If a crowd of people blocks the entrance, no one else can enter, and the business comes to a standstill.

4. **How It Works:** Attackers use multiple compromised computers or devices to continuously send requests to the target website. This overwhelms the servers and prevents them from serving real users.

5. **Potential Damages:** A DoS attack can cause service disruptions, loss of revenue, damage the company's reputation, and impact user experience.

6. **Different from DDoS:** DoS involves an attacker sending requests from a single source, while DDoS (Distributed Denial of Service) involves multiple sources attacking simultaneously.

7. **Prevention and Mitigation:** Website owners need to implement security measures to detect and block such attacks, such as using firewalls, request rate limiting, and DDoS mitigation systems.

A DoS attack is like blocking the entrance of a website with a crowd of requests, preventing legitimate users from accessing the service. It is a type of cyber attack that aims to overwhelm and paralyze a website, which can have serious consequences for the affected business or service.

## XSS

Cross-Site Scripting (XSS) is like a hidden malicious message on a web page that tricks users.

Imagine you visit a seemingly harmless web page. However, behind the scenes, an attacker has inserted malicious code into that page. When you open it, that code runs without you realizing.

Here are the key points about XSS:

1. **Malicious Code:** Attackers insert malicious code, such as JavaScript, into a web page.

2. **Tricking Users:** When a user visits the compromised page, the malicious code executes in their browser.

3. **Unauthorized Access:** The malicious code can steal sensitive information from the user, such as passwords or session cookies.

4. **Types of XSS:** There are several types of XSS, including Stored XSS, Reflected XSS, and DOM-based XSS.

5. **Prevention:** Developers can prevent XSS by using secure coding practices and properly validating input data.

## Brute Force

"Brute Force" is a trial-and-error method used in various situations, especially in the field of security and computing.

Imagine you have a combination lock with numbers to open it. If you don't know the combination, you could try all possible combinations, one by one, until you find the correct one.

Here are the key points about Brute Force:

1. **Exhaustive Testing:** Brute Force is an exhaustive testing method where all possible options are tried one after another, without using any privileged information or shortcuts.

2. **Time and Resources:** Brute Force can be effective, but it can take a lot of time and resources, especially if the number of possibilities is large.

3. **Security:** It's a common technique used by attackers to discover passwords, codes, or keys in systems that lack sufficient security measures.

4. **Mitigation:** To prevent Brute Force attacks, strong passwords and systems that limit the number of failed attempts are used to block repetitive tries.

5. **Applications:** Besides security, Brute Force is also used in mathematics and problem-solving to find solutions without using a specific algorithm.

## Validation

Validation in programming is like a "filter" that checks whether data meets certain rules before being used or processed by a program.

If you have a form on a web page where users enter their information, such as name, email, and password. Validation is responsible for checking that the entered information is correct and meets certain criteria before saving it to a database or using it to perform some action.

Here are some key points about validation:

1. **Data Checking:** Validation ensures that the entered data is of the correct type and within a valid range. For example, an age field should be a positive integer.

2. **Correct Format:** Validation verifies whether the data has the appropriate format. For example, an email field should have a structure like "name@example.com."

3. **Proper Length:** Validation checks that fields do not exceed a maximum length and are not left empty. For example, a password field should have at least 6 characters and not be too long.

4. **Error Messages:** When data does not pass validation, an error message is displayed to inform the user about what needs to be corrected.

5. **Security:** Validation is also essential for ensuring application security. For example, in a login form, validation can prevent malicious code injection attacks.

This ensures that the entered information is correct and reliable, avoiding errors and issues in the program's functionality. Validation is a fundamental practice for creating robust and secure applications.

## MFA

MFA is an authentication method that requires users to provide two or more different forms of identification before granting access to a system or application. This adds an extra layer of security beyond traditional single-factor authentication (typically a password).

Technical aspects of MFA include:

1. **Factors of Authentication:**
   - MFA relies on multiple factors to authenticate users:
     - Knowledge Factor: Something the user knows (e.g., password, PIN).
     - Possession Factor: Something the user possesses (e.g., mobile device, smart card).
     - Inherence Factor: Something inherent to the user (e.g., fingerprint, facial recognition).

2. **Challenge-Response Mechanism:**
   - When a user attempts to log in, the system initiates a challenge, requesting specific authentication factors.
   - The user responds with the required factors to complete the authentication process.

3. **Token-Based Authentication:**
   - MFA often uses tokens to generate one-time passcodes (OTPs) as a possession factor.
   - These tokens can be hardware-based (e.g., RSA SecurID token) or software-based (e.g., Google Authenticator).

4. **Out-of-Band Authentication:**
   - MFA may use out-of-band communication methods to deliver authentication challenges.
   - For example, sending a verification code to the user's mobile device via SMS or a mobile app.

5. **Time-Based or Event-Based Tokens:**
   - Tokens used in MFA can be time-based (changing every certain time interval) or event-based (changing with each new request).

6. **Adaptive Authentication:**
   - Adaptive MFA adjusts the level of authentication based on risk factors, user behavior, or context.
   - For high-risk actions, stronger authentication factors may be required.

7. **Token Enrollment and Management:**
   - Administrators handle token enrollment, provisioning, and revocation to manage MFA for users.

8. **Integration with Identity Providers:**
   - MFA is often integrated with identity providers and Single Sign-On (SSO) solutions to enable seamless user experiences.

Multi-Factor Authentication (MFA) is a robust security measure that involves using multiple factors of authentication to verify a user's identity. By combining different authentication methods, MFA significantly enhances the security of systems and applications, making it more challenging for unauthorized users to gain access.

## Prototype

## Promises

## ES6+

## Async Await


<!--Bibliography-->

## Bibliography

* [Git Pages](https://git-scm.com/)
* [Get started with GitHub.](https://docs.github.com/en/get-started/quickstart/hello-world)
* [About Git](https://docs.github.com/en/get-started/using-git/about-git)
* [Git Merge and Git Rebase](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
* [Git Squash](https://www.geeksforgeeks.org/git-squash/)
* [JavaScript](https://developer.mozilla.org/es/docs/Web/JavaScript)
* [Scrum](https://www.atlassian.com/agile/scrum)
* [HTML](https://developer.mozilla.org/es/docs/Web/HTML)
* [Data-attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)
* [Semantic HTML](https://developer.mozilla.org/en-US/docs/Glossary/Semantics)
* [Accessibility](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML)
* [SEO](https://developer.mozilla.org/es/docs/Glossary/SEO)
* [DOM](https://developer.mozilla.org/es/docs/Web/API/Document_Object_Model)
* [CSS](https://developer.mozilla.org/es/docs/Web/CSS)
* [Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
* [Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)
* [Hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)
* [Scope](https://developer.mozilla.org/en-US/docs/Glossary/Scope) (https://developer.mozilla.org/en-US/docs/Web/CSS/:scope)
* [Strict](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
* [Media Queries](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries)
* [Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)
* [Layouts: How to Make Them and Positioning in CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout)
* [Flexbox Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox) & [Grid Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grid)
* [Bootstrap](https://getbootstrap.com/docs) and [Materialize CSS](https://materializecss.com)
* [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) | [Ajax (XHR)](https://developer.mozilla.org/en-US/docs/Web/Guide/AJAX)
* [HTTP Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods) | [Response Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) | [Session Management](https://developer.mozilla.org/en-US/docs/Web/HTTP/Session)
* [HTTP/2](https://developer.mozilla.org/en-US/docs/Glossary/HTTP_2) | [HTTP/3](https://developer.mozilla.org/en-US/docs/Glossary/HTTP_3)
* [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies), [Local Storage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) & [Session Storage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage)
* [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) | [JSONP](https://developer.mozilla.org/en-US/docs/Glossary/JSONP)
* [JSON Web Token](https://developer.mozilla.org/en-US/docs/Glossary/JSON_Web_Token)
* [Events](https://developer.mozilla.org/en-US/docs/Web/API/Event) | [Event Bubbling](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#event_bubbling_and_capture)
* [SOLID Principles](https://developer.mozilla.org/en-US/docs/Glossary/SOLID)
* [OOP Concept](https://developer.mozilla.org/en-US/docs/Glossary/Object-oriented_programming)
* [Class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes) | [Inheritance](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance) | [Prototype](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/prototype) | [Prototype Inheritance](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
* [Encapsulation](https://developer.mozilla.org/en-US/docs/Glossary/Encapsulation) | [Polymorphism](https://developer.mozilla.org/en-US/docs/Glossary/Polymorphism)
* [Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
* [DoS](https://developer.mozilla.org/en-US/docs/Glossary/Denial_of_Service)
* [XSS](https://developer.mozilla.org/en-US/docs/Glossary/Cross-Site_Scripting)
* [Brute Force](https://developer.mozilla.org/en-US/docs/Glossary/Brute_force_attack)
* [Validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
* [MFA](https://developer.mozilla.org/en-US/docs/Glossary/Multi-factor_authentication)
* [Prototype](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/prototype)
* [Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
* [ES6+](https://developer.mozilla.org/en-US/docs/Web/JavaScript/New_in_JavaScript)
* [Async Await](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await)