# Modern Portfolio Documentation Guide

Official documentation explaining the architectural structure and content management model of the modern, modular, JSON-based portfolio system.

If you do not have technical knowledge or would like to edit JSON files quickly, you can directly copy and send the relevant section of this documentation to ChatGPT or another AI tool.

For example:

* I want to add a new project
* I want to add a new service card
* I want to add experience or education information
* I want to modify the structure of a specific field

When you provide the relevant documentation section along with the current file content to an AI tool, it will provide you with:

* Which file you need to edit
* Which part of the file you need to modify
* What the new JSON structure should look like
* The final updated version of the file

This allows you to safely make the necessary changes without dealing with technical complexities.



## Modern Portfolio

A modern, high-performance, and scalable developer portfolio application. It combines aesthetic design, modular architecture, and JSON-based content management into a single powerful system.

<p align="center">
  <a href="https://yasiralrawi.netlify.app">
    <img src="https://img.shields.io/badge/Live_Demo-Modern_Portfolio-8750f7?style=for-the-badge" />
  </a>
</p>

This documentation provides a detailed explanation of where and how the content of each section can be managed.


### Header (Top Navigation)

The Header is the top navigation menu of the website.
The menu texts, language selection, and contact information are controlled through separate files.

This allows you to update the content without modifying the core code.

<img width="1919" height="903" alt="header-map" src="https://github.com/user-attachments/assets/ae3597c6-38b9-4370-8469-5c92eeee67c3" />

#### ‣ Changing Menu Texts

The texts displayed in the menu are located in the following file:

```
messages/en.json
```

When you open this file, you will see a section like this:

```json
{
  "header": {
    "home": "Home",
    "stats": "Stats",
    "services": "Services",
    "work": "Work",
    "projects": "Projects",
    "resume": "Resume",
    "about": "About",
    "skills": "Skills",
    "languages": "Languages",
    "volunteering": "Volunteering",
    "certificates": "Certificates",
    "contact": "Contact",
    "startAProject": "Start a Project"
  }
}
```

You can modify the text inside the quotation marks as you wish.

For example:

```json
"home": "My Home"
```

If you change the `startAProject` value, the button text will also be updated.

For example:

```json
"startAProject": "Make Your Project"
```

After saving the file, the website will update automatically.
No code changes are required.

The file name `en` represents the English language.

If you want to add a new language, you need to create a new file with the same structure.
For example, for Turkish:

```
tr.json
```

The process of adding a new language will be explained step by step in the following sections.

#### ‣ Changing the Logo

The logo file path is defined in:

```
data/techIcons.ts
```

```ts
export const SiteLogo = "/assets/images/logoLight.svg";
```

Simply replace this path with the path to your new logo file.



#### ‣ Changing the Email Address

The email information is located in:

```
data/contacts.ts
```

```ts
export const contactData = {
  email: "example@email.com"
};
```

You can replace this value with your own email address.




















