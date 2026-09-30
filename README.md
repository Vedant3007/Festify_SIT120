# Festify — Smart Celebration Studio

 > **Celebrate more. Plan less.**

 Festify is a responsive celebration planning web application developed for **SIT120 — Intro to Responsive Web Apps** at **Deakin University**.

 The project transforms the original Festify wireframes and responsive form designs into a functional **Vue 3 + Vite** application using a component-based architecture.

---

 ## Project Overview

 Festify is designed to make celebration planning simpler, more organised, and more efficient.

 Users can:

 - Explore different celebration packages
- Learn about the Festify concept
- View available celebration services
- Complete a personalised Celebration Planner
- Receive inline form validation and feedback
- Submit their celebration requirements
- View a submission acknowledgement

 The application demonstrates responsive web development and core Vue 3 concepts, including **reusable components, props, custom events, two-way data binding, conditional rendering, dynamic rendering, and reactive state management**.

---

 ## Features

 - Responsive desktop, tablet, and mobile layouts
- Multi-page-style navigation
- Home page with Festify introduction and features
- Celebration packages page
- Our Story page
- Interactive Celebration Planner
- Form validation with inline feedback
- Submission acknowledgement
- Parent-child component communication
- Reusable Vue components
- Dynamic form options
- Responsive form layouts
- Accessible focus states
- Production build using Vite
- Deployment to the Deakin University student web server

---

 ## Technologies Used

 | Technology | Purpose |
| --- | --- |
| **Vue 3** | Front-end framework |
| **Vite** | Development server and build tool |
| **JavaScript** | Application logic |
| **HTML5** | Page structure |
| **CSS3** | Styling and responsive design |
| **Flexbox** | Flexible layouts |
| **CSS Grid** | Structured layouts |
| **Media Queries** | Responsive behaviour |
| **GitHub** | Version control and repository hosting |

---

 ## Vue 3 Features Demonstrated

 ### Single File Components

 The application is separated into reusable Vue Single File Components:

```
App.vue
AppHeader.vue
AppFooter.vue
HomeView.vue
PackagesView.vue
AboutView.vue
ContactForm.vue
```

 Each component has a specific responsibility, making the application easier to maintain and extend.

 ### Props

 Props are used to pass data and configuration from the parent `App.vue` component to `ContactForm.vue`.

 The form receives:

 - Initial form data
- Form configuration

 ### Emits and Custom Events

 `ContactForm.vue` uses `defineEmits()` to send completed form data back to `App.vue` through the custom `submit-form` event.

 The parent component listens for this event and stores the submitted data for the acknowledgement card.

 ### v-model

 The Celebration Planner demonstrates two-way data binding using `v-model`.

 The form includes:

 - Text inputs
- Email input
- Telephone input
- Date input
- Numeric input
- Radio buttons
- Select fields
- Checkbox selections
- Textarea

 ### v-model.number

 The guest count field uses:

```
v-model.number
```

 This converts the entered guest count into a numeric value.

 ### Dynamic Rendering with v-for

 Dropdown and checkbox options are generated dynamically using `v-for`.

 This reduces repetitive HTML and keeps the form options organised and reusable.

 ### Conditional Rendering

 Vue conditional rendering is used for:

 - Validation messages
- Success messages
- Form feedback
- Navigation between application views
- Submission acknowledgement

---

 ## Application Structure

```
my-vue-website/
│
├── public/
│   ├── festify1.jpg
│   ├── festify2.jpg
│   ├── packages1.jpg
│   ├── packages2.jpg
│   └── packages3.jpg
│
├── src/
│   ├── assets/
│   │   └── styles.css
│   │
│   ├── components/
│   │   ├── AppHeader.vue
│   │   ├── AppFooter.vue
│   │   ├── HomeView.vue
│   │   ├── PackagesView.vue
│   │   ├── AboutView.vue
│   │   └── ContactForm.vue
│   │
│   ├── App.vue
│   └── main.js
│
├── .gitignore
├── index.html
├── package.json
├── package-lock.json
├── vite.config.js
└── README.md
```

---

 ## Main Components

 ### App.vue

 The main parent component responsible for:

 - Managing the current application view
- Handling navigation events
- Passing initial form data to the planner
- Receiving submitted form data
- Displaying the persistent acknowledgement card

 ### AppHeader.vue

 Provides the main navigation and Festify branding.

 It communicates navigation changes to `App.vue` using a custom `navigate` event.

 ### AppFooter.vue

 Provides the footer content and additional navigation links.

 ### HomeView.vue

 Introduces Festify and presents:

 - Hero section
- Festify features
- Planning process
- Popular packages
- Calls to action

 ### PackagesView.vue

 Displays the available celebration packages and their information.

 ### AboutView.vue

 Explains the purpose and concept behind Festify and presents the principles behind the application.

 ### ContactForm.vue

 Provides the interactive **Celebration Planner**.

 It includes:

 - Event details
- Style and preferences
- Budget information
- Contact details
- Form validation
- Custom events
- Form reset functionality
- Successful submission feedback

---

 ## Celebration Planner

 The Celebration Planner collects information across several sections.

 ### Event Details

 - Event type
- Event date
- Number of guests
- Location type

 ### Style & Preferences

 - Preferred style
- Preferred colour theme
- Required products and services

 ### Budget

 - Budget range
- Additional requirements

 ### Contact Details

 - Full name
- Email address
- Mobile number

---

 ## Form Validation

 The application provides inline validation feedback for invalid or incomplete fields.

 Validation includes:

 - Missing event type
- Invalid or missing event date
- Invalid guest count
- Missing location type
- Missing style
- Missing colour theme
- No requirements selected
- Missing budget
- Invalid name
- Invalid email address
- Invalid mobile number

 Successful fields can also provide positive feedback where appropriate.

---

 ## Submission Workflow

 The form uses a parent-child communication workflow:

```
User completes form
        ↓
ContactForm.vue validates data
        ↓
ContactForm.vue emits submit-form
        ↓
App.vue receives submitted data
        ↓
App.vue stores submitted data
        ↓
Acknowledgement card is displayed
        ↓
ContactForm.vue resets its local form
        ↓
Acknowledgement remains visible
```

 This demonstrates how state can be managed by the parent component while the child component manages its own form interaction.

---

 ## Responsive Design

 Festify follows a **mobile-first responsive design approach**.

 The interface uses:

 - CSS Flexbox
- CSS Grid
- Responsive media queries
- Flexible containers
- Responsive typography
- Flexible images
- Mobile-friendly form layouts
- Responsive navigation
- Accessible focus states

 The application was designed and tested across:

 - **Desktop**
- **Tablet**
- **Mobile**

---

 ## Visual Design

 Festify uses a modern visual style based around:

 - **Navy**
- **Lavender**
- **Coral**
- **White**
- **Light neutral backgrounds**

 ### Typography

 - **Poppins** — headings
- **Inter** — body text

 The design focuses on:

 - Clear visual hierarchy
- Consistent spacing
- Reusable components
- Responsive layouts
- Accessible interaction states
- Clean and modern presentation

---

 ## Running the Project Locally

 ### 1\. Clone the Repository

```
git clone https://github.com/Vedant3007/Festify_SIT120
```

 ### 2\. Navigate to the Project Directory

```
cd my-vue-website
```

 ### 3\. Install Dependencies

```
npm install
```

 ### 4\. Start the Development Server

```
npm run dev
```

 Vite will provide a local development URL in the terminal.

---

 ## Production Build

 To create a production build:

```
npm run build
```

 The compiled production files are generated inside:

```
dist/
```

 The production build contains the compiled HTML, CSS, JavaScript, and public assets required to deploy the application.

---

 ## Deployment

 The production build was deployed to the **Deakin University student web server** for assessment.

 The deployed version uses the contents of the generated `dist/` directory.

---

 ## Academic Context

 | Detail | Information |
| --- | --- |
| **Unit** | SIT120 - Intro to Responsive Web Apps |
| **Assessment** | Task 9.3D |
| **University** | Deakin University |
| **Degree** | Bachelor of Computer Science |
| **Project** | Festify - Smart Celebration Studio |

Festify was developed as an academic project to demonstrate responsive web development and Vue 3 application development.

---

 ## Learning Outcomes

 Through this project, the development process demonstrated understanding of:

 - Responsive web design
- Vue 3 component architecture
- Single File Components
- Props
- Emits and custom events
- Two-way data binding
- Form handling and validation
- Reactive state management
- Parent-child communication
- Dynamic rendering using `v-for`
- Conditional rendering
- Vite development and production builds
- Web application deployment

---

 ## Author

 **Vedant Patel**

 Bachelor of Computer Science\
 Deakin University

---

 ## Project Status

 **Completed — SIT120 Task 9.3D**

 The application has been built, tested, production-built with Vite, and deployed for assessment.

---

 ## License

 This project was developed for **educational purposes** as part of the **Deakin University SIT120 — Intro to Responsive Web Apps** unit.
