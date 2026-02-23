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


### Home Page → Hero Section

This image shows which files provide the data for the top section of the website (the Hero area).

<img width="1919" height="903" alt="hero-map" src="https://github.com/user-attachments/assets/dc682336-cc6f-45dd-9584-c07483292a17" />

All content displayed in the Hero section (texts, buttons, profile photo, social media links, and statistics) is managed through separate files.

This means you do not need coding knowledge to update the content.


#### ‣ Text Content

All text in the Hero section comes from the `messages/en.json` file.

After opening this file, locate the `"home"` section. Inside, you will see a structure like this:

```json
"home": {
  "hero": {
    "greeting": "Hello, I'm",
    "name": "Yasir",
    "titleLine1": "Full-Stack",
    "titleLine2": "Web Developer",
    "description": "I transform complex user experience challenges into clear, cohesive solutions, developing strong and reliable foundations that deliver real impact and tangible results",
    "downloadCV": "Download CV",
    "viewWork": "View Work",
    "follow": "FOLLOW"
  }
}
```

You can freely modify the text inside the quotation marks.

For example:

```json
"name": "Ahmet"
```

After saving the file, the website will update automatically.
No additional steps are required.

#### ‣ Contact Information

Contact details are stored in a separate file.
This is because the same information is used both in the Hero section and in the Contact section.

To update it, open:

```
data/contacts.ts
```

You will see a structure like this:

```ts
export const contactData: ContactData = {
  email: "yasir7alrawi23@gmail.com",
  phone: "",
  location: "",
  cvPath: "/assets/docs/cv.pdf",
  projectsPath: "/projects",
  socialLinks: [
    {
      name: "Instagram",
      icon: "Instagram",
      href: ""
    },
    {
      name: "LinkedIn",
      icon: "Linkedin",
      href: ""
    },
    {
      name: "Twitter",
      icon: "Twitter",
      href: ""
    },
    {
      name: "GitHub",
      icon: "Github",
      href: ""
    }
  ]
};
```

To update social media links, simply add your profile URL to the `href` field.

For example:

```ts
href: "https://instagram.com/yourusername"
```

When users click the Instagram icon in the Hero section, they will be redirected to your profile.



#### ‣ Profile Photo

The profile photo is updated in:

```
data/personal.ts
```

```ts
export const personalData = {
  photo: "/assets/images/my-photo.png"
};
```

Simply replace this path with the file path of your own photo.



#### ‣ Statistics

Statistics such as years of experience and number of projects are used both in the Hero section and in the Statistics section.

To update them, open:

```
data/stats.ts
```

You will see values like:

```ts
export const statsData = {
  years: 5,
  projects: 54,
  clients: 2,
  awards: 48
};
```

Once you modify these numbers, the website will automatically reflect the changes.





### Home Page → Statistics

This image shows which files provide the data for the **Statistics section** on the Home Page.

<img width="1919" height="903" alt="stats-map" src="https://github.com/user-attachments/assets/9c22e682-9a69-4367-b5e9-8a891f1940b9" />

The information displayed in this section is managed through separate files.
This allows you to easily update both the numbers and the texts.


#### ‣ Title and Text Content

The section title and descriptive texts come from the `messages/en.json` file.

After opening the file, locate the `"home"` → `"stats"` section.

You will see a structure like this:

```json
"home": {
  "stats": {
    "title": "Our Achievements",
    "subtitle": "Let the figures tell the story of our impact before you explore our work",
    "yearsLabel": "Years",
    "yearsDesc": "of Experience",
    "projectsLabel": "Projects",
    "projectsDesc": "Successfully Completed",
    "clientsLabel": "Clients",
    "clientsDesc": "Worldwide",
    "awardsLabel": "Awards",
    "awardsDesc": "& Recognition",
    "trustedBy": "Trusted by industry leaders worldwide",
    "yearsExp": "Years Exp",
    "projects": "Projects",
    "k": "K"
  }
}
```

You can modify these texts as you wish.

For example:

```json
"title": "Our Successes"
```

After saving the file, the website will update automatically.



#### ‣ Updating the Numbers

The number of years of experience, projects, clients, and awards are stored in a separate file.

Open:

```
data/stats.ts
```

You will see a structure like this:

```ts
export const statsData = {
  years: 5,
  projects: 54,
  clients: 2,
  awards: 48
};
```

You can update these values according to your own information.

For example:

```ts
years: 8,
projects: 120
```

Once saved, both the Statistics section on the Home Page and any other areas using this data will update automatically.


### Home Page → Services

This image shows which file provides the data for the **Services section** on the Home Page.

<img width="1919" height="903" alt="services-map" src="https://github.com/user-attachments/assets/ed5fcb35-ef32-4807-b04d-ad6e47e2cf4f" />

All content displayed in this section is managed through a single file:

```
messages/services/en.json
```

The file structure is as follows:

```json
{
  "title": "My Quality Services",
  "subtitle": "I turn ideas into powerful, scalable, and beautifully crafted digital experiences — built with precision and long-term vision.",
  "items": [
    {
      "title": "Full Stack Development",
      "description": "I create complete end-to-end web solutions — from intuitive, high-performance interfaces to secure backend architectures. My focus is on clean code, scalability, and exceptional user experience across all devices.",
      "icon": "Code"
    },
    {
      "title": "UI / UX Design",
      "description": "I design elegant, functional, and user-centered interfaces. Every layout, interaction, and flow is shaped to feel natural, visually refined, and effortless, ensuring your users enjoy every moment of the experience.",
      "icon": "Palette"
    },
    {
      "title": "Algorithm Development",
      "description": "I develop custom algorithms that solve complex problems with precision and efficiency. From optimized logic structures to intelligent automation, I engineer systems that run smarter, faster, and more reliably.",
      "icon": "Cpu"
    },
    {
      "title": "Website Security & Maintenance",
      "description": "I protect and maintain websites using industry-standard security practices. With continuous monitoring, performance optimization, and regular updates, I ensure your website stays fast, stable, and fully secure.",
      "icon": "Shield"
    }
  ]
}
```



#### ‣ What Can Be Modified?

* `title` → Section title
* `subtitle` → Section description text
* `items` → All service cards

For each card:

* `title` → Service title
* `description` → Service description
* `icon` → Icon name used for the card

To add a new service, simply add a new object inside the `items` array.
Once you save the file, the website will update automatically.

To add a new card, insert the following structure into the `items` array:

```json
{
  "title": "",
  "description": "",
  "icon": ""
}
```

Make sure to place a comma `,` between objects.
However, do not add a comma after the last object. Otherwise, the JSON file will produce an error.



#### ‣ Icon Selection

The icons used in service cards come from the `lucide-react` library.

To change an icon, simply write the name of the desired icon inside the `icon` field:

```json
"icon": "Code"
```



#### ‣ How to Choose an Icon

1. To view the list of available icons:

<p align="center">
  <a href="https://lucide.dev/icons" target="_blank">
    <img 
      src="https://github.com/user-attachments/assets/6ce78af2-d171-4f5c-a698-80db4404bd8a"
      alt="Lucide React Icons"
      width="900"
      style="border-radius:15px;"
    />
  </a>
</p>

<p align="center">
  <sub>
    If you cannot access the icon page,
    <a href="https://lucide.dev/icons" target="_blank">
      click here
    </a>
    to access it directly.
  </sub>
</p>

2. Click on the icon you want to use.
3. Open the details page and view its code.
4. Copy the icon name (for example: `Palette`, `Shield`, `Cpu`, `Smartphone`).
5. Paste the copied name into the `icon` field of the relevant card inside your JSON file:

```json
"icon": "Smartphone"
```

Once saved, the icon will update automatically.

To correctly obtain the icon name, follow the steps below:

<br>

<p align="center">
  <img width="900" alt="Copying the icon name" src="https://github.com/user-attachments/assets/1d017023-ca6e-4fab-a754-53d04df011da" style="border-radius:15px;" />
</p>

1. Click on the icon you want to use.
2. Navigate to its details page and view the code.
3. On the opened page, copy the icon name.
4. Paste the copied name into the `"icon"` field in your JSON file.

> Note: Icon names are case-sensitive. You must write the name exactly as it appears on the website.


### Home Page → Featured Projects

This image shows which files provide the data for the **Featured Projects** section on the Home Page.

<img width="1919" height="903" alt="featured-projects-map" src="https://github.com/user-attachments/assets/d5e1810d-69fd-410b-918b-66fc55cf57fd" />

All information displayed in this section is managed through a single file:
`messages/projects/index/en.json`

The file structure is as follows:

```json
{
  "featuredProjects": {
    "title": "Featured Projects",
    "subtitle": "Showcasing innovative solutions built with modern technologies",
    "viewProject": "View Project"
  }
}
```


#### ‣ Editable Fields

* `title` → Section title
* `subtitle` → Introductory description text
* `viewProject` → Button label text

When you modify any of these fields, the page updates automatically.

Other project-related information cannot be edited manually from this section.
These fields are retrieved automatically (dynamically) from the individual project files.

In the following sections, we will explain in detail how to add a new project.

For a project to appear in the **Featured Projects** section, the following property must be added to the relevant project’s JSON file:

```json
"isFeatured": true,
```


### Home Page → All Projects Section

This image shows which files provide the data for the **All Projects section** on the Home Page.

<img width="1919" height="903" alt="all-projects-map" src="https://github.com/user-attachments/assets/5428db7f-3da8-42a1-a5da-52fb2ef0ffb5" />

The following elements displayed in this section:

* Title (*Explore My Complete Portfolio*)
* Description text
* “View All Projects” button
* Project, Technology, and Year statistics

are managed through two different files.


#### ‣ Where Are the Texts Edited?

The title, description, and button text are managed from the following file:

```
messages/projects/index/en.json
```

File structure:

```json
"featuredProjects": {
  "allProjects": {
    "title": "Explore My Complete Portfolio",
    "description": "Discover more...",
    "button": "View All Projects",
    "stats": {
      "projects": "Projects",
      "technologies": "Technologies",
      "years": "Years"
    }
  }
}
```


#### ‣ Editable Fields

* `title` → Section title
* `description` → Description text
* `button` → Button label
* `stats` → Sub-statistics labels

For example:

```json
"title": "Explore All My Projects",
"button": "View All Projects"
```

When you update these values, the page reflects the changes automatically.


#### ‣ Where Are the Numbers Edited?

The numbers displayed at the bottom:

* Total number of projects
* Number of technologies used
* Years of experience

are retrieved from the following file, as explained earlier in the **Statistics** section:

```
data/stats.ts
```

File structure:

```ts
export const statsData = {
  years: 5,
  technologies: 26,
  projects: 54
};
```

When you modify these values, the section updates automatically.



## Home Page → Experience & Education

This image shows which file provides the data for the **Experience & Education** section on the Home Page.

<img width="1919" height="903" alt="experience-education-map" src="https://github.com/user-attachments/assets/09797f30-9e52-40d2-9e02-102e8ff7f0c6" />

This section is managed through the following file:

```
messages/resume/en.json
```

The file structure is as follows:

```json
{
  "title": "Experience & Education",
  "subtitle": "My professional journey and academic achievements",
  "tabs": {
    "experience": "My Experience",
    "education": "My Education"
  },
  "experience": [],
  "education": []
}
```

---

#### ‣ Titles and Tabs

* `title` → Main section title
* `subtitle` → Description text
* `tabs.experience` → Experience tab label
* `tabs.education` → Education tab label

When you modify these texts, the page updates automatically.

---

#### ‣ How to Add Experience

Experience entries are stored inside the `"experience"` array.

Example structure:

```json
{
  "year": "July 2025 - August 2025",
  "title": "Freelance Full-Stack Developer",
  "company": "AI-Powered Audio Separation Platform"
}
```

---

#### ‣ Meaning of Experience Fields

* `year` → Employment date range
* `title` → Position title
* `company` → Company or project name

---

#### ‣ Adding a New Experience Entry

Simply add a new object inside the `experience` array:

```json
"experience": [
  {
    "year": "2026 - Present",
    "title": "Senior Developer",
    "company": "Tech Company"
  }
]
```

If you want to add multiple entries, the structure should look like this:

```json
"experience": [
  {
    "year": "2026 - Present",
    "title": "Project 1",
    "company": "Alrawi"
  },
  {
    "year": "2024 - Present",
    "title": "Project 2",
    "company": "Alrawi"
  }
]
```

> Note: A comma must be placed between each object. However, do not add a comma after the last object.

---

#### ‣ How to Add Education

Education entries are stored inside the `"education"` array.

Example structure:

```json
{
  "year": "September 2021 - June 2025",
  "title": "Bachelor in Computer Engineering",
  "company": "Kırıkkale University, Kırıkkale"
}
```

---

#### ‣ Meaning of Education Fields

* `year` → Education date range
* `title` → Degree or program name
* `company` → University or institution name

---

#### ‣ Adding a New Education Entry

Add a new object inside the `education` array:

```json
"education": [
  {
    "year": "2026 - 2028",
    "title": "Master in Software Engineering",
    "company": "Example University"
  }
]
```

To add multiple education entries:

```json
"education": [
  {
    "year": "2026 - 2028",
    "title": "Master in Software Engineering",
    "company": "Example- 1 University"
  },
  {
    "year": "2023 - 2026",
    "title": "Bachelor in Software Engineering",
    "company": "Example- 2 University"
  }
]
```

> Note: A comma must be placed between each object. However, do not add a comma after the last object.











