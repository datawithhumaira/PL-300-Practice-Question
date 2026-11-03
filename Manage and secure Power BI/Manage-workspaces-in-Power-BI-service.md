# 📝Question 1
finance manager needs to review the monthly P&L report, explore visual filters, and export summary tables to Excel, but they must not be allowed to modify the report layout or publish apps.

## Question: Which workspace role should you assign to this finance manager?

A) Admin

B) Member

C) Contributor

D) Viewer

(Answer: D) Viewer, because Viewers have read-only access to view and interact with reports and use features like Analyze in Excel without having editing or publishing privileges.)
---
# 📝Question 2
You are the Power BI administrator for a regional sales organization. You have set up a shared workspace named “Sales Analytics” backed by a Pro license mode.

You have three users with different responsibilities:

Alex (Sales Analyst): Needs to create new reports, edit existing report visuals, and delete outdated reports within the workspace, but should not be allowed to share underlying datasets or manage who has access to the workspace.

Brenda (Department Lead): Needs to update reports, package and publish the final App to the broader sales team, and manage content settings within the workspace, but should not be allowed to delete the workspace itself.

Charlie (Regional Director): Only needs to view and interact with the executive dashboard and reports, use the "Analyze in Excel" feature, and must never be able to modify content or settings.

## Question: Which exact combination of workspace roles should you assign to Alex, Brenda, and Charlie, respectively?

A) Alex: Contributor | Brenda: Member | Charlie: Viewer

B) Alex: Member | Brenda: Contributor | Charlie: Viewer

C) Alex: Contributor | Brenda: Admin | Charlie: Contributor

D) Alex: Member | Brenda: Admin | Charlie: Member

## Description

Here is where the roles line up with the scenario requirements:

Alex (Needs to create/edit/delete content, but cannot share datasets or manage workspace access):

A Contributor can create, edit, and delete content in the workspace, but lacks control over app publishing, sharing datasets, and workspace settings. This matches Alex perfectly! A Member would actually be allowed to share items and update/publish apps, which exceeds Alex's permissions.

Brenda (Needs to update reports, package/publish the App, and manage content settings, but cannot delete the workspace):

A Member can manage content, publish and update apps, share items, and modify data settings, but cannot delete the workspace or manage Admin roles. A Contributor cannot publish apps or share items, so Brenda couldn't do her job as a Contributor.

Charlie (Only needs to view/interact and use "Analyze in Excel", with no modification rights):

A Viewer has read-only access to view and interact with content without making changes.

(Answer: A) Alex: Contributor | Brenda: Member | Charlie: Viewer
---
# 📝Question 3
You have a finalized sales report .pbix file stored in your team's SharePoint document library. Instead of publishing manually from Power BI Desktop every time a change is made, you decide to add the report to a shared workspace by connecting directly to the file in SharePoint using the Get data > OneDrive / SharePoint option.

## Question: Once connected, how frequently does the Power BI service automatically check for and sync changes made to that file in SharePoint?

A) Real-time (instantly upon saving the file in SharePoint)

B) Automatically, approximately each hour

C) Once every 24 hours (at midnight UTC)

D) It never syncs automatically; you must manually click "Refresh now" every time

(Answer: B), when you connect to a .pbix file stored in SharePoint or OneDrive, the Power BI service automatically syncs and checks for updates approximately each hour.
---
# Question 3
You need to organize a large shared workspace that contains over 50 different Power BI items (reports, semantic models, and dashboards) created by multiple project teams. To keep things clean and easy to navigate for your team, you decide to use Folders inside the workspace.

## Question: According to Power BI service capabilities, what is the maximum depth allowed when creating nested subfolders inside a workspace folder?

A) 3 levels deep

B) 5 levels deep

C) 10 levels deep

D) Unlimited nesting

(Answer: C)
---
# 📝Question 4
You have created a workspace in the Power BI service for your regional sales team. You want to ensure that all workspace members and viewers have access to advanced capabilities, including larger semantic model sizes, AI-powered features, and up to 48 scheduled data refreshes per day, without purchasing full enterprise Fabric capacity. However, all users who access this workspace must be licensed accordingly.

## Question: Which workspace type should you select to achieve these advanced features?

A) My Workspace

B) Pro workspace type

C) Premium Per User (PPU) workspace type

D) Standard Free workspace type

(Answer: C) The Premium Per User (PPU) workspace type unlocks those advanced capabilities (like up to 48 refreshes per day, larger model sizes, and AI features) without needing full Fabric capacity, with the caveat that everyone accessing it must have a PPU license.
---
# 📝Question 5
You are managing a shared workspace assigned to the Pro workspace type. A new data analyst joins your team, and you assign them the Contributor role in the workspace. The analyst creates a fantastic new report and wants to distribute it as an App to the broader department so that end-users can consume it.

## Question: What happens when the analyst attempts to create and publish the App from the workspace?

A) The app is successfully published, and all department users immediately gain access.

B) The action fails because Contributors do not have permission to publish or update apps.

C) The action fails unless the analyst is simultaneously upgraded to the Admin role.

D) The app is published, but only other workspace Contributors can view it.

(Answer: B) A workspace Contributor can create, edit, and delete content inside the workspace, but they cannot publish or update apps or manage workspace access. Publishing apps is reserved for Members and Admins.
---
# 📝Question 6
Your organization uses Power BI Pro licenses for all users. You create a new shared workspace and select the Premium Per User (PPU) workspace type because you want to take advantage of advanced AI capabilities and higher refresh rates (up to 48 refreshes per day). A colleague who has a standard Power BI Pro license needs to view and interact with the reports in this workspace.

## Question: Can this colleague access and view the content inside this PPU workspace?

A) Yes, because Power BI Pro licenses inherit access to all workspace types.

B) Yes, but only if they are assigned the Viewer role.

C) No, because PPU workspaces can only be accessed by users who also have a PPU license.

D) No, unless you upgrade their workspace type to a Fabric Capacity workspace.
## Description 
Premium Per User (PPU) workspaces have a strict licensing rule: every single user who accesses the workspace—regardless of whether they are an Admin, Member, Contributor, or even a read-only Viewer—must have a PPU license.

A standard Power BI Pro license is not enough to access a PPU workspace. If a user only has a Pro license, they will be blocked from opening or viewing anything inside that workspace unless they are upgraded to PPU (or the workspace is changed to a standard Pro or Fabric Capacity workspace).

(Answer: C)
---
# 📝 Question 7
You have published a report from Power BI Desktop to a shared workspace. A stakeholder who has been assigned the Viewer role needs to analyze the data further. They click around the report visuals and notice an option to look at the underlying data in a familiar spreadsheet interface.

## Question: Can a user with the Viewer role use the "Analyze in Excel" feature to connect to the semantic model and build pivot tables in Excel?

A) Yes, Viewers are allowed to use features like "Analyze in Excel" to explore semantic models.

B) No, the "Analyze in Excel" feature is restricted exclusively to Admins and Members.

C) No, Viewers have completely read-only web browser access and cannot export or connect to data outside the web interface.

D) Yes, but only if they upgrade their workspace role to Contributor first.

## Description: 
- The Viewer Role & Analyze in Excel: By default, the Viewer role has read-only access. However, a Viewer can use features like "Analyze in Excel" or export underlying data if they are explicitly granted Build permission on the semantic model.
- They do not need to be upgraded to a Contributor or Member just to use Excel integration; a workspace Admin can simply assign them Build permission on that specific dataset while keeping them as a Viewer in the workspace.
- Therefore, saying they are completely restricted to read-only web access with zero external connection capability (Option C) is false because Build permission enables external connection tools like Excel.
(Answer: A)
---
# 📝 Question 8
Your company has purchased Power BI Pro licenses for all employees. You create a new workspace backed by Fabric Capacity. You want to share the finalized executive dashboard with 50 external stakeholders across the organization who only have Free licenses, without buying them Pro licenses.

## Question: How should you share the reports with these Free-licensed stakeholders so they can view them successfully?

A) Add them directly to the Fabric Capacity workspace as Viewers.

B) Upgrade their workspace role to Contributors so they can access the capacity.

C) Package the reports into a Power BI App and publish the App to those users.

D) It is impossible; Free users can never view content on a Fabric Capacity workspace under any circumstance.

##Description:

- The Fabric Capacity Free User Loophole: If a workspace is backed by Fabric Capacity (or Premium Capacity), users with Free licenses are allowed to view content—but only if that content is delivered to them via an App!
- If you tried to add those Free-licensed users directly to the workspace as Viewers (Option A), Power BI would block them because direct workspace access generally requires a Pro (or PPU) license.
- By packaging the content into an App (Option C) and publishing it from a Fabric-backed workspace, Free users can safely consume it without needing a Pro license. This is one of the biggest cost-saving reasons organizations buy Fabric capacity!
(Answer: C)
---
# 📝 Question 9
You have set up a workspace using the Premium Per User (PPU) license mode to take advantage of advanced AI features and higher refresh rates. A senior business analyst in your department holds a standard Power BI Pro license and needs to collaborate with you inside this workspace by editing reports and semantic models.

## Question: Can this analyst access and edit content inside your PPU workspace using their current Power BI Pro license?

A) Yes, because Power BI Pro licenses automatically include PPU workspace access.

B) Yes, provided you assign them the Contributor or Member role.

C) No, because every user accessing a PPU workspace must also have a PPU license.

D) No, unless you downgrade the workspace type to a standard Pro workspace first.
(Answer: C)
---
# 📝 Question 10
You have built a core sales report in Power BI Desktop and want to share it safely with 40 general employees across your company who only have standard Free licenses. Your workspace is backed by a dedicated Fabric Capacity.

To ensure these Free-licensed employees can view the report without you having to buy them Pro licenses, how should you distribute the report to them?

A) Add all 40 employees directly to the workspace as Viewers.

B) Package the report into a Power BI App and publish the App to those employees.

C) Email them a direct link to the .pbix file stored in the workspace.

D) It is impossible; Free users cannot view reports on Fabric Capacity workspaces under any circumstances.

## Description: 
Remember our Kitchen vs. Restaurant Analogy: The workspace is the kitchen where you build, but the App is the menu/dining room you hand to the regular consumers (Free users) so they can view the data safely without needing a Pro license.
(Answer: B)
---
# 📝 Question 11
Scenario:
A team member in your shared workspace has been assigned the Contributor role. They have spent the afternoon updating a report and now want to publish these changes as an updated App so the rest of the company can consume the latest version. However, when they look at the workspace menu, they notice they cannot publish or update the App.

## Question: Why is the Contributor unable to publish or update the App?

A) Contributors can only publish apps if they upgrade their workspace role to Member or Admin.

B) Contributors are only allowed to view reports; they cannot edit workspace contents.

C) Contributors can publish apps, but only if the workspace is backed by Fabric Capacity.

D) Contributors must first export the .pbix file to SharePoint before an app can be updated.

## Description:
Remember our Permission Staircase: A Contributor is a builder (line cook), but they are not allowed to publish or update Apps. To do that, they need to be stepped up to a Member or an Admin (the head chefs/managers).
(Answer: A)
---
# 📝 Question 12
Scenario:
You are organizing a large shared workspace that contains over 60 different items (reports, semantic models, and dashboards) created by various teams. To make it easier for users to navigate the workspace, you decide to organize items into Folders.

According to Power BI workspace capabilities, what is the maximum nesting depth allowed when creating subfolders inside a workspace folder?

A) 3 levels deep

B) 5 levels deep

C) 10 levels deep

D) Unlimited nesting

(Answer: C)
---
# 🔑 The 3 Golden Rules of Power BI Workspaces
### Rule 1: The Workspace License Dictates Everyone's Entry Fee
Pro Workspace: Every single person entering needs a Pro license.

PPU (Premium Per User) Workspace: 100% strict. Every single person entering must have a PPU license. If someone only has a Pro license, the door is slammed in their face. No exceptions!

Fabric Capacity Workspace: Enterprise-grade. People with standard Free licenses can look at reports here, but only if you give them an App (never by putting them directly in the workspace).

### Rule 2: Workspaces vs. Apps (The "Kitchen vs. Restaurant" Analogy)
The Workspace is the Kitchen: This is where the chefs (creators, contributors, members) cook, chop, edit, and mess things up. You don't let random customers into the kitchen.

The App is the Dining Room / Menu: This is what you hand to the regular customers (consumers). They can look and enjoy, but they can't change the recipe or go into the kitchen.

### Rule 3: The 4 Workspace Roles (Ranked from Lowest to Highest Power)
Viewer: The Customer. Can look and click around, but can't change anything. Can use "Analyze in Excel" if given permission.

Contributor: The Line Cook. Can build, edit, and delete reports inside the workspace. Cannot publish apps or share data outside.

Head Chef (Member): Can do everything a Contributor does, plus they can publish Apps and share items with others. Still can't delete the workspace.

Admin: The Owner. Absolute control. Can delete the workspace and hire/fire people (add/remove users).
