# Input and Output

- Inputs
    - Anything the computer takes in.
    - Keyboard, Mouse, Network card, camera, ect

- Output
    - Anything the computer puts out.
    - Text, Graphics, Sound, Networking, Printing, etc.

- Input and Output together are called **I/O**

- The only part of your computer that is *really* a computer is the CPU and the RAM, All other devices are technically I/O Devices

## Memory vs I/O

- reading and writing to I/O on devices is **slow**
    - I/O operations take *seconds* or *milliseconds*
    - CPU Operations take *nanoseconds*

- Every time you ask JS to do an I/O operation, it pauses your program

- In NodeJS, you have to write a function for JS to run once it resumes
    - This function is called an *asynchronous callback*

## What does "asynchronous" mean?
 - Javascript is a "synchronous" language. This means it runs the code line by line, one a time. When Javascript "listens" for events, it seemingly has asynchronous functionality, meaning it can process more than one thing at once. While it is still synchronous under the hood, it takes on the appearance of asynchronicity.

## Terminal I/O

- In JS
    - `console.log` means "print this line to the terminal"

- In NodeJS,
    - `process.stdin` means "input coming from the terminal"

Example:
```
process.stdin.once('data', (chunk) => {
    console.log(chunk.toString())
})
```
- `process.stdin` means "hey terminal input"
- `.once('data', ...)` means "when you get some data"
- `console.log(chunk.toString())` do this!

## Event Listeners

- They are attached to a specific element or interface

- AND they wait for a specific type of interaction or event

- THEN run your callback function.

## Welcome to Callback City!

The previous one line code is equivalent to this:
```
function printline(chunk) {
    console.log(chunk)
}
process.stdin.once('data', printLine);
```

`printLine` is a *callback* (since you're asking the I/O device to *call you back* when it receives input)

- you can put any function into a callback function you just need to remember not to call it.

## The way to exit

- `process.exit()` tells your program to quit
    - it must be called from *inside* the callback function


## async/await and Promises
- A promise is a placeholder for future data.
- `async` marks a function as utilizing a promise
- `await` means "wait for the following to happen"
- when you use `await` inside of the function, you must use `async` to define that function

## The readline Library

- NodeJS has a collection of *JavaScript Libraries*
    - Libraries are an extension to the language
    
- One library is called `readline`

## Using readline

- First you need to bring the library into the JS program
- using `require` is how you bring in any native libraries

`const readline = require("readline")`

then you need to establish where you are reading from and what you are writing to.

`let rlInterface = readline.createInterface(process.stdin, process.stdout)`

- this states that it is reading from the standard input and writing to the standard output  
- we want this to be stored in a variable
    - `rlInterface`

- then we create a function that wraps around a promise.  
    - a `Promise` stands in for data that has not been received yet.   
    - when the promise is resolved, it will then continue the program.

```
function ask(questionText) {
    return new Promise(function(resolve, reject) {
        rlInterface.question(questionText, resolve)
    })
}
```

# Git

- *git* is a distributed version control tool
    - it tracks changes to your files and saves them through commits
    - you can go back to previous commits if needed

## What is a version control system?

- it's a file system, plus it keeps track of
    - who made the changes
    - when the changes were made
    - and why the changes were made

## Why is version control important?
- For a dev team?
    - you can recover lost code
    - share code between contributors
    - see which parts people are working on to stop duplication
- For an individual on that dev team?
    - you can roll back to old code if you break something
- For product manager or client?
    - to track times
    - see who is working on what
- For a sysadmin?
    - Keep track of which version is being working on
- For a QA engineer?
    - To make sure everything works
    - If a change breaks something they can see who was responsible

## git vs GitHub

- *git* is a distributed version control tool started in 2005
- *github* is a centralized collaboration website that was started in 2007

- GitHub holds onto your repositories for you

## Core Concept: Repository

a *repository* or "repo" is a hidden file that tracks changes

>Do not create a repo inside of a git repo!

- the command `git init` "blesses" the current directory and makes it into a repo
- the command `git status` describes the state of the current repo

## Core Concepts: Staging Area

git has a two step process for tracking changes on a file

- first you `add` the changes to the *staging area*
- then you `commit` the changes to the *history*
    - commits take a message when making them and they should explain *why* you did what you did

## Core Concepts: Commit

After adding changes you then must `commit` your changes.

When committing, each time you must also add a message.

example:  
`git commit -m 'allow users to change their profile picture'`

## Adding and Committing

Always in Master Branch
When adding and committing changes to files you must **FIRST** use `git add .`
Followed **Secondly** by `git commit -m"some message"`
This order is important because "adding" caches the changes, and "committing" logs the changes.
`git status` is a very useful tool that can allow you to see which branch you're working on and if changes have been committed.
`git log` shows you all the changes that were made to a file
`git show` plus whatever the commit ID is will give a detailed account of the commit. It reveals information about a single commit, including metadata (such as date and author) and the changes made (in unix diff)
Keep in mind that all commits will be accessible in GitHub. This is important because it could cause security issues(More on this in future lectures)
Commit IDs are automatically generated and are unique for _each_ commit
Adding and committing will be the most common git commands that will be used.
Don't go into the VIM!... unless you want to, I'm not your mother
Vim occurs when you don't add a message to you commit, but is a tool used by developers
[vimAndGit](https://vimways.org/2018/vim-and-git/)

## Repository?

A repository (or "repo") contains the version history a collection of files
in git, a repo comprises all files and subdirectories inside a single "root" directory
To create a repository:

1. `git init`
2. `git add README.md`
3. `git commit -m"commit message"`
4. `git branch -M master`
5. `git remote add origin git@github.com:username/project-name.git`
6. `git push -u origin master`

## Pushing and Pulling

`git push` "pushes" the most recent commit to the project repository on GitHub. Pushes help you track the progression of the project, who is working on it and the history of it.

`git pull` "pulls" any new changes down from the repo locally. Pulls allow you to merge any conflicts between the repo and your code.

Merge Conflicts are an event that occurs when Git is unable to automatically resolve differences in code between two commits. When all the changes in the code occur on different lines or in different files, Git will successfully merge commits without your help.


# QA & Further Resources

## QA
- Q: How do I format code blocks in Discord for readability? 

    - A: Place three backticks ``` at the beginning and end of your code block. Optionally, you can put javascript on the first line OR js next to the first three backticks for syntax highlighting.


- Q: How do I multi-select in VSCode?

    - A: Select your target, and VSCode will highlight all repeat occurrences. Then, hit CTRl-D to select as many instances as you want.

- Q: Will one error stop the rest of my code running?

    - A: Yes. Because Javascript is compiled "just in time", if it finds an error during its creation phase, it will halt the creation phase and throw an error. 

- Q: What type is user input?
    - A: A: User input always comes in as a string. However, this string may not be in the format you expect. If you are unsure of what you will receive, you can always sanitize your input via the .toString() method OR the parseInt() function.

- Q: Will my commit ever overwrite another commit?
    - A: No. Commits have what is called a "hash", a unique ID. 

- Q: How do I clone a repository? How do I add a folder to GitHub?
    - A: Check out further resources for detailed instructions.

## Further Resources

- [MDN: Callbacks](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)
- [MDN: Async functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- [MDN: Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)

- [GitHub: How to clone a repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)
- [GitHub: How to add a preexisting directory to GitHub](https://docs.github.com/en/github/importing-your-projects-to-github/importing-source-code-to-github/adding-an-existing-project-to-github-using-the-command-line)
- [GitHub: Terminal Cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf)


