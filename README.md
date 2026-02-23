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

 

#### ‣ Titles and Tabs

* `title` → Main section title
* `subtitle` → Description text
* `tabs.experience` → Experience tab label
* `tabs.education` → Education tab label

When you modify these texts, the page updates automatically.

 

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

 

#### ‣ Meaning of Experience Fields

* `year` → Employment date range
* `title` → Position title
* `company` → Company or project name

 

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

 

#### ‣ Meaning of Education Fields

* `year` → Education date range
* `title` → Degree or program name
* `company` → University or institution name

 

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


## Home Page → Skills (Skills & Expertise)

This image shows which file provides the data for the **Skills** section on the Home Page.

<img width="1919" height="903" alt="skills-map" src="https://github.com/user-attachments/assets/92571936-b8f2-4f17-b425-619f50508af0" />

This section is managed through the following file:

```
messages/skills/en.json
```

The file structure is as follows:

```json
{
  "title": "Skills & Expertise",
  "subtitle": "Technologies and tools I work with...",
  "categories": {
    "programmingLanguages": "Programming Languages",
    "frameworks": "Frameworks & Libraries",
    "concepts": "Concepts & Techniques",
    "databases": "Databases"
  },
  "skills": {
    "programmingLanguages": [],
    "frameworks": [],
    "concepts": [],
    "databases": []
  }
}
```

 

#### ‣ Changing the Title and Category Names

* `title` → Section title
* `subtitle` → Description text
* `categories` → Tab labels

For example:

```json
"title": "My Skills",
"programmingLanguages": "Programming Languages"
```

When you save the file, the page updates automatically.

 

#### ‣ How to Add a Skill

Each category has its own array.

Example:

```json
"programmingLanguages": [
  { "name": "C#" },
  { "name": "Java" }
]
```

 

#### ‣ Adding a New Programming Language

```json
{ "name": "Python" }
```

 

#### ‣ Adding a New Framework

```json
"frameworks": [
  { "name": "ASP.NET MVC Core" },
  { "name": "Laravel" },
  { "name": "React" }
]
```

 

#### ‣ Adding a New Concept

```json
{ "name": "Clean Architecture" }
```

 

#### ‣ Adding a New Database

```json
{ "name": "PostgreSQL" }
```

 

#### ‣ Important Notes

* A comma `,` must be placed between each object.
* Do not add a comma after the last element.
* Filling in only the `"name"` field is sufficient.


## Home Page → Languages

This image shows which file provides the data for the **Languages** section on the Home Page.

<img width="1919" height="903" alt="languages-map" src="https://github.com/user-attachments/assets/0359f538-bba8-4c3d-8188-1e81562e0dd1" />

This section is managed through the following file:

```
messages/languages/en.json
```

The file structure is as follows:

```json
{
  "title": "Languages",
  "subtitle": "Mastering languages...",
  "levels": {
    "native": "Native",
    "professional": "Professional",
    "intermediate": "Intermediate"
  },
  "languages": []
}
```

 

#### ‣ Changing the Title and Level Names

* `title` → Section title
* `subtitle` → Description text
* `levels` → Language level labels

For example:

```json
"title": "Languages",
"native": "Native Language"
```

When you save the file, the page updates automatically.

 

#### ‣ How to Add a New Language

Each language is stored inside the `"languages"` array.

Example structure:

```json
{
  "name": "Arabic",
  "nativeName": "العربية",
  "level": "native",
  "flag": "🇮🇶",
  "backward": "/assets/images/LanguagesFlags/iraq.png"
}
```

 

#### ‣ Field Definitions

* `name` → Language name in English
* `nativeName` → Language name in its native form
* `level` → Proficiency level (`native`, `professional`, `intermediate`)
* `flag` → Emoji flag
* `backward` → Path to the background flag image

 

#### ‣ Adding a New Language

Simply add a new object inside the `languages` array:

```json
{
  "name": "German",
  "nativeName": "Deutsch",
  "level": "intermediate",
  "flag": "🇩🇪",
  "backward": "/assets/images/LanguagesFlags/germany.png"
}
```

 

#### ‣ Important Notes

* The `level` field must be one of the following values only:

  * `native`
  * `professional`
  * `intermediate`

* A comma must be placed between each object.

* Do not add a comma after the last element.


## Home Page → Volunteering Section

This image shows which file provides the data for the **Volunteering** section on the Home Page.

<img width="1919" height="903" alt="volunteering-map" src="https://github.com/user-attachments/assets/26abe781-2dd1-4fdf-ae19-c796022610aa" />

This section is managed through the following file:

```
messages/volunteering/en.json
```

The volunteering title and all event content are automatically retrieved from this file.

 

#### ‣ File Structure

```json
{
  "title": "Volunteering",
  "volunteering": []
}
```

 

#### ‣ How to Add a New Volunteering Activity

Each activity is added as an object inside the `"volunteering"` array.

Example structure:

```json
{
  "role": "Guest Speaker",
  "organization": "Bahçeşehir College – Kırıkkale Campus",
  "event": "Career Journeys: How I Succeeded",
  "location": "Kırıkkale, Türkiye",
  "date": "November 2025",
  "description": "As a representative of Kırıkkale University, I shared my experiences...",
  "image": "/assets/images/Volunteering/bahcesehir-katilim-belgesi.png"
},
{
  "role": "Organizing Committee Member",
  "organization": "Kırıkkale University",
  "event": "International Symposium on History of Science",
  "location": "Kırıkkale, Turkey",
  "date": "November 2024",
  "description": "Served as a member of the organizing committee for the International Symposium on History of Science, contributing to planning, organizing, website management, and supervision to ensure the success of the academic event.",
  "image": "/assets/images/Volunteering/Committee.png"
}
```

 

#### ‣ Field Descriptions

* `role` → Role (e.g., Guest Speaker, Mentor, Volunteer)
* `organization` → Organization name
* `event` → Event title
* `location` → City and country
* `date` → Date information
* `description` → Description text
* `image` → Path to the certificate or event image

 

#### ‣ Adding an Image

1. Add the image to the following folder:

```
/assets/images/Volunteering/
```

2. Specify the file name in the `image` field:

```json
"image": "/assets/images/Volunteering/file-name.png"
```

 

#### ‣ Important JSON Rules

* A comma `,` must be placed between each object.
* Do not add a comma after the last object.
* The image path must be written correctly.
* If the file structure is broken, the system will return an error.




## Home Page → Certificates

This image shows which file provides the data for the **Certificates** section on the Home Page.

<img width="1919" height="903" alt="certificates-map" src="https://github.com/user-attachments/assets/9ba47c0d-af48-417b-b564-8fad8a28a810" />

This section is managed through the following file:

```
messages/certificates/en.json
```

The title, subtitle, category names, and all certificates are automatically retrieved from this file.

 

#### ‣ File Structure

```json
{
  "title": "Certificates & Achievements",
  "subtitle": "Professional certifications and continuous learning journey",
  "certificatesCount": "Certificates",
  "viewCertificate": "View Certificate",
  "of": "/",
  "categories": {},
  "certificates": []
}
```

 

#### ‣ Editing Titles and Texts

* `title` → Section title
* `subtitle` → Description text
* `certificatesCount` → Certificate count label
* `viewCertificate` → Button text

Example:

```json
"title": "Certificates",
"viewCertificate": "View Certificate"
```

When you update these values, the page updates automatically.

 

#### ‣ Category Management

Categories are defined inside the `categories` object:

```json
"categories": {
  "ai": "Artificial Intelligence",
  "cybersecurity": "Cybersecurity",
  "devops": "DevOps"
}
```

The key on the left (`ai`, `devops`, etc.) is the technical identifier.
The text on the right is the name displayed in the user interface.

To add a new category:

```json
"mobile": "Mobile Development"
```

 

#### ‣ How to Add a New Certificate

Each certificate is added as an object inside the `"certificates"` array.

Example structure:

```json
{
  "title": "Diction, Announcing and Presentation",
  "issuer": "Republic of Türkiye – Ministry of National Education",
  "date": "2026",
  "category": "effectiveCommunication",
  "img": "/assets/images/Certificates/diksiyon.png",
  "link": "#"
}
```

 

#### ‣ Field Descriptions

* `title` → Certificate name
* `issuer` → Issuing organization
* `date` → Year or date
* `category` → Category key defined above
* `img` → Certificate image path
* `link` → Certificate link (PDF, verification link, etc.)

 

#### ‣ Adding an Image

1. Add the certificate image to the following folder:

```
/assets/images/Certificates/
```

2. Specify the file path in the `img` field:

```json
"img": "/assets/images/Certificates/certificate-name.png"
```

 

#### ‣ Adding a New Certificate

Simply add a new object inside the `certificates` array:

```json
{
  "title": "Cloud Computing Fundamentals",
  "issuer": "ABC Academy",
  "date": "2025",
  "category": "cloudComputing",
  "img": "/assets/images/Certificates/cloud.png",
  "link": "https://certificate-link.com"
}
```

 

#### ‣ Important Rules

* The `category` value must be defined inside the `categories` object.
* A comma must be placed between each object.
* Do not add a comma after the last element.
* The image path must be written correctly.





## Home Page → Vision

This image shows which file provides the data for the **Vision** section on the Home Page.

<img width="1919" height="903" alt="vision-map" src="https://github.com/user-attachments/assets/bea35b68-ffe5-4b01-8e6e-55a422bc2f4c" />

This section is managed through the following file:

```
messages/vision/en.json
```

The large highlighted statements displayed on the Home Page are automatically retrieved from this file.

 

#### ‣ File Structure

```json
{
  "statements": [
    {
      "text": "I turn complex ideas into unforgettable digital experiences",
      "direction": "default"
    }
  ]
}
```

 

#### ‣ Statement Structure

Each statement is defined as an object inside the `"statements"` array.

Example:

```json
{
  "text": "I don’t just write code, I craft game-changing solutions",
  "direction": "right"
}
```

 

#### ‣ Field Descriptions

* `text` → The text displayed on the screen
* `direction` → Animation direction

 

#### ‣ Direction (Animation Types)

The `direction` field can take the following values:

* `"default"` → Standard entrance animation
* `"right"` → Entrance animation from the right
* `"down"` → Entrance animation from below

If an invalid value is entered, the animation may not function properly.

 

#### ‣ Adding a New Statement

To add a new highlighted statement, insert a new object with the same structure into the `statements` array:

```json
{
  "text": "Design is where creativity meets logic",
  "direction": "default"
}
```

 

#### ‣ Important Rules

* A comma must be placed between each object.
* Do not add a comma after the last element.
* The `direction` value must be valid.



## Home Page → Contact

This image shows which files provide the data for the **Contact** section on the Home Page.

<img width="1919" height="903" alt="contact-map" src="https://github.com/user-attachments/assets/c47d1635-8c01-4240-9abe-247564757954" />

This section is managed through two different files:

```
messages/en.json
```

and

```
data/contacts.ts
```

* `messages/en.json` → Text content (titles, form fields, messages)
* `data/contacts.ts` → Actual contact information and social media links

 

#### ‣ Text Content (`messages/en.json`)

The contact title, description, and form fields are managed from this file.

File structure:

```json
"contact": {
  "title": "Let's Work Together",
  "subtitle": "Got an idea or project? Let’s collaborate and turn your vision into reality.",
  "badge": "Contact Me",
  "form": {},
  "success": {},
  "info": {},
  "social": {}
}
```

 

#### ‣ Editing the Title and Description

```json
"title": "Get in Touch",
"subtitle": "Do you have an idea? Let’s bring it to life together."
```

 

#### ‣ Editing the Form Fields

```json
"form": {
  "name": {
    "label": "Name",
    "placeholder": "John Doe"
  },
  "email": {
    "label": "Email",
    "placeholder": "john@example.com"
  },
  "subject": {
    "label": "Subject",
    "placeholder": "Project Inquiry"
  },
  "message": {
    "label": "Message",
    "placeholder": "Tell me about your project..."
  },
  "submit": "Send Message",
  "sending": "Sending..."
}
```

All text values here can be freely modified.

 

#### ‣ Successful Submission Message

```json
"success": {
  "title": "Message Sent Successfully!",
  "message": "Thank you for reaching out. I'll get back to you as soon as possible."
}
```

 

#### ‣ Actual Contact Information (`data/contacts.ts`)

The real email, phone number, location, and social media links are stored in this file.

File structure:

```ts
export const contactData = {
  email: "example@gmail.com",
  phone: "+90 500 000 00 00",
  location: "Ankara, Türkiye",
  cvPath: "/assets/docs/cv.pdf",
  projectsPath: "/projects",
  socialLinks: []
}
```

 

#### ‣ Editing Email / Phone / Location

```ts
email: "yourmail@gmail.com",
phone: "+90 555 555 55 55",
location: "Ankara, Türkiye",
```

 

#### ‣ Social Media Links

Each social media account is added as an object inside the `socialLinks` array.

```ts
{
  name: "LinkedIn",
  icon: "Linkedin",
  href: "https://www.linkedin.com/in/username"
}
```

 

#### ‣ Field Descriptions

* `name` → Platform name
* `icon` → Icon name to be used
* `href` → Profile URL

To add a new social media account:

```ts
{
  name: "YouTube",
  icon: "Youtube",
  href: "https://youtube.com/@username"
}
```

 

#### ‣ Important Notes

* `messages/en.json` only controls text content.
* Actual contact information is stored in `data/contacts.ts`.
* The `icon` value must match the icon system used in the project.
* The TypeScript structure must not be broken (pay attention to commas and curly braces).



### Projects Page → Hero & Filter Section

This image shows which files provide the data for the **Projects Page**.

<img width="1919" height="903" alt="our-project-map" src="https://github.com/user-attachments/assets/8c915b07-3b69-4c88-be81-d087b036b70e" />

> How to add a new project will be explained in detail in the following sections.

This section is managed from the following file:

```
messages/projects/index/en.json
```

The page title, description text, search field texts, and category names are automatically retrieved from this file.

 

#### ‣ Hero Section (Header Area)

The title and description text at the top of the page are managed here.

Example structure:

```json
"hero": {
  "badge": "Portfolio",
  "title": "Our Projects",
  "subtitle": "Explore our portfolio of innovative solutions and creative works that drive success"
}
```

#### ‣ Fields

* `badge` → Small top label (e.g., Portfolio)
* `title` → Main title
* `subtitle` → Description text

 

#### ‣ Search and Filter Texts

The search field and filter texts come from the `search` object.

Example structure:

```json
"search": {
  "placeholder": "Search projects...",
  "filterButton": "Filters",
  "showingResults": "Showing",
  "project": "project",
  "projects": "projects"
}
```

#### ‣  Fields

* `placeholder` → Search box placeholder text
* `filterButton` → Filter button text
* `showingResults` → Result counter text (e.g., Showing 3 projects)
* `project` / `projects` → Singular and plural forms

 

#### ‣ Categories (Filter Buttons)

The category filter buttons at the top come from the `categories` object.

Example structure:

```json
"categories": {
  "all": "All",
  "webDevelopment": "Web Development",
  "mobileApp": "Mobile App",
  "design": "Design",
  "aiMl": "AI/ML",
  "blockchain": "Blockchain"
}
```

* **Left side (Key):** Technical value. Must exactly match the `category` field in project files.
* **Right side (Text):** The label displayed in the interface.

#### ‣  Adding a New Category

```json
"gameDevelopment": "Game Development"
```

⚠️ Important:
Projects that belong to this category must also have `"category": "gameDevelopment"`.

 
#### ‣  Important Rules

* The JSON structure must not be broken.
* Each line must be separated by a comma.
* There must not be a comma after the last element.
* Category keys must match project files exactly.

 

### How to Add a New Project

Follow the steps below to add a new project.

 

#### ‣ 1️⃣ Navigate to the Correct Folder

Project details are located in:

```
messages/projects/details
```

Inside this folder, there are language directories (e.g., `en`, `tr`).

You must create the new JSON file inside the language folder corresponding to your project language.

Example:

```
messages/projects/details/en/
```

 

#### ‣ 2️⃣ Create the File Name Correctly

The file name must follow this format:

```
index-projectname.json
```

Rules:

* First, write the project index number
* Add a hyphen `-`
* Write the project name without spaces
* Lowercase is recommended

#### ‣ Examples

```
12-nobadwords.json
13-portfolioai.json
14-mobilebankingapp.json
```

⚠️ Important:

* The project name must not contain spaces.
* Each project must have a unique index number.

 

#### ‣ 3️⃣ Add the JSON Content

After creating the file, copy and edit the following base structure:

```json
{
  "id": 13,
  "title": "Project Title",
  "subtitle": "Project Subtitle",
  "isFeatured": false,
  "description": "Project Description",
  "longDescription": "Project Long Description",
  "category": "Project Category",
  "tags": ["tag1", "tag2"],
  "image": "image link",
  "techLogos": ["techLogo1", "techLogo2"],
  "date": "2026-02",
  "duration": "4 months",
  "teamSize": 1,
  "role": "Your Role",
  "demoLink": null,
  "githubLink": null
}
```

To view available technology logo names:

```
data/techIcons.ts
```

 

#### ‣ Important Fields

‣ id

* Must be unique
* Recommended to match the file index number

‣ isFeatured

* `true` → Appears in Featured Projects on the Home Page
* `false` → Appears only on the Projects Page

‣ category

Must match one of the category keys defined in:

```
messages/projects/index/en.json
```

Example:

```json
"category": "aiMl"
```

 

#### ‣ technologies

Used to display detailed information about technologies used in the project.

```json
"technologies": [
  {
    "name": "Django & Python",
    "description": "Backend API with machine learning integration"
  }
]
```

‣ Purpose

* Lists main technologies used
* Shows a short description for each
* Appears as a separate section on the project detail page

‣ Rules

* `name` → Technology name
* `description` → Role of that technology in the project
* At least one entry is allowed
* Order determines display order

 

#### ‣ contentBlocks

Defines the main content of the project detail page.

Each block represents a different content type.

 

‣ type: 0 → Text Block

Used for long explanations.

```json
{
  "type": 0,
  "heading": "Project Overview",
  "subheading": "Building a Safer Digital Environment",
  "content": "Long description text..."
}
```

**Fields:**

* `heading` → Section title
* `subheading` → Subtitle
* `content` → Long description (`\n\n` for line breaks)

 

‣ type: 1 → Single Image Block

Used to display one large image.

```json
{
  "type": 1,
  "heading": "Platform Hero Section",
  "imageUrl": "https://...",
  "caption": "Image description"
}
```

**Fields:**

* `imageUrl` → Image link
* `caption` → Caption text

 

‣ type: 3 → Multiple Image Block

Used to display multiple images in a grid layout.

```json
{
  "type": 3,
  "heading": "Examples",
  "images": [
    {
      "url": "https://...",
      "alt": "Image alt text",
      "caption": "Image caption 1"
    }
  ]
}
```

**Fields:**

* `url` → Image link
* `alt` → Alternative text (SEO & accessibility)
* `caption` → Description

 

‣ type: 4 → Code Example Block

Used to display API or usage examples.

```json
{
  "type": 4,
  "heading": "Usage Example",
  "codeBlocks": [
    {
      "language": "javascript",
      "label": "Node.js",
      "code": "console.log('Hello');"
    }
  ],
  "defaultTab": 0
}
```

**Fields:**

* `language` → Programming language (for syntax highlighting)
* `label` → Tab title
* `code` → Code content
* `defaultTab` → Default open tab index

 

#### ‣ challenges

Lists technical challenges encountered in the project.

```json
"challenges": [
  "Ensuring real-time performance",
  "Multilingual model training"
]
```

 

#### ‣ solutions

Contains solutions corresponding to the challenges.

```json
"solutions": [
  "Implemented GPU-supported inference system",
  "Trained custom transformer models"
]
```

 

#### ‣ results

Displays measurable project outcomes.

```json
"results": [
  {
    "metric": "Accuracy",
    "value": "92.3%",
    "description": "Detection accuracy"
  }
]
```

**Fields:**

* `metric` → Metric name
* `value` → Result value
* `description` → Explanation

Recommended especially for corporate and professional projects.

 

#### ‣ testimonial

Used to display client or user feedback.

```json
"testimonial": {
  "text": "This project transformed our workflow...",
  "author": "Ahmed Al-Rashid",
  "position": "Community Manager"
}
```

**Fields:**

* `text` → Review text
* `author` → Reviewer name
* `position` → Reviewer position

 

#### ‣ Images

* Add images to the appropriate folder.
* Write the correct path in the `image` field.
* For content blocks, URL or local paths can be used.

 

#### ‣ Important Rules and Notes

* The JSON structure must never be broken.
* Do not add a comma after the last line.
* The `category` value must match the filter system.
* File names must not contain spaces.
* Index numbers must not be duplicated.
* `type` values are system-defined and must not be changed.
* Not all fields are mandatory, but filling detailed sections is recommended for a professional and rich project page.


## How to Add a New Language?

To add a new language to the system, you must carefully follow the steps below.

#### ‣ 1️⃣ Register the Language in the System

First, you need to define the language at the system level.

Open the following file:

```
data/systemLanguages.ts
```

Current structure:

```ts
export const systemLanguages = [
  { code: 'en', name: 'English', locale: 'en-US' },
] as const;
```

For example, if you want to add Arabic, add the following line to the `systemLanguages` array:

```ts
{ code: 'ar', name: 'العربية', locale: 'ar-SA' }
```

The final structure should look like this:

```ts
export const systemLanguages = [
  { code: 'en', name: 'English', locale: 'en-US' },
  { code: 'ar', name: 'العربية', locale: 'ar-SA' }
] as const;
```

#### ‣ 2️⃣ Create the Required Language Files

For the new language, you must create the corresponding JSON files inside the `messages` directory.

‣ You can paste the following command into your terminal to automatically generate all required files with the proper base structure. After the files are created, you only need to fill in the relevant fields.

> ⚠️ Before running the command, do not forget to assign the language code you want to add to the `LangCode` variable.





```pash

$LangCode = "<language-code>"

if (-not $LangCode) {
    Write-Host "Usage: First set the language code, then run the script" -ForegroundColor Yellow
    Write-Host '  $LangCode = "ar"' -ForegroundColor White
    exit 1
}

Write-Host ""
Write-Host "Creating files for language '$LangCode'..." -ForegroundColor Cyan
Write-Host ""

function Write-JsonFile {
    param ([string]$FilePath, [string]$Content)
    $Dir = Split-Path -Parent $FilePath
    if (-not (Test-Path $Dir)) { New-Item -ItemType Directory -Path $Dir -Force | Out-Null }
    if (Test-Path $FilePath) {
        Write-Host "Skipped (already exists): $FilePath" -ForegroundColor Yellow
        return
    }
    [System.IO.File]::WriteAllText((Resolve-Path $Dir).Path + "\" + (Split-Path -Leaf $FilePath), $Content, [System.Text.Encoding]::UTF8)
    Write-Host "Created: $FilePath" -ForegroundColor Green
}

Write-JsonFile "messages\$LangCode.json" '{
  "header": {
    "home": "", "stats": "", "services": "", "work": "", "projects": "",
    "resume": "", "about": "", "skills": "", "languages": "", "volunteering": "",
    "certificates": "", "contact": "", "startAProject": ""
  },
  "home": {
    "hero": {
      "greeting": "", "name": "", "titleLine1": "", "titleLine2": "",
      "description": "", "downloadCV": "", "viewWork": "", "follow": ""
    },
    "stats": {
      "title": "", "subtitle": "",
      "yearsLabel": "", "yearsDesc": "",
      "projectsLabel": "", "projectsDesc": "",
      "clientsLabel": "", "clientsDesc": "",
      "awardsLabel": "", "awardsDesc": "",
      "trustedBy": "", "yearsExp": "", "projects": "", "k": ""
    }
  },
  "contact": {
    "title": "", "subtitle": "", "badge": "",
    "form": {
      "name":    { "label": "", "placeholder": "" },
      "email":   { "label": "", "placeholder": "" },
      "subject": { "label": "", "placeholder": "" },
      "message": { "label": "", "placeholder": "" },
      "submit": "", "sending": ""
    },
    "success": { "title": "", "message": "" },
    "info": {
      "email":    { "title": "" },
      "phone":    { "title": "" },
      "location": { "title": "" }
    },
    "social": { "title": "" }
  },
  "loading": { "text": "" },
  "backToProjects": "", "technologiesUsed": "", "projectLink": "",
  "liveDemo": "", "sourceCode": "", "challenges": "", "solutions": "",
  "duration": "", "teamSize": "", "resultsImpact": "", "videoNotSupported": "",
  "client": "", "technologies": "", "date": ""
}'

Write-JsonFile "messages\certificates\$LangCode.json" '{
  "title": "", "subtitle": "", "certificatesCount": "", "viewCertificate": "", "of": "",
  "categories": {
    "ai": "", "dataScience": "", "cybersecurity": "", "php": "",
    "cloudComputing": "", "programming": "", "devops": "", "softSkills": "",
    "network": "", "effectiveCommunication": "", "trainingTrainers": ""
  },
  "certificates": [
    { "title": "", "issuer": "", "date": "", "category": "", "img": "", "link": "" },
    { "title": "", "issuer": "", "date": "", "category": "", "img": "", "link": "" },
    { "title": "", "issuer": "", "date": "", "category": "", "img": "", "link": "" }
  ]
}'

Write-JsonFile "messages\languages\$LangCode.json" '{
  "title": "", "subtitle": "",
  "levels": { "native": "", "professional": "", "intermediate": "" },
  "languages": [
    { "name": "", "nativeName": "", "level": "", "flag": "", "backward": "" },
    { "name": "", "nativeName": "", "level": "", "flag": "", "backward": "" },
    { "name": "", "nativeName": "", "level": "", "flag": "", "backward": "" }
  ]
}'

Write-JsonFile "messages\projects\index\$LangCode.json" '{
  "hero": { "badge": "", "title": "", "subtitle": "" },
  "search": {
    "placeholder": "", "filterButton": "", "showingResults": "", "project": "", "projects": ""
  },
  "categories": {
    "all": "", "webDevelopment": "", "mobileApp": "", "design": "", "aiMl": "", "blockchain": ""
  },
  "projectCard": { "technologiesUsed": "" },
  "noResults": { "title": "", "description": "", "clearButton": "" },
  "featuredProjects": {
    "title": "", "subtitle": "", "viewProject": "",
    "allProjects": {
      "title": "", "description": "", "button": "",
      "stats": { "projects": "", "technologies": "", "years": "" }
    }
  }
}'

Write-JsonFile "messages\resume\$LangCode.json" '{
  "title": "", "subtitle": "",
  "tabs": { "experience": "", "education": "" },
  "experience": [
    { "year": "", "title": "", "company": "" },
    { "year": "", "title": "", "company": "" },
    { "year": "", "title": "", "company": "" }
  ],
  "education": [
    { "year": "", "title": "", "company": "" },
    { "year": "", "title": "", "company": "" },
    { "year": "", "title": "", "company": "" }
  ]
}'

Write-JsonFile "messages\services\$LangCode.json" '{
  "title": "", "subtitle": "",
  "items": [
    { "title": "", "description": "", "icon": "" },
    { "title": "", "description": "", "icon": "" },
    { "title": "", "description": "", "icon": "" }
  ]
}'

Write-JsonFile "messages\skills\$LangCode.json" '{
  "title": "", "subtitle": "",
  "categories": {
    "programmingLanguages": "", "frameworks": "", "concepts": "", "databases": ""
  },
  "skills": {
    "programmingLanguages": [ { "name": "" }, { "name": "" } ],
    "frameworks":           [ { "name": "" }, { "name": "" } ],
    "concepts":             [ { "name": "" }, { "name": "" } ],
    "databases":            [ { "name": "" }, { "name": "" } ]
  }
}'

Write-JsonFile "messages\vision\$LangCode.json" '{
  "statements": [
    { "text": "", "direction": "" },
    { "text": "", "direction": "" },
    { "text": "", "direction": "" }
  ]
}'

Write-JsonFile "messages\volunteering\$LangCode.json" '{
  "title": "",
  "volunteering": [
    { "role": "", "organization": "", "event": "", "location": "", "date": "", "description": "", "image": "" },
    { "role": "", "organization": "", "event": "", "location": "", "date": "", "description": "", "image": "" },
    { "role": "", "organization": "", "event": "", "location": "", "date": "", "description": "", "image": "" }
  ]
}'

Write-JsonFile "messages\projects\details\$LangCode\1-example-project.json" '{
  "id": 0,
  "title": "", "subtitle": "", "isFeatured": false,
  "description": "", "longDescription": "", "category": "",
  "tags": [ "", "", "" ],
  "image": "",
  "techLogos": [ "", "", "" ],
  "date": "", "duration": "", "teamSize": 0, "role": "",
  "demoLink": "", "githubLink": null,
  "technologies": [
    { "name": "", "description": "" },
    { "name": "", "description": "" },
    { "name": "", "description": "" }
  ],
  "contentBlocks": [
    { "type": 0, "heading": "", "subheading": "", "content": "" },
    { "type": 1, "heading": "", "imageUrl": "", "caption": "" },
    { "type": 2, "heading": "", "videoUrl": "", "posterUrl": "", "caption": "" },
    { "type": 3, "heading": "", "images": [
      { "url": "", "alt": "", "caption": "" },
      { "url": "", "alt": "", "caption": "" },
      { "url": "", "alt": "", "caption": "" }
    ]},
    { "type": 4, "heading": "", "codeBlocks": [
      { "language": "", "label": "", "code": "" },
      { "language": "", "label": "", "code": "" },
      { "language": "", "label": "", "code": "" }
    ], "defaultTab": 0 }
  ],
  "challenges": [ "", "", "" ],
  "solutions":  [ "", "", "" ],
  "results": [
    { "metric": "", "value": "", "description": "" },
    { "metric": "", "value": "", "description": "" },
    { "metric": "", "value": "", "description": "" }
  ],
  "testimonial": { "text": "", "author": "", "position": "" }
}'

Write-Host ""
Write-Host "━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━" -ForegroundColor Cyan
Write-Host "All files have been successfully created!" -ForegroundColor Green
Write-Host ""
Write-Host "Final step — add the following line to data/systemLanguages.ts:" -ForegroundColor Yellow
Write-Host "  { code: '$LangCode', name: 'Language Name', locale: '$LangCode-XX' }" -ForegroundColor White
Write-Host "━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━" -ForegroundColor Cyan
```



If you want to write it manually, the following files must be created:

```
messages/ar.json
messages/certificates/ar.json
messages/languages/ar.json
messages/projects/index/ar.json
messages/services/ar.json
messages/skills/ar.json
messages/vision/ar.json
messages/volunteering/ar.json
```

#### ‣ 3️⃣ Create a Language Folder for Project Details

A separate folder is required for project details.

Go to the following directory:

```
messages/projects/details
```

For English, the structure usually looks like this:

```
messages/projects/details/en/
```

For the new language:

```
messages/projects/details/ar/
```

Create this folder.

#### ‣ Add Project Translations

If English projects already exist in the system (inside the `details/en` folder), you must create the Arabic versions of the same files.

Example:

```
messages/projects/details/en/12-nobadwords.json
```

Arabic version:

```
messages/projects/details/ar/12-nobadwords.json
```

The content must keep the same structure, with only the texts translated into Arabic.

#### ‣ Important Rules

* The `code` value must match the folder name.
* All message files must be created.
* The language will not work unless the project details folder is created.
* The JSON structure must not be modified.
* No required file should be missing.

 

#### ‣ Structure inside messages/[language-code].json:

```json
{
  "header": {
    "home": "",
    "stats": "",
    "services": "",
    "work": "",
    "projects": "",
    "resume": "",
    "about": "",
    "skills": "",
    "languages": "",
    "volunteering": "",
    "certificates": "",
    "contact": "",
    "startAProject": ""
  },
  "home": {
    "hero": {
      "greeting": "",
      "name": "",
      "titleLine1": "",
      "titleLine2": "",
      "description": "",
      "downloadCV": "",
      "viewWork": "",
      "follow": ""
    },
    "stats": {
      "title": "",
      "subtitle": "",
      "yearsLabel": "",
      "yearsDesc": "",
      "projectsLabel": "",
      "projectsDesc": "",
      "clientsLabel": "",
      "clientsDesc": "",
      "awardsLabel": "",
      "awardsDesc": "",
      "trustedBy": "",
      "yearsExp": "",
      "projects": "",
      "k": ""
    }
  },
  "contact": {
    "title": "",
    "subtitle": "",
    "badge": "",
    "form": {
      "name": {
        "label": "",
        "placeholder": ""
      },
      "email": {
        "label": "",
        "placeholder": ""
      },
      "subject": {
        "label": "",
        "placeholder": ""
      },
      "message": {
        "label": "",
        "placeholder": ""
      },
      "submit": "",
      "sending": ""
    },
    "success": {
      "title": "",
      "message": ""
    },
    "info": {
      "email": {
        "title": ""
      },
      "phone": {
        "title": ""
      },
      "location": {
        "title": ""
      }
    },
    "social": {
      "title": ""
    }
  },
  "loading": {
    "text": ""
  },
  "backToProjects": "",
  "technologiesUsed": "",
  "projectLink": "",
  "liveDemo": "",
  "sourceCode": "",
  "challenges": "",
  "solutions": "",
  "duration": "",
  "teamSize": "",
  "resultsImpact": "",
  "videoNotSupported": "",
  "client": "",
  "technologies": "",
  "date": ""
}
```

 

#### ‣ Structure inside messages/certificates/[language-code].json:

```json
{
  "title": "",
  "subtitle": "",
  "certificatesCount": "",
  "viewCertificate": "",
  "of": "",
  "categories": {
    "ai": "",
    "dataScience": "",
    "cybersecurity": "",
    "php": "",
    "cloudComputing": "",
    "programming": "",
    "devops": "",
    "softSkills": "",
    "network": "",
    "effectiveCommunication": "",
    "trainingTrainers": ""
  },
  "certificates": [
    {
      "title": "",
      "issuer": "",
      "date": "",
      "category": "",
      "img": "",
      "link": ""
    },
    {
      "title": "",
      "issuer": "",
      "date": "",
      "category": "",
      "img": "",
      "link": ""
    }
  ]
}
```

 

#### ‣ Structure inside messages/languages/[language-code].json:

```json
{
  "title": "",
  "subtitle": "",
  "levels": {
    "native": "",
    "professional": "",
    "intermediate": ""
  },
  "languages": [
    {
      "name": "",
      "nativeName": "",
      "level": "",
      "flag": "",
      "backward": ""
    },
    {
      "name": "",
      "nativeName": "",
      "level": "",
      "flag": "",
      "backward": ""
    },
    {
      "name": "",
      "nativeName": "",
      "level": "",
      "flag": "",
      "backward": ""
    }
  ]
}
```

#### ‣ Structure inside messages/projects/details/[dil kodu]/[index-projcetname].json:


```json
{
  "id": 0,
  "title": "",
  "subtitle": "",
  "isFeatured": false,
  "description": "",
  "longDescription": "",
  "category": "",
  "tags": [
    "",
    "",
    ""
  ],
  "image": "",
  "techLogos": [
    "",
    "",
    ""
  ],
  "date": "",
  "duration": "",
  "teamSize": 0,
  "role": "",
  "demoLink": "",
  "githubLink": null,
  "technologies": [
    {
      "name": "",
      "description": ""
    },
    {
      "name": "",
      "description": ""
    },
    {
      "name": "",
      "description": ""
    }
  ],
  "contentBlocks": [
    {
      "type": 0,
      "heading": "",
      "subheading": "",
      "content": ""
    },
    {
      "type": 1,
      "heading": "",
      "imageUrl": "",
      "caption": ""
    },
    {
      "type": 2,
      "heading": "",
      "videoUrl": "",
      "posterUrl": "",
      "caption": ""
    },
    {
      "type": 3,
      "heading": "",
      "images": [
        {
          "url": "",
          "alt": "",
          "caption": ""
        },
        {
          "url": "",
          "alt": "",
          "caption": ""
        },
        {
          "url": "",
          "alt": "",
          "caption": ""
        }
      ]
    },
    {
      "type": 4,
      "heading": "",
      "codeBlocks": [
        {
          "language": "",
          "label": "",
          "code": ""
        },
        {
          "language": "",
          "label": "",
          "code": ""
        },
        {
          "language": "",
          "label": "",
          "code": ""
        }
      ],
      "defaultTab": 0
    }
  ],
  "challenges": [
    "",
    "",
    ""
  ],
  "solutions": [
    "",
    "",
    ""
  ],
  "results": [
    {
      "metric": "",
      "value": "",
      "description": ""
    },
    {
      "metric": "",
      "value": "",
      "description": ""
    },
    {
      "metric": "",
      "value": "",
      "description": ""
    }
  ],
  "testimonial": {
    "text": "",
    "author": "",
    "position": ""
  }
}
```

#### ‣ Structure inside messages/projects/index/[dil kodu].json:

```json
{
  "hero": {
    "badge": "",
    "title": "",
    "subtitle": ""
  },
  "search": {
    "placeholder": "",
    "filterButton": "",
    "showingResults": "",
    "project": "",
    "projects": ""
  },
  "categories": {
    "all": "",
    "webDevelopment": "",
    "mobileApp": "",
    "design": "",
    "aiMl": "",
    "blockchain": ""
  },
  "projectCard": {
    "technologiesUsed": ""
  },
  "noResults": {
    "title": "",
    "description": "",
    "clearButton": ""
  },
  "featuredProjects": {
    "title": "",
    "subtitle": "",
    "viewProject": "",
    "allProjects": {
      "title": "",
      "description": "",
      "button": "",
      "stats": {
        "projects": "",
        "technologies": "",
        "years": ""
      }
    }
  }
}
```



#### ‣ Structure inside messages/resume/[dil kodu].json.json:
```json
{
  "title": "",
  "subtitle": "",
  "tabs": {
    "experience": "",
    "education": ""
  },
  "experience": [
    {
      "year": "",
      "title": "",
      "company": ""
    },
    {
      "year": "",
      "title": "",
      "company": ""
    },
    {
      "year": "",
      "title": "",
      "company": ""
    }
  ],
  "education": [
    {
      "year": "",
      "title": "",
      "company": ""
    },
    {
      "year": "",
      "title": "",
      "company": ""
    },
    {
      "year": "",
      "title": "",
      "company": ""
    }
  ]
}
```


#### ‣ Structure inside messages/services/[dil kodu].json:

```json
{
  "title": "",
  "subtitle": "",
  "items": [
    {
      "title": "",
      "description": "",
      "icon": ""
    },
    {
      "title": "",
      "description": "",
      "icon": ""
    },
    {
      "title": "",
      "description": "",
      "icon": ""
    }
  ]
}
```

#### ‣ Structure inside messages/skills/[dil kodu].json:
```json
{
  "title": "",
  "subtitle": "",
  "categories": {
    "programmingLanguages": "",
    "frameworks": "",
    "concepts": "",
    "databases": ""
  },
  "skills": {
    "programmingLanguages": [
      { "name": "" },
      { "name": "" }
    ],
    "frameworks": [
      { "name": "" },
      { "name": "" }
    ],
    "concepts": [
      { "name": "" },
      { "name": "" }
    ],
    "databases": [
      { "name": "" },
      { "name": "" }
    ]
  }
}
```
#### ‣ Structure inside messages/vision/[dil kodu].json:
```json
{
  "statements": [
    {
      "text": "",
      "direction": ""
    },
    {
      "text": "",
      "direction": ""
    },
    {
      "text": "",
      "direction": ""
    }
  ]
}
```
#### ‣ Structure inside messages/volunteering/[dil kodu].json:

```json
{
  "title": "",
  "volunteering": [
    {
      "role": "",
      "organization": "",
      "event": "",
      "location": "",
      "date": "",
      "description": "",
      "image": ""
    },
    {
      "role": "",
      "organization": "",
      "event": "",
      "location": "",
      "date": "",
      "description": "",
      "image": ""
    },
    {
      "role": "",
      "organization": "",
      "event": "",
      "location": "",
      "date": "",
      "description": "",
      "image": ""
    }
  ]
}
```















