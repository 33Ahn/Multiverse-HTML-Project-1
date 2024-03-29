# Multiverse-HTML-Project-1

Project #1: HTML/CSS Personal Website

Introduction

#### Why did I do this project?

This is my first project to as an apprentice at Verizon through Multiverse bootcamp.
As part of the Multiverse bootcamp curriculum, I wanted to use this project as a learning and growing opportunity and showcase my projects.

#### what did I build?

I built my responsive personal website that has home, bio, experiences, portfolios, and contact pages.
Even though there are no projects to showcase yet, the portfolios page has placeholders for the projects to come in the near future.

#### How did i build it?

First, I created a repository in GitHub and cloned it to my local computer. Throughout the whole process, my work was added to a staging area and committed and pushed to my remote repository in GitHub. By doing so, I could leave the history of my wrok progress for the version control purpose.
I got to use the command line to navigate the file tree and create directories and files.

Second, I created index.html, which is the default landing page for any webpages. After the initial starting point, I built the rest of the pages. HTML stands for Hyper Text Markup Language, which is the code that defines our content's structure and consists of a number of elements.

Third, I added CSS (Cascading Style Sheets) to add colors, images, position elements to the HTML files to make websites more pleasing to users.

Fourth, I added JavaScript for the creaation of the hamburger menu for a mobile view even though this project is about HTML and CSS only.

Lastly, I deployed my personal website through GitHub Pages. Git integrates with GitHub.com, a platform for developers to host and share their code.

#### What did I learn?

Through this project, I learned three things.

First, it is important to use semantic HTML elements because they clearly describe their meanings to both the browser and the developer. That information helps robots/crawlers like Google to better understand the roles and relative importance of the different parts of our page, which could affect SEO (Search Engine Optimization) result too. Also for users who are blind or visually impaired and rely on screen readers, proper use of HTML5 semantic elements will greatly improve their experiences.

Second, I can have a fully deployed website on GitHub, and can share a link to it with others.

Third, web pages need to have responsive designs to render appropriately based on users' devices to improve their expereinces.
During the process of making my web pages responsive, I experienced the situation that the content was overflowing into other portions of the site due to the height setting. It was tricky to manipulate the size of the contents and images.
With more practice, I can become better.

Key Topics

Git & Git workflow

    git clone <url>
    git add <file_name> or git add .
    git status
    git commit -m "commit message"
    git push
    git pull

HTML

    proper usage of Attributes: name and value
    Document structure, Proper Nesting HTML
    Headings h1, h2, h3...
    Paragraphs
    Images
    Lists
    Links
    Semantic Elements such as <article>, <aside> instead of only <div>
    Structure elements such as <header>, <nav>, <main>, <footer>
    Fallback elements such as <div>, <span>

CSS

    3 ways of doing CSS -- inline, internal, external

    Margin vs. Padding
    Borders and Shadows
    Fonts
    Background-color
    Background-image
    background-size
    Sizes: em, rem, px, %
    Flexbox
    color: hexadecimal, rgb and named
    Media Queries for mobile friendly design

    Types of Selectors
        1. HTML element name
        2. by html element's id -- use #
        3. by html element's class -- use .
        4. by attribute -- [type="text"] or [href=" "]

    3 rules of CSS
        1. the source order: when the same selector is chosen, the last selector with value will be applied.
        2. the specificity: the selectors have a rank or score
                HTML tags: 1
                classes: 10
                ids: 100
                inline class: 1000
        3. the inheritance: inherit values from parents.

    Box model
        1. content: can be styled directly
        2. padding: CAN'T be styled, transparent
        3. border: can be styled directly
        4. margin:CAN'T be styled, transparent

GitHub

    Create a new repository
    Deploy to personal pages

Resources

1. HTML
   https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics

2. CSS
   https://developer.mozilla.org/en-US/docs/Web/CSS

3. Responsive navbar
   https://dev.to/devggaurav/let-s-build-a-responsive-navbar-and-hamburger-menu-using-html-css-and-javascript-4gci


Deployment

    Step 1 - Create a Directory for the Website Make sure that you have your HTML files already in the current directory.

    Step 2 - Create a file called Dockerfile
    Place the following contents into the Dockerfile

        FROM nginx:alpine
        COPY . /usr/share/nginx/html

    These lines of code represent the image we're going to use along with copying the contents of the current directory into the container.


    Step 3 - Build the Docker Image for the HTML Server
    Run the following command:

        docker build -t html-server-image:v1 .

    You can confirm that this has worked by running the command:

        docker images

    Step 4 - Run the Docker Container
    Run the following command to run the HTML container server:

        docker run -d -p 80:80 html-server-image:v1


    Step 5 - Test the Port with cURL
    Run the following command to ensure the server is running:

        curl localhost:80

    You can also view it in the browser now by going to localhost:80 and you should see your HTML file

To push a Docker container image to Docker Hub
    To push an image to Docker Hub, you must first name your local image using your Docker Hub username and the repository name that you created through Docker Hub on the web.

    You can add multiple images to a repository by adding a specific :<tag> to them (for example docs/base:testing). If it’s not specified, the tag defaults to latest.

    Name your local images using one of these methods:

        When you build them, using docker build -t <hub-user>/<repo-name>[:<tag>]
        By re-tagging an existing local image docker tag <existing-image> <hub-user>/<repo-name>[:<tag>]
        By using docker commit <existing-container> <hub-user>/<repo-name>[:<tag>] to commit changes
        Now you can push this repository to the registry designated by its name or tag.


        docker push <hub-user>/<repo-name>:<tag>
    The image is then uploaded and available for use by your teammates and/or the community.