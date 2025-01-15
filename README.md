# Starter Email Boilerplate
### A skeleton HTML template of essential design patterns for accessible, responsive emails

A modularly designed boilerplate template that acts as a starting point for your own email templates, with focus on semantics and accessibility, and clean code that works across email clients. It includes essential email layouts and components, with minimal styling for you to build on top of.

**Optimized for accessibility**

Div's for structure, ghost tables only used when needed to support Outlook, and semantic elements like heading and paragraph tags used throughout.

**Modular design**

Stackable sections and standalone components following modular design practices.

**Responsive adjustments**

Simple CSS media query definitions to adjust layout for mobile across all modules.

**Available in modern and legacy versions**

Modern does not use tables or inline styling. Legacy includes backwards compatibility for Outlook for Windows Word rendering engine and uses ghost tables and inline styles.

## Features ##
- Support for major email clients
- Built semantically with accessibility in mind
- Mobile-responsive ready
- Dark mode compatibility
- Essential pre-built modules
- Blocks Edit ready

## Email clients tested ##
- Gmail and Android
- Apple Mail
- Microsoft Outlook versions
- Yahoo! Mail and AOL

## Modules included ##

<img src="starter-template-sections-mobile.png" />

## The frame ##

### Doctype ###

    <!DOCTYPE html>

HTML5 Doctype is enough to trigger standards mode on supported clients.

### HTML element ###

    <html lang="en" dir="ltr">

Set language for email clients, browsers, and screen readers. If you need to set language direction, add `dir="ltr"` for left-to-right, or `dir="rtl"` for right-to-left reading.

#### Legacy support images DPI ####

Add the XML namespace for Outlook image DPI setting:

    <html lang="en" dir="ltr" xmlns:v="urn:schemas-microsoft-com:vml" xmlns:o="urn:schemas-microsoft-com:office:office">

### Meta ###

    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=yes">
    <meta name="color-scheme" content="light dark">
    <title>Starter Email Boilerplate</title>

Set the character encoding standard.

`viewport` element controls the page's dimensions and scaling. This is particularly important for mobile devices, to make sure content is not zoomed in or out.

`color-scheme` tells email clients preferred dark mode settings, for the ones that follow it. `light dark` means you support both. `light only` means you only support light styling. [More on dark mode support →](https://blocksedit.com/content-code/dark-mode-decision/)

#### Legacy support Outlook DPI setting ####

    <!--[if mso]>
    <noscript>
      <xml>
        <o:OfficeDocumentSettings>
          <o:PixelsPerInch>96</o:PixelsPerInch>
        </o:OfficeDocumentSettings>
      </xml>
    </noscript>
    <![endif]-->

Helps with rendering images on higher DPI screens, specificially background images, in Outlook on Windows. [More on Outlook DPI scaling →](https://www.courtneyfantinato.com/correcting-outlook-dpi-scaling-issues/)

### Style ###

    /* Dark mode settings */
    :root {
      color-scheme: light dark;
    }

    /* Reset */
    html, body {
      margin: 0 auto !important;
      padding: 0 !important;
      height: 100% !important;
      width: 100% !important;
    }
    .main {
      box-sizing: border-box;
    }

Dark mode setting works the same as the meta definition but is currently only supported by Apple Mail.

Content styling that replaces legacy inline code:

    /* Content */
    body {
      background: #ffffff;
      font-family: Helvetica Neue, Helvetica, Arial, sans-serif;
      font-size: 18px;
      line-height: 24px;
      color: #333333;
      font-weight: 300;
    }

    img {
      display: block;
      margin: 0 auto;
    }
    img.fill {
      width: 100%;
      height: auto;
    }

    .preview {
      display: none;
    }

    .wrapper {
      background: #ffffff;
    }
    .main {
      max-width: 600px;
      margin: 0 auto;
    }
    .content {
      margin: 0;
      text-align: left;
    }

    .row {
      display: table;
      width: 100%;
    }
    .row-alt {
      background-color: #eeeeee;
    }
    .col {
      display: table-cell;
      vertical-align: top;
    }
    .row-alt .col {
      padding: 14px;
    }
    .col-3 {
      width: 25%;
    }
    .col-4 {
      width: 33.3%;
    }
    .col-6 {
      width: 50%;
    }
    .col-8 {
      width: 66.6%;
    }

    h1, h2, h3 {
      margin: 0;
      font-family: Georgia, Times New Roman, serif;
      color: #333333;
      font-weight: normal;
    }
    h1 {
      font-size: 18px;
      line-height: 24px;
    }
    h2 {
      margin-bottom: 10px;
      font-size: 28px;
      line-height: 32px;
    }
    h3 {
      margin-bottom: 10px;
      font-size: 22px;
      line-height: 28px;
    }
    p {
      margin: 0;
      margin-bottom: 10px;
    }
    p:last-child {
      margin-bottom: 0;
    }
    a {
      text-decoration: underline;
      color: #1467ac;
    }
    ul {
      margin: 0;
      padding-left: 30px;
    }

    .btn {
      margin: 0;
      display: inline-block;
      border-radius: 50px;
      padding: 12px 25px;
      background: #333333;
      color: #ffffff !important;
      font-weight: 400;
      line-height: 1;
      text-decoration: none;
      text-align: center;
    }

    .spacer-sm, .spacer-md {
      display: inline-block;
      margin: 0;
      margin-bottom: 14px;
      width: 100%;
      line-height: 0;
    }
    .spacer-md {
      margin-bottom: 28px;
    }

    .bg-image {
      background-repeat: no-repeat;
      background-size: cover;
      background-position: top center;
      width: 100%;
      min-height: 300px;
      text-align: center;
    }
    .bg-image h2 {
      padding-top: 40px;
    }

    .footer {
      margin: 30px 20px;
    }
    .footer p {
      font-size: 14px;
      line-height: 18px;
      text-align: center;
    }

### Preview text ###

    <div style="display: none;"> </div>

Text snippet shown under the subject line in the listing of emails in email clients.

### Outlook for Windows Word rendering engine note ###

For anyone that may still be on a legacy version of Outlook.

    <!--[if mso]>
      <p style="text-align: center;">Email may not look quite right in your version of Outlook. <a href="#" style="text-decoration: underline; color: #1467ac;">View it in your browser.</a></p>
    <![endif]-->

### Wrapper ###

    <div role="article" lang="en" dir="ltr" class="wrapper" style="background: #ffffff; font-size: 16px;"> </div>

`role` property for accessibility, defining the content as an article. Set `lang` property in case it gets removed by email clients along with the HTML tag. Set language direction also, if needed.

For styling, set a background color for email clients that may remove it from the body tag. And a font size to override email client default size. For readability, at least `16px` is recommended.

## Layout sections ##

### Example section ###

    <!-- Two-column section with image on the left -->
    <div style="display: table; width: 100%;">
      <div class="column" style="display: table-cell; width: 50%; padding-right: 0;">
        <img height="auto" src="https://dummyimage.com/600x400/60bcde/ffffff&text=Content+Image" width="300" alt="" class="fill" style="display: block; width: 300px; height: auto;">
      </div>
      <div class="column" style="display: table-cell; width: 50%; padding-left: 14px; vertical-align: middle;">
        <p style="margin: 0; font-family: Helvetica Neue, Helvetica, Arial, sans-serif; font-size: 18px; line-height: 24px; color: #333333; font-weight: 300;">Text next to an image, in a two-colum section, split 50/50.</p>
      </div>
    </div>

#### Legacy support example section ####

    <!-- Two-column section with image on the left -->
    <!--[if true]>
    <table border="0" cellpadding="0" cellspacing="0" role="presentation" width="100%" style="all: unset; opacity: 0;">
      <tr>
    <![endif]-->
    <div style="display: table; width: 100%;">
      <!--[if true]><td width="50%" style="padding-right: 0;"><![endif]-->
      <!--[if !true]><!-->
        <div class="column" style="display: table-cell; width: 50%; padding-right: 0;">
      <!--<![endif]-->
          <img height="auto" src="https://via.placeholder.com/600x400/60bcde/ffffff/?text=Content+Image" width="300" alt="" class="fill" style="display: block; width: 300px; height: auto;">
      <!--[if !true]><!-->
        </div>
      <!--<![endif]-->
      <!--[if true]>
        </td>
        <td width="50%" style="padding-left: 14px;">
      <![endif]-->
      <!--[if !true]><!-->
        <div class="column" style="display: table-cell; width: 50%; padding-left: 14px; vertical-align: middle;">
      <!--<![endif]-->
          <p style="margin: 0; font-family: Helvetica Neue, Helvetica, Arial, sans-serif; font-size: 18px; line-height: 24px; color: #333333; font-weight: 300;">Text next to an image, in a two-colum section, split 50/50.</p>
      <!--[if !true]><!-->
        </div>
      <!--<![endif]-->
      <!--[if true]></td><![endif]-->
    </div>
    <!--[if true]>
      </tr>
    </table>
    <![endif]-->

Uses both divs and ghost tables for columns.

### Background images ###

An example feature section with a background image:

    <div class="block-section" data-group="feature-bg-image" data-title="Featured background image">
      <div class="block-background" data-block="feature-bg-image-image" style="background-image: url(https://dummyimage.com/1200x600/60bcde/ffffff&text=Background+Image); background-repeat: no-repeat; background-size: cover; background-position: top center; width: 100%; min-height: 300px; text-align: center;">
        <p style="display: inline-block; margin: 0; margin-bottom: 40px; width: 100%; line-height: 0;">&nbsp;</p>
        <h2 class="block-edit block-remove" data-block="feature-bg-image-title" style="margin: 0; font-family: Georgia, Times New Roman, serif; font-size: 28px; line-height: 32px; color: #333333; font-weight: normal; text-align: center;">Headline/primary title text</h2>
        <p style="display: inline-block; margin: 0; margin-bottom: 40px; width: 100%; line-height: 0;">&nbsp;</p>
      </div>
    </div>

#### Legacy support background images ####

    <div style="background-image: url(https://via.placeholder.com/1200x600/60bcde/ffffff/?text=Background+Image); background-repeat: no-repeat; background-size: cover; background-position: top center; width: 100%; height: 300px;">
      <!--[if mso]> <v:rect xmlns:v="urn:schemas-microsoft-com:vml" fill="true" stroke="false" fillcolor="#333333" style="width: 450pt; height: 300px; text-align: center;"> <v:fill type="frame" size="450pt,300pt" aspect="atleast" alignshape="true" src="https://via.placeholder.com/1200x600/60bcde/ffffff/?text=Background+Image" data-block="feature-bg" color="#ffffff"> <v:textbox inset="0,0,0,0" style="mso-fit-shape-to-text: true;"><![endif]-->
      <table role="presentation" width="100%" cellspacing="0" cellpadding="0">
        <tr>
          <td style="height: 260px; padding: 14px; vertical-align: middle; text-align: center;">
            <h2 style="margin: 0; font-family: Georgia, Times New Roman, serif; font-size: 28px; line-height: 32px; color: #333333; font-weight: normal;">Headline/primary title text</h2>
          </td>
        </tr>
      </table>
      <!--[if mso]></v:textbox></v:rect><![endif]-->
    </div>

Uses VML background image for Outlook. [More on background properties in VML →](https://www.hteumeuleu.com/2021/background-properties-in-vml/)

## Standalone components ##

### Fluid images ###

    <img src="https://via.placeholder.com/1200x600/60bcde/ffffff/?text=Content+Image" width="600" height="auto" alt="" style="display: block; width: 100%; height: auto;">

Adjusts to column width.

### Spacers ###

    <div style="width: 100%; height: 14px;"> </div>
    <div style="width: 100%; height: 28px;"> </div>

Multiple standardized sizes to use throughout.

### Titles ###

    <h2 style="margin: 0; margin-bottom: 10px; font-family: Georgia, Times New Roman, serif; font-size: 28px; line-height: 32px; color: #333333; font-weight: normal;">Headline/primary title text</h2>
    <h3 style="margin: 0; margin-bottom: 10px; font-family: Georgia, Times New Roman, serif; font-size: 22px; line-height: 28px; color: #333333; font-weight: normal;">Subheadline/secondary title text</h3>

Headlines and subheadlines, using semantic title tags.

### Text ###

    <p style="margin: 0; font-family: Helvetica Neue, Helvetica, Arial, sans-serif;">More text copy goes here. It could be as long as you need it to be as there is plenty of room to let it flow!</p>
    <ul style="margin: 0; padding-left: 30px;">
      <li>List item</li>
    </ul>

Paragraph and unordered lists.

### Links ###

    <a href="https://blocksedit.com/#" style="text-decoration: underline; color: #1467ac;">link</a>

### Buttons ###

    <a href="https://blocksedit.com/#" style="margin: 0; display: inline-block; border-radius: 50px; padding: 12px 25px; background: #333333; color: #ffffff; font-family: Helvetica, Arial, sans-serif; font-size: 18px; font-weight: 400; line-height: 1; text-decoration: none; text-align: center;">link</a>

#### Legacy support buttons ####

    <table border="0" cellpadding="0" cellspacing="0" role="presentation" class="btn" style="display: inline-block; margin: 0 auto; border-collapse: separate; border-radius: 50px; line-height: 100%;">
      <tbody style="display: inline-block;">
        <tr>
          <td style="display: inline-block; border: none; border-radius: 50px; cursor: auto; mso-padding-alt: 12px 25px; background: #333333;"><a href="https://blocksedit.com/#" style="margin: 0; display: inline-block; border-radius: 50px; padding: 12px 25px; background: #333333; color: #ffffff; font-family: Helvetica, Arial, sans-serif; font-size: 18px; font-weight: 400; line-height: 1; text-decoration: none; mso-padding-alt: 0px; text-align: center;" target="_blank">Call to Action</a></td>
        </tr>
      </tbody>
    </table>

Uses table code for backwards compatibility. `border-radius` does not work in Outlook.

## Responsive adjustments ##

### Media query ###

    @media screen and (max-width: 480px) { }

`480px` breakpoint accounts for mobile devices with larger screens.

### Layout ###

`column` class is used in the HTML to adjust multiple columns for mobile:

    .column {
      display: block !important;
      width: 100% !important;
      box-sizing: border-box;
      padding: 0 14px 14px 14px !important;
    }
    .column:last-child {
      padding-bottom: 0 !important;
    }
    .column.alt {
      padding-top: 14px !important;
      padding-bottom: 0 !important;
    }
    .column.alt:last-child {
      padding-bottom: 14px !important;
    }
    .column img.fill {
      width: 100% !important;
      height: auto !important;
    }
    .icons .column {
      width: 50% !important;
      float: left;
    }
    .icons .column:nth-child(3) {
      padding-bottom: 0 !important;
    }
    .icons .column.alt:nth-child(3) {
      padding-bottom: 14px !important;
    }

Padding adjustments are made as columns are stacked on top of each other. 4-column icon sections are stacked as 2 by 2 columns. Images are scaled to fit the space.

## Dark mode adjustments ##

### Media query ###

    @media (prefers-color-scheme: dark) { }

### Layout ###

    body, .wrapper {
      background-color: #222 !important;
    }
    h1, h2, h3, p, ul li, code {
      color: #f1f1f1 !important;
    }
    .column.alt {
      background-color: #1b1b1b !important;
    }
    .btn a {
      background: #a6a6a6 !important;
      color: #404040 !important;
    }

Body changes to essentially black, but for improved accessibility it's better to go a shade lighter. The same goes for making text color off-white.

## References ##

- [Good Email Code](https://www.goodemailcode.com/) - a thorough overview of email code and why it's used
- [Email Coding Guidelines](https://github.com/hteumeuleu/email-guidelines) - also covers and explains standard email code to use
- [Cerberus](https://www.cerberusemail.com/) - additional code compatibility options for older email clients
