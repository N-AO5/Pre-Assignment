
- [Jira](#jira)
  - [Agile methodology](#agile-methodology)
  - [Jira terms](#jira-terms)
  - [Jira interface](#jira-interface)
  - [Team managed projects - no jira admin needed](#team-managed-projects---no-jira-admin-needed)
  - [Company managed projects - jira admin needed](#company-managed-projects---jira-admin-needed)
  - [Company-Managed Project Administration](#company-managed-project-administration)
- [Confluence](#confluence)
  - [Versions of Confluence](#versions-of-confluence)
  - [What is Confluence](#what-is-confluence)
  - [Confluence Terms You Need to Know](#confluence-terms-you-need-to-know)
  - [Understanding Personal Spaces and Team Spaces](#understanding-personal-spaces-and-team-spaces)
    - [Creating a Personal Space](#creating-a-personal-space)
      - [Navigating our Personal Space](#navigating-our-personal-space)
      - [Creating Pages in our Personal Spaces](#creating-pages-in-our-personal-spaces)
      - [Controlling who can see our Personal Spaces](#controlling-who-can-see-our-personal-spaces)
      - [Deleting a Personal Space](#deleting-a-personal-space)
    - [Creating and Navigating Pages in a Team Space](#creating-and-navigating-pages-in-a-team-space)
      - [Page Drafts and Unpublished Versions](#page-drafts-and-unpublished-versions)
      - [Editing an Existing Page](#editing-an-existing-page)
      - [Setting a New Home page](#setting-a-new-home-page)
      - [Overview of Space Settings](#overview-of-space-settings)
      - [Getting to Pages Quickly with Stars](#getting-to-pages-quickly-with-stars)
      - [Using the Watch Page Feature](#using-the-watch-page-feature)
      - [Task Management in Confluence](#task-management-in-confluence)
      - [How Blogs Work](#how-blogs-work)
      - [Importing Word documents](#importing-word-documents)
      - [Exporting Pages out of Confluence](#exporting-pages-out-of-confluence)
      - [Using the Confluence Mobile app](#using-the-confluence-mobile-app)
  - [Managing Team Spaces](#managing-team-spaces)
    - [Collaborative Editing](#collaborative-editing)
    - [Sharing Pages with our Team](#sharing-pages-with-our-team)
    - [Working with Teams in Confluence](#working-with-teams-in-confluence)
    - [Managing Files in our Space](#managing-files-in-our-space)
    - [Page Restrictions](#page-restrictions)
  - [Administrating Confluence](#administrating-confluence)
    - [User Management](#user-management)
    - [User Management Overview](#user-management-overview)
    - [Working with Groups](#working-with-groups)
    - [Controlling User Permissions in Confluence](#controlling-user-permissions-in-confluence)
    - [Creating New Templates](#creating-new-templates)
    - [Using JIRA and Confluence](#using-jira-and-confluence)
    - [Archiving and Deleting Spaces and Pages](#archiving-and-deleting-spaces-and-pages)
    - [Exporting and Space Backups](#exporting-and-space-backups)

# Jira

Jira uses AGILE

## Agile methodology  

A methodology that promotes adaptive planning, evolutionary development, early delivery, continuous improvement and encourages rapid and flexible response to change.

Agile can be SCUM or KANBAN 
Kanban doesn't use sprints - a set time to complete a set of tasks


## Jira terms
projects = containers for issues
issues = containers for fields (epics, stories, bugs)
fields = hold all your data (description, summary, due date etc)

story = user story as a person, a goal and a reason (non-technical)
epic = multiple stories to make up one goal

## Jira interface

your work = main dashboard
filters = saved searches
dashboards = customized with all organization projects
apps = added functionalities 

## Team managed projects - no jira admin needed
- project scope entities 
- fast and easy to set up and maintain

## Company managed projects - jira admin needed
- global entities
- more complex to set up and maintain 
- can have/see as many boards as you want in one lace (scum or kanban)

- neither can be switched between each other

## Company-Managed Project Administration

1. **Accessing Project Settings**:
   - Find project settings at the bottom of the left menu.
   - Administrative permissions for individual projects differ from overall Jira admin permissions.

2. **Project Details**:
   - Modify the project name and key (key must be unique).
   - Changing the key triggers Jira to reindex issues but preserves old URLs via forwarding.
   - **Project Lead**: The default assignee for unassigned issues.

3. **People Management**:
   - Free Jira plan doesn’t allow user role control at the project level.
   - Project administrators can manage users and assign roles (e.g., admins for specific projects).

4. **Automation**:
   - Set up automation rules (e.g., closing an epic when all stories in it are closed).

5. **Feature Settings**:
   - Turn on/off features like roadmap or code integration based on project needs.

6. **Summary**:
   - A summary view of settings like screens, workflows, and customization options set by the project template.

7. **Issue Types and Layout**:
   - Customize issue types, remove unwanted types (e.g., bugs), and control field layouts for different issue types using screens.

8. **Utilities & Permissions**:
   - Admin access required for some configurations shared across multiple projects.
   - **Workflow**: Define statuses and transitions.
   - **Fields**: Control fields visible on issues.

9. **Components & Integration**:
   - Use components to group issues (e.g., payment processing in a website project).
   - Integrate tools like Bitbucket, GitHub, and Ops Genie.

10. **Permissions & Issue Security**:
    - Set who can view and manage issues, manage sprints, and control issue visibility with security schemes.

11. **Notifications**:
    - Default notification scheme sends alerts to watchers and assignees when issues are created.

12. **Additional Features**:
    - **Issue Collectors**: Create forms for customers to report issues, which automatically create Jira issues.
    - **Slack Integration**: Link Jira issues and notifications to Slack channels.

# Confluence

## Versions of Confluence

**Summary: Confluence Versions and Licenses**

- **Version Differences**: Confluence may look different depending on the version used by your organization. Core concepts remain consistent across versions, but features and interface may vary.
  
- **Licenses and Updates**: The version of Confluence is often determined by the license your organization holds, which affects how often the software is updated. There are three main licenses:
  - **Confluence Cloud**: A SaaS version where updates are automatically handled by Atlassian.
  - **Confluence Server & Data Center**: Installed locally at your organization. Server is being phased out, with Data Center being the focus for new features.
  
- **Confluence Cloud Benefits**: No need to manage installations, automatic updates, and no concern about version updates—your instance is always the latest version.

- **Third-Party Apps**: While you can extend Confluence with third-party apps from the Atlassian Marketplace, this course will not use them, focusing solely on the core features of Confluence.

- **Version for the Course**: The course uses Confluence Cloud (version 7.3 as of recording). If your organization uses a different version (Server or Data Center), you may notice slight differences.

## What is Confluence


- **What is Confluence?**  
  Confluence is a wiki application developed by Atlassian, designed for collaborative editing via a web browser. It allows users to work together on documents, processes, and data without needing special software.

- **Confluence vs. JIRA**  
  - **Confluence**: Acts as a digital brain for an organization, where information (such as documents, workflows, processes, and data) is stored. It is not primarily for storing files (like in Google Drive), but rather for knowledge sharing and documentation.
  - **JIRA**: Focuses on tracking projects and issues, such as bugs, features, and progress for ongoing projects. It is used to manage and track the development lifecycle, like app development.
  
- **Use Case Examples**:  
  - In an app development scenario, **JIRA** tracks the progress of tasks (e.g., front-end and back-end development), while **Confluence** stores related documentation, processes, and standards (e.g., coding conventions or logo usage).
  - Once an app version is released, **JIRA** tracks the status of tasks, while **Confluence** can be used to document the change log or knowledge base for users.

## Confluence Terms You Need to Know

- **Confluence Terms Overview**:
  - **Pages**: These are where all content, like text, images, tables, attachments, and macros, are stored.
  - **Macros**: Used to add dynamic content to pages, such as a Table of Contents or live JIRA issues that automatically update.
  - **Spaces**: Containers for pages. Similar to projects in JIRA, spaces help organize pages and manage permissions for access. 

- **Navigating Confluence Interface**:
  - **Home Page**: Displays recent spaces, pages, and updates across the organization.
  - **Navigation Bar**: Located at the top, it includes features such as an **app switcher** (for switching between Atlassian products like JIRA and Confluence), **spaces**, **recent pages**, **people** (for managing users), and **apps** (for adding add-ons). 
  - **Create Button**: To create new pages, with a keyboard shortcut (C).
  - **Search**: To find content within Confluence, with restricted content excluded from search results.
  - **Notifications**: Alerts you to updates such as comments or mentions in Confluence.
  - **Help**: Provides access to Atlassian's documentation.
  - **Settings**: For administrators to manage overall Confluence settings.
  - **Profile**: For personal account settings like password changes or profile pictures.

- **Interface Tips**:
  - **Customization**: The interface may vary depending on whether you are using an updated version of Confluence or an older one. The navigation moved from the left to the top in a 2020 update.
  - **Productivity**: The navigation and features are designed to streamline workflow, helping users quickly access and manage their Confluence spaces and pages.

##  Understanding Personal Spaces and Team Spaces

- **Spaces in Confluence**: 
  - **Definition**: Spaces are organizational containers for content in Confluence, similar to drawers in a filing cabinet. Each space can hold various types of content such as documents, images, and processes, and can be locked to control access.
  - **Pages**: The content within spaces is stored on pages. For example, a space like "Website Documentation" could include pages for the website's interface overview, FAQs, and JIRA issues using macros.

- **Types of Spaces**:
  - **Personal Spaces**: These are individual spaces where users can have full control over the content. They are typically used as staging areas for content before it's shared with a team or moved to a Team Space.
  - **Team Spaces**: These are meant for collaborative work across teams or the entire organization. While access can be controlled, they are designed to be used by multiple people and managed by administrators.

- **Key Differences**:
  - **Intent**: Team Spaces are meant for shared use by a team or the organization, while Personal Spaces are for individual use.
  - **Content**: Both space types can contain similar content (pages with text, images, etc.), but the primary distinction lies in their intended audience and purpose.

### Creating a Personal Space

- **Creating a Personal Space**: 
  - To create a Personal Space in Confluence, simply click "Add Personal Space" in the top right corner.
  - The space is automatically named after the user, but you can change it if desired.
  - After clicking "Create," the Personal Space is set up.

- **Accessing Your Personal Space**: 
  - To revisit your Personal Space, go to the Home page and find your Personal Space in the top right corner.

#### Navigating our Personal Space

**Summary: Navigating Your Personal Space in Confluence**

- **Navigation Panel**:
  - On the left-hand side of your Personal Space, you can expand or collapse the navigation panel using the icon or a keyboard shortcut.
  - The panel is resizable for better visibility.

- **Overview**:
  - The "Overview" is the default home page of your Personal Space, and it functions like any other page in Confluence. You can customize it using course techniques.

- **Blog**:
  - The "Blog" section allows you to create date-specific pages.

- **Space Settings**:
  - In the "Space Settings," you can manage administrative settings for your Personal Space, as you have admin permissions for it.

- **Shortcuts**:
  - You can add shortcuts to frequently used links, such as internal email or external project sites.

- **Pages**:
  - Confluence automatically creates sample pages for your Personal Space. These pages may use different templates and contain varying types of content.

####  Creating Pages in our Personal Spaces

- **Creating a Page**:
  - To create a page, click the "Create" button or use the keyboard shortcut (C).
  - This opens the page editor, where you can add a title and content (e.g., "Welcome to my Personal Space").

- **Templates**:
  - The page editor offers various templates, which can be previewed and selected for easier content creation.
  - Templates like a To-Do List pre-populate information, speeding up the process.

- **Managing Templates**:
  - Templates can be filtered or promoted for quicker access.
  - In "Space Settings," templates can be rearranged or disabled, reducing clutter and streamlining the page creation process.

- **Tips**:
  - If you frequently use a specific template, you can promote it to the top of the list for faster access.
  - Disabling unused templates in "Space Settings" makes the template list shorter and more manageable.

#### Controlling who can see our Personal Spaces

- **Default Access**: By default, everyone in the organization can view your Personal Space in Confluence. However, you may want to limit access if you're using it for drafts or personal content.

- **Changing Permissions**:
  - To adjust who can access your Personal Space, go to *Space Settings* > *Space Permissions*.
  - Permissions are managed through **Groups**, **Individual Users**, or **Anonymous Access**.
  - Groups allow administrators to control access for multiple users (e.g., marketing team).
  - **Anonymous Access** allows anyone on the internet to view the space, but it's recommended to keep this off unless necessary.

- **Disabling Access**: 
  - To restrict access, uncheck the groups (like *Confluence Users*) that can view the space and save the changes.
  - After saving, users in the unchecked groups won't see your Personal Space.

- **Testing Permissions**: 
  - Log in as a different user to see if the changes took effect. Once you disable access for *Confluence Users*, they won't be able to view the space unless specific permissions are granted.

#### Deleting a Personal Space

- **Deleting the Space**: To delete your Personal Space, go to *Space Settings* > *Manage Space* > *Delete Space*. 
  - Once deleted, all data within the space, including pages and content, is permanently lost—there is no way to recover it.
  
- **Warning**: Confluence will confirm if you're sure about deleting, and it’s advised to archive the space if you're uncertain. Archiving hides the space without permanently deleting it.

- **Recreating the Space**: After deletion, you can recreate your Personal Space by clicking *Add Personal Space*. However, all custom data (e.g., pages created) will be gone.

- **One Personal Space**: Each user can only have one Personal Space. 

### Creating and Navigating Pages in a Team Space

- **Permissions**: To create a Team Space, you need administrative permissions in Confluence, unlike a Personal Space where these permissions aren't required.

- **Creating a Team Space**: You can create a Team Space by clicking *Create a Space* on the homepage or from the *Spaces* dropdown. You can choose from pre-built templates or start with a blank space. After naming the space and setting a unique key, you can define the permissions before clicking *Create*.

- **Navigating a Team Space**: The Team Space has several sections:
  - **Overview**: The default landing page of the space.
  - **Blog**: A special page tied to the creation date.
  - **Space Settings**: For managing space-specific settings and administrative permissions.
  - **Space Shortcuts**: For quick access to commonly used URLs.
  - **Pages**: Lists all pages in the space, with archived pages hidden from the primary navigation.

- **Creating Pages**: The process is similar to Personal Spaces. You can create new pages using the *Create* button. Templates are available to streamline page creation, like the *Weekly Meeting Notes*. You can also disable unused templates via the *Space Settings*.

- **Customization**: You can organize your Team Space with templates, shortcuts, and page drafts. The tools for managing pages in Team Spaces are similar to those in Personal Spaces, including the handling of drafts and unpublished versions.

####  Page Drafts and Unpublished Versions

- **Page Drafts**: When creating a new page, it is initially saved as a draft. Confluence automatically saves drafts in the background, so there's no need for a manual save button. To access a draft, go to the *Recent* section or the *Home* page, then navigate to *Drafts*. You can continue editing a draft later before publishing it.

- **Publishing a Page**: Once a draft is published, it becomes a live page. However, if you make further edits without publishing them, those changes are considered unpublished versions. The published version of the page remains unchanged until you publish the edits.

- **Viewing Unpublished Changes**: To see unpublished changes, click the three dots on the page and select *View Changes*, which will show a preview of the edits. This preview only includes changes to the body, not the title. You can also use the *Preview* button to see how the page will look after publishing.

- **Reverting Changes**: If you decide you don't like the unpublished changes, you can revert to the last published version by using the *Revert* option. This will discard the unpublished edits and return the page to its published state.

#### Editing an Existing Page

- **Accessing the Page Editor**: To edit an existing page, click the pencil icon in the top-right corner or use the keyboard shortcut *E*.

- **Page Layout**: You can adjust the page's width to full or fixed width. Additionally, you can modify the layout by adding columns (e.g., two, three, or with sidebars) to organize content.

- **Drag and Drop Content**: Confluence allows dragging and dropping content within the page. For example, entire panels (like meeting information) can be moved together, while text and images must be moved individually.

- **Editing Tables**: You can resize tables and adjust their layout. Tables can be toggled to a wider width, even if the overall page remains fixed.

- **Text Editing**: Use standard text formatting options like bold, italics, and heading styles. You can also insert macros to pull external content, such as from JIRA, by using the JIRA macro to display issues directly within your Confluence page.

- **Publishing**: Once edits are complete, you can publish the page to see the changes, including updated tables, layout adjustments, and JIRA issue displays.

#### Setting a New Home page

 By default, each space has a Home page, which is listed as the Overview in the left menu. 
 <br>
 To change it, go to Space Settings, edit the Space Details, and select the new page as the Home page. Once saved, this page becomes the default landing page. 

####  Overview of Space Settings

- **Space Details**: Manage the space’s logo, name, key, and homepage.
- **Sidebar Customization**: Adjust visible sections such as Overview or Blog.
- **Manage Pages**: Reorder or hide pages, including managing "Hidden" and "Undefined" pages (those linked but not created yet).
- **Permissions & Attachments**: Manage space permissions and view attachments.
- **Look and Feel**: Customize themes, templates, and add headers or footers for announcements.
- **Export & Integrations**: Integrate with other tools like JIRA, use RSS feeds, or set up Slack notifications for updates.

####  Getting to Pages Quickly with Stars

- **Starring Pages**: You can star a page by hovering over it and clicking the star icon in the top-right corner. Once starred, pages can be quickly accessed by filtering the space to show only starred pages.
- **Accessing Starred Pages**: To view all starred pages across different spaces, go to the "Recent" menu and select "Starred". You can also find starred pages on your Home page.
- **Starring Spaces**: Instead of starring individual pages, you can star an entire space. This helps quickly access important spaces, which will then appear in your space drop-down menu.
- **Keyboard Shortcut**: You can use the "f" key as a shortcut to star a page.
- **Next Video**: The next video will cover "Watching" pages, a feature similar to starring but with different functionality.

####  Using the Watch Page Feature

- **Starring**: Allows you to bookmark pages for quick access, similar to favorites or bookmarks in a browser.
- **Watching**: Sends notifications about updates to a page, such as edits, deletions, comments, and attachments. Watching a page or space keeps you informed of changes, even if you’re not logged into Confluence, through email and in-app notifications.
  
Key Points:
- **Watching Pages**: To watch a page, click the eye icon (or use the "w" keyboard shortcut). You can choose to watch just the page or the entire space.
- **Default Behavior**: When you create or edit a page, Confluence automatically adds you as a watcher, though you can unwatch it later.
- **Managing Watchers**: Space administrators can manage watchers, including adding or removing them, if a user isn't receiving updates.

#### Task Management in Confluence

1. **Creating Tasks**: Confluence allows you to add tasks to pages, either using a pre-built **To-do list template** or manually creating tasks with checkboxes. Tasks are treated as simple checkboxes—checked means completed, unchecked means incomplete.
   
2. **Assigning Tasks**: You can assign tasks to team members by mentioning them in the task (using `@` to tag someone). Once a task is assigned, the person will receive an **email notification** and the task will appear in their **task list** within Confluence.

3. **Viewing Tasks**: Assigned tasks can be viewed in a **Task list** accessible from the user profile. From here, tasks can be marked as complete, and users can easily navigate to the page where the task was created.

4. **Task Completion**: Tasks are completed by checking the checkbox. When checked, they show up as completed in the user's task list and on the page itself.

5. **Context for Tasks**: It's important to provide context within the task description, as tasks may lack full context if users are working from their task list without viewing the entire page.

####  How Blogs Work

1. **Blog Overview**: A Blog in Confluence is a special type of page that's organized by date and displayed separately from other pages in a space. To access it, the space administrator must enable the Blog in the sidebar.

2. **Creating Blog Posts**: Blog posts are created in the same way as pages. You can either click the plus next to "Blog" in the sidebar or use the "Create" button to start a new post. Blog posts are organized by date in the sidebar, and you can add content, images, macros, tasks, and action items just like you would on a regular page.

3. **Limitations**: Each space in Confluence can only have one Blog, but you can create as many posts as you need.

4. **Editing**: Editing a Blog post is the same as editing a page—just click "Edit" to modify the content.

5. **RSS Feed**: Confluence allows you to set up an RSS feed for the Blog, which can be accessed from the Space Settings under Integrations. You can subscribe to the Blog using an RSS client or a browser extension. However, permissions may restrict access to the RSS feed if the space is not public.

####  Importing Word documents

1. **Importing Process**:
   - Navigate to the page where you want to import the document.
   - Click the three dots, select "Advanced Details," and choose "Import Word document."
   - You can browse to your Word document and select it for import. The title of the Word document will become the page title in Confluence.
   - You have options to either create a new page or replace the current page with the Word document. The location of the page will impact these choices.

2. **Handling Title Conflicts**:
   - If a page with the same title already exists, Confluence will prompt you to either rename the imported page or replace the existing page.

3. **Splitting Pages by Heading**:
   - When importing, you can choose to split the document into multiple pages based on headings (e.g., Heading 1). This helps organize long documents into a hierarchy of pages and child pages.
   - Confluence automatically renames pages sequentially to avoid title conflicts when multiple pages are created.

4. **Embedding Word Documents**:
   - You can also embed a Word document directly into a Confluence page by attaching it to the page. Once attached, you can preview and publish the document within the page.

#### Exporting Pages out of Confluence

1. **Exporting Single Pages**:
   - Navigate to the page you want to export, click the three dots at the top, and choose "Export."
   - You can export the page as either a **Word document** or a **PDF**.
   - The export format choice may depend on the page's layout or macros. For example, embedded Word documents may export better as PDFs, while other content may export better as Word documents.

2. **Exporting Multiple Pages or Entire Space**:
   - **Administrative Permissions** are required to export multiple pages or entire spaces.
   - In the **Space Settings**, you can choose to export the space as **HTML**, **XML**, or **PDF**.
   - When exporting as PDF, you can choose a **normal export** (all pages) or a **custom export** (select specific pages). You can also choose to include page numbers and a table of contents.

3. **Exported PDF Features**:
   - The exported PDF includes a **linked table of contents** for easy navigation between pages.
   - The export captures only the pages, not blogs, comments, or attachments.

4. **Considerations**:
   - Exporting is useful for sharing content with people who don’t have Confluence access, but keep in mind that the PDF will not automatically update if the content is changed in Confluence. You will need to re-export it for the latest version.

#### Using the Confluence Mobile app

1. **Getting Started**:
   - The app is available for both **iOS** and **Android**, with similar functionality on both platforms.
   - After downloading the app from the App Store, log in and customize your **notification preferences** to receive alerts, similar to the desktop version.

2. **Interface and Features**:
   - The mobile app layout mirrors the **Desktop Home Page** with recent pages, starred pages, and spaces you have access to.
   - You can **create new spaces** (if you have the right permissions) and view recent activity across all spaces.
   - The **Profile** section offers settings for mobile-specific features like push notifications.
   - **Search functionality** lets you find content easily, and changes (like un-starring a page) sync across both mobile and desktop versions.

3. **Editing and Collaboration**:
   - The app allows for **editing pages** on the go, where changes are reflected in real-time across devices. For example, adding content in the mobile app will update the same page when viewed on the desktop.

4. **Limitations**:
   - While the mobile app offers many features, it's not a full replacement for the desktop version. Some advanced functionalities may be unavailable on mobile.

## Managing Team Spaces

### Collaborative Editing

- **Collaborative Editing in Confluence**  
   - Demonstrated with two users: Dan and Brad  
   - Both users can edit the same page simultaneously  
   - Real-time visibility of each users cursor and changes  
   
- **Notifications & Invitations**  
   - Users can invite others to edit  
   - Notifications alert users to collaboration opportunities  

- **Real-Time Updates**  
   - Changes appear instantly on each users screen  
   - Each user can see cursor position and text changes of others  

- **Unpublished Changes**  
   - Changes are visible to collaborators before publishing  
   - Only published changes are saved to the page  
   - Example: Remote teams use this feature for live meeting notes

### Sharing Pages with our Team

- **Sharing Pages in Confluence**  
   - **Steps to Share**:  
     1. Click the "Share" button on the page.  
     2. Enter the name of the person, group, or team to share with.  
     3. Optionally, add a message.  
     4. Send the share request.  
   
   - **Notifications**:  
     - Recipient gets a notification in Confluence.  
     - An email notification is also sent.  
     - Notifications appear in the Confluence app (if installed and enabled).  

- **Recipient Interaction**:  
   - Receives the message and can access the shared page directly.  

- **Use Cases**:  
   - Simplifies sharing pages with individuals or groups within the organization.  

###  Working with Teams in Confluence 

**Overview**  
- **Teams Feature**: Dedicated Confluence feature for organizing groups of collaborators within an organization.  
- **Purpose**: Facilitates collaboration, activity tracking, and resource sharing, independent of Spaces.  

**Creating and Managing Teams**  
1. **Create a Team**:  
   - Go to **People > Teams** and create a new team (e.g., "Web Team").  
   - Add members by inviting users (e.g., Brad).  
2. **Joining a Team**:  
   - Invited users must accept the invitation to become full members.  

**Key Features of Teams**  
- **Activity Tracking**:  
  - Displays activity feed (e.g., edits, comments, page creations) for team members.  
- **Resource Sharing**:  
  - Add links and resources for quick access.  
- **Customizable Graphics**:  
  - Upload a banner image (though the feature may have bugs).  
- **Independent of Spaces**:  
  - Teams can include members from different Spaces or subsets of a Space's users.  

**Use Cases**  
- **Collaboration for Subgroups**:  
  - Ideal for smaller teams within larger Spaces (e.g., Web Team vs. App Team).  
- **Project-Based Organization**:  
  - Teams can act as project-specific "homepages," centralizing resources and activity.  

**Deleting Teams**  
- Deleting a Team:  
  - Permanently deletes the team and its links but preserves pages and comments in Spaces.  

### Managing Files in our Space

**Adding Attachments**  
1. **Drag-and-Drop**:  
   - Easily add files (e.g., images, Word documents, MP3s) by dragging them onto a page.  
   - Confluence recognizes certain file types, creating previews (e.g., audio player for MP3s).  
   - Unsupported file types (e.g., ZIP files) can still be downloaded but lack previews.  

2. **File Interaction**:  
   - Files can be resized, captioned, or previewed on the page.  
   - All files can be downloaded, regardless of preview availability.  

**Managing File Versions**  
- Attachments support versioning, similar to pages:  
  - New uploads of the same file name create a new version.  
  - Users can access and download older file versions.  
  - The latest version is always displayed on the page.  

**Finding Attachments Across a Space**  
1. **Space Settings**:  
   - Go to **Space Settings > Manage Pages > Attachments** to view all attachments in a space.  
2. **Filtering**:  
   - Filter by file type (e.g., Word documents) to locate specific attachments.  

**Best Practices**  
- Use file versioning to maintain updates while preserving previous versions.  
- Use space-level attachment management to handle large-scale file organization efficiently.  

### Page Restrictions
  
**Key Concepts**  
1. **Permissions vs. Restrictions**:  
   - **Permissions**: Apply to all pages across a space.  
   - **Restrictions**: Apply to individual pages and control access at the page level.  

**Applying Page Restrictions**  
1. **Restricting Access**:  
   - You can specify who can **view** or **edit** a page.  
   - Once restricted, only authorized users can access the page.  
   - Restricted pages do not appear in the sidebar or search results for unauthorized users.  

2. **Requesting Access**:  
   - Unauthorized users can request access, which sends a notification to the page owner.  

3. **Hierarchy Impact**:  
   - Restrictions on a parent page automatically extend to its child pages, making them inaccessible to unauthorized users.  
   - Adjusting restrictions on the parent page also affects its child pages.  

**Removing or Modifying Restrictions**  
- Restrictions can be updated or removed anytime, allowing broader access as needed.  

## Administrating Confluence

### User Management

1. **Users and Licensing**:
   - Confluence supports unlimited Users, but licensing costs are based on **Product Access** (e.g., Confluence, JIRA).  
   - Users without product access do not affect licensing costs and can be retained for reference without full deletion.

2. **User Roles**:
   - **Basic User**: Access to specific products (e.g., Confluence only).  
   - **Trusted User**: Can invite Basic Users. Useful for team leaders or managers.  
   - **Site Administrator**: Has full control, including billing management.  

3. **Adding and Managing Users**:
   - New Users are invited via email and guided to set up their profiles.  
   - Administrators can track if a User has accessed the site and manage access to optimize billing.  

4. **Login as User Feature**:
   - Allows Administrators to troubleshoot User issues by logging in as them (with email notifications sent to the User).  
   - Useful for resolving problems when Users cannot clearly describe issues.  

5. **User Deletion vs. Disabling Access**:
   - Deleting a User removes them completely but retains their contributions.  
   - Disabling access is a less disruptive option, allowing reactivation if needed.  

6. **Billing Considerations**:
   - Product-specific licenses mean separate charges for access to Confluence and JIRA.  
   - Invited Users count toward billing even if they haven’t logged in.

### User Management Overview

1. **Unlimited Users**:
   - Confluence allows unlimited Users, but costs depend on **Product Access** (e.g., Confluence or JIRA licenses).

2. **Managing User Accounts**:
   - **Active vs. Disabled Users**: When someone leaves, their account can be disabled rather than deleted, retaining their contributions without incurring licensing costs.  
   - Deleted accounts require re-invitation and profile setup if reinstated.

3. **User Roles**:
   - **Basic Users**: Limited to specified products (e.g., Confluence only).  
   - **Trusted Users**: Can invite Basic Users, useful for managers.  
   - **Site Administrators**: Full control, including billing and system management.

4. **Adding Users**:
   - Administrators can invite Users via email and specify their product access.  
   - Unused invitations still count toward billing until rescinded or the account is set up.

5. **Troubleshooting with "Login as User"**:
   - Administrators can log in as a User to troubleshoot issues, with email notifications sent to the User for transparency.  
   - Useful for diagnosing problems that Users struggle to describe.

6. **Billing**:
   - Charges are specific to each product. For example, adding a User to both Confluence and JIRA incurs separate costs.

7. **Removing Users**:
   - Removing a User prevents future access while preserving their contributions.  

### Working with Groups

1. **Purpose of Groups**:  
   - Groups enable **bulk management of Users** by assigning permissions and product access to multiple Users simultaneously.

2. **Creating and Managing Groups**:  
   - Groups can be created in the **User Management Area**, with some default groups auto-generated for Confluence or JIRA.  
   - Administrators can add or remove members from groups at any time.

3. **Group Product Access**:  
   - Assigning product access (e.g., Confluence or JIRA) to a group applies permissions to all members.  
   - **Additive Permissions**: If a User has individual access to one product and group access to another, they gain permissions for both.  

4. **Group Usage Examples**:  
   - **Page Sharing**: Pages can be shared with groups instead of individual Users for convenience.  
   - **Default Access Groups**: New Users are automatically added to the default group for a product unless this feature is disabled.

5. **Billing Considerations**:  
   - Monitor product access carefully to avoid unexpected billing increases, as more Users or groups with product access will raise costs.  
   - Default group access can be turned off to control costs and ensure only necessary Users gain access.

6. **Modifying Group Access**:  
   - Groups can be added, removed, or set as the default for product access at any time.  
   - Changes cascade automatically to all members of the group.


### Controlling User Permissions in Confluence

1. **Administrative Permissions for Team Spaces**:  
   - By default, only users with **administrative permissions** can create new Team Spaces.  
   - This restriction can be customized to allow more users, such as those in specific groups, to create spaces.

2. **Global Permissions**:  
   - Global Permissions define what users or groups can do across the entire Confluence site.  
   - Example: Allowing the "Managers" group to create spaces.  
   - Changes require adding the group via the **Atlassian Administration area**, after which permissions can be modified within Confluence.

3. **Space Permissions**:  
   - **Space-specific settings** control access and actions for individual spaces.  
   - Permissions can be granted to groups or individual users, allowing them to view, add, delete, or archive content.  
   - Fine-grained controls are available to tailor permissions for each space.

4. **Anonymous Access**:  
   - Can be enabled globally or for specific spaces to allow non-licensed users access.  
   - Best practice: Limit to viewing and commenting to avoid misuse.

5. **Default Space Permissions**:  
   - Default permissions for new spaces can be pre-configured (e.g., granting the "Managers" group administrative rights).  
   - Saves time by avoiding manual adjustments for every new space.

6. **Best Practices**:  
   - Regularly review and adjust both **Global** and **Space Permissions** to ensure appropriate access levels.  
   - Limit unnecessary permissions to reduce security risks and prevent unauthorized access.

### Creating New Templates

1. **Templates vs. Blueprints**:  
   - **Templates** and **Blueprints** are similar but differ in purpose.  
   - **Blueprints** are pre-built templates provided by Confluence, while **Templates** are custom page layouts created by users or administrators.

2. **Creating and Customizing Templates**:  
   - You can create custom **global templates** by navigating to **Settings** > **Global Templates and Blueprints**.  
   - Templates can include layouts, columns, and formatting to standardize page creation, such as adding headings or specific sections.

3. **Using Custom Templates**:  
   - Once a template is created, users (like Brad) can select it when creating a new page. This will auto-populate the page layout, streamlining the documentation process.

4. **Managing Blueprints and Templates**:  
   - **Blueprints** (default templates) can be **disabled** or **customized** but not deleted.  
   - **Custom templates** created by users can be edited or deleted, giving more flexibility.

5. **Deleting Templates**:  
   - Deleting a template removes it from the available options for new pages, but it may take time for the changes to propagate across all users.

6. **Use Case**:  
   - Templates ensure consistency across pages, ensuring users follow a standardized layout when adding content.

### Using JIRA and Confluence

1. **Linking JIRA and Confluence**:  
   - For integration to work, both JIRA and Confluence need to be linked.  
   - If not already linked, you can configure it via **Settings** > **Application Links**.  
   - Custom URLs are used, so for issues, Atlassian Support may be needed.

2. **Using JIRA with Confluence**:  
   - You can **embed JIRA issues** in Confluence using macros.  
   - Create a **JIRA query** (e.g., for "bugs") to display related issues, adjusting display options (e.g., hide assignee, reporter).  
   - Updates in JIRA are reflected in Confluence with slight delays.

3. **Creating JIRA Issues from Confluence**:  
   - Issues can be created directly from Confluence and linked to the relevant JIRA project.

4. **JIRA Retrospectives**:  
   - After a Sprint, you can use **Confluence templates** to create **retrospectives** based on JIRA data.  
   - Templates ensure a consistent layout for each retrospective.

5. **Customization**:  
   - Custom templates in Confluence can be adjusted as needed, including for retrospectives.  


###  Archiving and Deleting Spaces and Pages

1. **Archiving Pages**:  
   - To archive a page, click the three dots at the top right and select "Archive."  
   - Archived pages disappear from the sidebar and search results but can be restored from the archive at any time.  
   - Archived content is hidden from search results by default, but can be included if desired.

2. **Deleting Pages**:  
   - Deleting a page removes it from search and the site.  
   - Deleted pages go to the Trash, and can only be restored by a **Space Administrator**.  
   - After restoration, the page reappears as it was.

3. **Archiving vs. Deleting Spaces**:  
   - **Archiving a space** hides it from listings and search results but can be restored at any time from the space settings.  
   - **Deleting a space** permanently removes it, with no recovery option (unless a backup exists).  
   - Deleting a space removes both the space and its pages entirely.

4. **Recommendation**:  
   - It is generally recommended to **archive** rather than delete, since archiving allows for easy restoration.  
   - Deleting is irreversible and should be done with caution.

### Exporting and Space Backups

1. **Backing Up a Space**:  
   - To back up a space, go to the space settings and select **Export Space**.  
   - Choose **XML** for a full export (includes pages, comments, and attachments but **not blog posts**).  
   - The export creates a zip file containing the space data, which can be stored for future restoration.

2. **Restoring a Space**:  
   - To restore a space, go to **Settings** > **Import** and upload the exported XML file.  
   - If an error occurs due to an existing space with the same key, rename the space key in the XML file before re-importing. This involves modifying both the space key and any associated references in the file.

3. **Error Handling**:  
   - A common import error occurs when the space key is already in use. This can be resolved by either deleting the existing space or renaming the space key in the XML export files.  
   - After renaming, re-zip the files and import them again, ensuring no errors occur.

4. **Final Steps**:  
   - After successful import, the space will appear with the new key and can be accessed just like the original.  
   - Reminder to backup spaces before deleting them, as recovery without a backup is not possible.