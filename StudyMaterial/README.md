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
12. [Meta-tags](#meta-tags)
13. [Input types](#input-types)
14. [Difference between HTML and XHTML](#difference-between-html-and-xhtml)
15. [Data-attributes](#data-attributes)
16. [Bibliography](#bibliography)

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
