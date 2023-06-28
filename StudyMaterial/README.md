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
28. [Layouts how to make them and positioning in css](#layouts-how-to-make-them-and-positioning-in-css)
29. [Flexbox layout & Grid Layout](#flexbox-layout-&-grid-layout)
30. [Bootstrap and Materialize CSS](#bootstrap-and-materialize-css)
31. [OOCSS | BEM | SMACSS](#oocss-bem-smacss)
32. [What are css preprocessors | SASS](#what-are-css-preprocessors-sass)
33. [Fetch API | Ajax (XHR)](#fetch-api-ajax(XHR))
34.
35.
36.
37.
38.
39.
40.
41. [Bibliography](#bibliography)

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
