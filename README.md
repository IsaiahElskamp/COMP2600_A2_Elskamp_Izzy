# Hosting a Resume on GitHub Pages with the Pelican Static Site Generator (Windows)

## Statement of Purpose

This README describes how to host a markdown-formatted resume using Github pages and the Pelican static site generator. This guide is written for readers like Marvin McLaren who have basic markdown and command line knowledge, but do not have any prior experience with forges or static site generators. 

This document gives detailed instructions for each step of the process, and links these steps to the principles of technical writing described in "Modern Technical Writing" by Andrew Etter. The document also contains further readings on the topic, and a FAQ to answer your burning questions.

>[!NOTE]
> This tutorial is for Windows machines only.

## Prerequisites

- A Windows machine running Windows 10 or 11
- A [GitHub](github.com) account

## Instructions

### Project Setup

#### Python Installation

>[!Note]
> If you already have Python installed (version must be at least 3.10), skip step 1.

1. Go to [Python Downloads](https://www.python.org/downloads/) and click the yellow button that states "Download Python (version number)".
2. Open the exe and follow the Python setup wizard.

#### Pelican Installation

1. Open Windows PowerShell and enter this command:
```
python -m pip install "pelican[markdown]"
```
### Create and Host your Resume Website

#### Generate a New Site and Run it Locally

1. Create a new directory for your project:
```
mkdir projectName
```
2. Navigate to the directory:
```
cd projectName
```
3. Start a new Pelican generation process:
```
pelican-quickstart
```
4. Follow the questions

6. Generate your website:
```
pelican content
```
6. Run your website locally:
```
pelican --listen
```
#### Add your Resume to the Site

Now that you have generated and run your website, you can add a Markdown formatted page to the site which contains your resume.

1. Navigate to the contents folder:
```
cd projectName\contents
```
2. Create a folder to hold your pages. It must be named "pages":
```
mkdir pages
```
3. Navigate into the pages folder:
```
cd pages
```
4. Create your resume.md Markdown file:
```
Notepad resume.md
```
This will open notepad and prompt you to create a new file called "resume". Click yes and you can begin editing.

5. Edit your resume.md file in notepad and save it using **Ctrl + S** once you have completed the resume.

#### GitHub Repository Setup

In order to host your website on GitHub pages, you first need to create a repository.

1. Log in to your GitHub account and click the ``+`` button in the top right corner.
2. Click ``New Repository``.
3. Enter a name, and leave all other settings as default.
4. Click ``Create Repository``.
5. Copy the url of your repository from your browser once you are inside. For example, mine would look like: https://github.com/IsaiahElskamp/COMP2600_A2_Elskamp_Izzy.git

#### Git Setup

#### GitHub Pages Setup

## Further Resources

- [Markdown Basic Guide](https://quarto.org/docs/authoring/markdown-basics.html) - Basic formatting guide for the Markdown language
- [Pelican Quickstart Documentation](https://docs.getpelican.com/en/stable/quickstart.html) - Official Pelican documentation on how to install the software and generate a new website
- [Python for Windows](https://docs.python.org/3/using/windows.html) - A general overview for using/installing Python on Microsoft Windows
- [Creating a GitHub Pages Site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site) - A set of steps for setting up a new site from your repository using GitHub Pages

## FAQ

**Q: Why do I have to use the GitHub Forge to host my site?**

A: You don't! Since Pelican gives such a simple output, you can use any Forge with built-in static site hosting. Some other popular Forges with this feature include [Codeberg](https://codeberg.org/) and [Gitlab](https://about.gitlab.com/).


**Q: How do I update my site if it is already hosted?**

A: To update your site again, you will have to first re-generate your Pelican site and route the output to your gh-pages branch after you have made your changes. Enter this into your command line while within the project directory:
```
python -m pelican content
python -m ghp_import output -b gh-pages
```
Now you can push to the gh-pages branch... 
```
git push origin gh-pages
```
and your hosted site will be updated!

## Credits

Proofreaders:
- Conner Lavineway
- Christian Javen Samson

