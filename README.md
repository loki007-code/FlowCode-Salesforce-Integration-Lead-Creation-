```markdown
# Flowcode + Salesforce Integration (Lead Creation)

## 1. Introduction to Flowcode

Flowcode is a next-generation QR code platform designed for businesses and creators. Unlike traditional static QR codes, Flowcode offers dynamic, trackable, and customizable QR codes that can be linked to websites, forms, CRM systems, or digital experiences.

## 2. How Flowcode Works

1. **QR Code Generation**  
   - Businesses create QR codes in Flowcode and customize them (colors, logos, branding).  
   - Each QR code links to a destination URL (e.g., form, landing page, payment gateway, CRM portal).

2. **Scanning & Redirect**  
   - Customers scan the QR code using their mobile device.  
   - Flowcode routes them to the defined destination.

3. **Data Capture & Analytics**  
   - Every scan is tracked: time, device, location, frequency.  
   - Flowcode dashboards show engagement data.

4. **CRM Integration**  
   - Flowcode can integrate directly with CRM systems like Salesforce to capture leads, customer activity, or marketing campaign data.

## 3. Advantages of Flowcode

- Dynamic Codes – destinations can be updated anytime without reprinting.  
- Custom Branding – QR codes with colors, logos, and shapes.  
- Analytics – scan tracking, location, and engagement insights.  
- CRM-Friendly – direct integrations with Salesforce, HubSpot, and others.  
- Security & Privacy – encrypted scan data, unlike most free QR tools.

## 4. Disadvantages of Flowcode

- Paid Model – advanced features (dynamic links, analytics, CRM integration) require subscription.  
- Dependency – business depends on Flowcode’s servers; if they go down, QR codes break.  
- Not Fully Native – in Salesforce use cases, Flowcode acts only as the gateway, not the CRM itself.

## 5. How Flowcode is Different from Other QR Platforms

- Static Generators (like free QR websites) embed one fixed link with no analytics.  
- Flowcode offers:  
  - Dynamic redirection  
  - Real-time analytics  
  - Custom branding  
  - Secure CRM integrations  
- Competitors like Bitly QR, Beaconstac, QR Code Monkey offer similar services, but Flowcode is more CRM-focused and brand-driven.

## 6. CRM Use Cases of QR Codes

- Lead Generation – QR links to a lead form, capturing customer details directly into Salesforce.  
- Customer Engagement – QR codes on products to drive loyalty registrations.  
- Event Management – QR codes for check-ins or RSVP that create Salesforce records.  
- Payments/Donations – QR connected to Salesforce records for transaction tracking.

## 7. Technical Documentation – QR Code Lead Capture with Salesforce Experience Site

### 7.1. Introduction

This document explains the integration of QR code technology with Salesforce Experience Cloud (Community Site) to streamline lead capture. Users scan a QR code, open a web form hosted inside the community site, submit their details, and the information is stored in Salesforce as a Lead record via Apex.

### 7.2. What is Flowcode?

Flowcode is a dynamic QR code generation platform that connects offline interactions to digital workflows.

### 7.3. How QR Code Was Embedded with Salesforce

- **Step 1: Generate QR Code**  
  A QR code was created via Flowcode.

- **Step 2: Embed URL Inside QR Code**  
  The QR code contains the public Experience Site URL of the Salesforce community page hosting the lead capture form.  
  Example:  
  `https://mycompany.force.com/leadform/s/`  
  When scanned, users are redirected to this community page.

### 7.4. Community Site Setup

- Enabled **Digital Experiences** and created a new Experience Site (community).  
- Configured **Guest User Profile** for the community to ensure public users can access:  
  - The `LeadFormController` Apex class  
  - The custom LWC component  
  - Necessary object/field permissions for Lead creation  
- Permissions were structured via a **Permission Set** assigned to the Guest User (search with site name + guest user to assign).

### 7.5. Lightning Web Component (LWC) Component Purpose

- Displays a lead capture form (First Name, Last Name, Company, Email, Phone).  
- On submit, calls an Apex method to insert a Lead record.  
- The LWC (`leadForm`) is deployed and placed in the Community Site page via Lightning App Builder.

### 7.6. Apex Controller

- An Apex class (`LeadFormController`) handles lead record creation.  
- The method is exposed with `@AuraEnabled` for communication between LWC and Apex.  
- Security is managed by granting Guest User access to the class and required Lead fields.

### 7.7. Workflow of the Project

1. User scans the QR code and opens the Experience Site public URL.  
2. LWC form loads on the community page.  
3. User enters details (name, company, email, phone).  
4. Form submission triggers Apex: LWC → Apex → Insert Lead record.  
5. Lead is saved in Salesforce CRM for sales follow-up.

### 7.8. CRM Benefits

- Eliminates manual lead entry at events, booths, or offline campaigns.  
- Seamlessly integrates offline QR interactions with Salesforce CRM.  
- Centralized lead database accessible to sales and marketing teams.

### 7.9. Advantages of This Implementation

- Scalable – QR code can be placed on flyers, events, or digital channels.  
- Future-proof – if the site URL changes, the QR code can be updated without reprinting.  
- Native Salesforce – uses LWC + Apex, no dependency on external servers.  
- Secure – guest user permissions are limited to only required objects and fields.

---

For more details and to create your dynamic QR codes, visit [Flowcode’s official website](https://flowcode.com).
```
