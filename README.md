# Print Stylesheet Documentation

This is a comprehensive print stylesheet that transforms how your web pages appear when printed. It provides refined typography, elegant layouts, and numerous utility classes for complete control over printed output.

## Table of Contents

- [Basic Setup](#basic-setup)
- [Page Configuration](#page-configuration)
- [Document Structure](#document-structure)
- [Typography](#typography)
- [Media Elements](#media-elements)
- [Tables](#tables)
- [Special Elements](#special-elements)
- [Layout Control](#layout-control)
- [Utility Classes](#utility-classes)

## Basic Setup

Include this CSS in your project either by linking to it or by embedding it within a media query:

```html
<link rel="stylesheet" href="print.css" media="print">
```

Or embed directly in your HTML:

```html
<style media="print">
  /* Your print CSS here */
</style>
```

## Page Configuration

### Page Size and Margins

The stylesheet sets up A4 paper size with appropriate margins and page numbering:

```html
<body data-document-title="Quarterly Financial Report">
  <h1>Quarterly Financial Report</h1>
  <p>This document will have the title "Quarterly Financial Report" 
     appear in a header on each printed page.</p>
</body>
```

### Page Breaks

Control where page breaks occur:

```html
<section>
  <h2>First Section</h2>
  <p>Content of first section...</p>
</section>

<div class="page-break"></div><!-- Forces a page break -->

<section>
  <h2>Second Section</h2>
  <p>This section starts on a new page...</p>
</section>

<div class="avoid-break">
  <h3>Important Content</h3>
  <p>This content will not be split across pages.</p>
</div>
```

### Watermark

Add a watermark to printed pages:

```html
<div class="watermark">DRAFT</div>
<h1>Project Proposal</h1>
<p>This document will print with "DRAFT" as a diagonal watermark.</p>
```

## Document Structure

### Headings

Headings are styled with appropriate sizing and spacing:

```html
<h1>Main Document Title</h1>
<h2>Section Heading</h2>
<h3>Sub-section Heading</h3>
<h4>Minor Heading</h4>
```

### Lists

```html
<h3>Project Requirements</h3>
<ul>
  <li>Responsive design for all devices</li>
  <li>Accessible according to WCAG 2.1 AA</li>
  <li>Cross-browser compatibility</li>
</ul>

<h3>Implementation Timeline</h3>
<ol>
  <li>Planning phase: 2 weeks</li>
  <li>Development: 8 weeks</li>
  <li>Testing: 3 weeks</li>
  <li>Deployment: 1 week</li>
</ol>

<h3>Technical Terminology</h3>
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language, the standard markup language for documents designed to be displayed in a web browser.</dd>
  
  <dt>CSS</dt>
  <dd>Cascading Style Sheets, a style sheet language used for describing the presentation of a document written in HTML.</dd>
</dl>
```

## Typography

### Text Styling

```html
<p>This is a standard paragraph with <strong>bold text</strong> and <em>italic text</em>.</p>

<blockquote>
  This is a blockquote containing an important statement or quotation.
  <cite>— Author Name</cite>
</blockquote>

<p class="print-text-center">This text will be centered when printed.</p>
<p class="print-text-right">This text will be right-aligned when printed.</p>
<p class="print-text-justify">This longer paragraph demonstrates justified text, which aligns the text to both the left and right margins, creating a clean edge on both sides.</p>
```

### Code and Pre-formatted Text

```html
<p>The <code>print-color-adjust: exact</code> property ensures backgrounds print correctly.</p>

<pre>
function printDocument() {
  window.print();
}
</pre>
```

## Media Elements

### Images

```html
<img src="chart.png" alt="Sales chart">

<figure>
  <img src="diagram.png" alt="System architecture diagram">
  <figcaption>Fig 1: High-level system architecture showing key components and data flow.</figcaption>
</figure>

<!-- Control image size -->
<img src="logo.png" alt="Company logo" class="print-img-small">
```

## Tables

### Basic Table

```html
<table>
  <thead>
    <tr>
      <th>Product</th>
      <th>Q1 Sales</th>
      <th>Q2 Sales</th>
      <th>Q3 Sales</th>
      <th>Q4 Sales</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Widget A</td>
      <td>256</td>
      <td>312</td>
      <td>408</td>
      <td>512</td>
    </tr>
    <tr>
      <td>Widget B</td>
      <td>128</td>
      <td>125</td>
      <td>176</td>
      <td>229</td>
    </tr>
  </tbody>
</table>
```

### Advanced Table Styling

```html
<table class="print-table-compact">
  <caption>Compact Table Example</caption>
  <thead>
    <tr>
      <th>Date</th>
      <th>Transaction</th>
      <th>Amount</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="print-cell-nowrap">2024-01-15</td>
      <td>Office Supplies</td>
      <td>$245.99</td>
    </tr>
    <tr>
      <td class="print-cell-nowrap">2024-01-22</td>
      <td>Software License</td>
      <td>$1,200.00</td>
    </tr>
  </tbody>
</table>
```

## Special Elements

### Boxes and Callouts

```html
<div class="print-box">
  <h3>Important Notice</h3>
  <p>This content appears in a boxed container when printed.</p>
</div>

<div class="print-box-dashed">
  <h3>Action Required</h3>
  <p>Please review and sign this document by March 1st.</p>
</div>

<div class="print-callout">
  <p>This is a callout box that draws attention to important information.</p>
</div>
```

### Link Handling

```html
<p>
  Visit our website at <a href="https://example.com">Example Company</a> for more information.
  When printed, this will automatically show the URL in parentheses.
</p>

<p>
  For more details, see <a href="#section3" class="no-print-url">Section 3</a>. 
  Internal links like this won't show the URL.
</p>
```

## Layout Control

### Multi-column Layout

```html
<div class="two-columns">
  <p>This content will flow into two columns when printed. This is useful for presenting information in a more compact format, similar to newspapers or magazines. The columns are balanced and separated with a subtle rule.</p>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris.</p>
</div>

<!-- Custom column control -->
<div class="print-columns-3 print-column-gap-md print-column-rule">
  <p>This will create three columns with medium gap and a separator rule.</p>
  <p>Each column will contain approximately the same amount of text.</p>
  <p>The columns will be balanced automatically.</p>
  <h3 class="print-column-span-all">This heading spans across all columns</h3>
  <p>Content continues in the three-column layout after the spanning heading.</p>
</div>
```

### Landscape Page

```html
<div class="print-landscape-page">
  <h2>Yearly Revenue Comparison</h2>
  <img src="wide-chart.png" alt="Yearly revenue chart">
  <p>This entire section will print in landscape orientation.</p>
</div>
```

## Utility Classes

### Visibility Controls

```html
<!-- Only visible when printed -->
<div class="print-only">
  <p>This content only appears in print.</p>
</div>

<!-- Hidden when printed -->
<div class="print-hide">
  <p>This content will not appear in print.</p>
</div>
```

### Text Size Controls

```html
<p class="print-text-xs">Extra small text (7pt)</p>
<p class="print-text-sm">Small text (8pt)</p>
<p class="print-text-md">Medium text (10pt)</p>
<p class="print-text-lg">Large text (12pt)</p>
<p class="print-text-xl">Extra large text (16pt)</p>
```

### Spacing Controls

```html
<div class="print-m-2">
  <p>This div has 8pt margin all around when printed.</p>
</div>

<div class="print-p-1">
  <p>This div has 4pt padding all around when printed.</p>
</div>

<h3 class="print-mb-2">Heading with margin bottom</h3>
<p class="print-mt-0">This paragraph has no top margin.</p>
```

### Border Controls

```html
<div class="print-border">
  <p>This div has a solid border on all sides.</p>
</div>

<div class="print-border-top print-border-bottom">
  <p>This div has borders only on top and bottom.</p>
</div>

<div class="print-border-dashed">
  <p>This div has a dashed border on all sides.</p>
</div>
```

### Width Controls

```html
<div class="print-w-50">
  <p>This div takes up 50% of the available width.</p>
</div>

<div class="print-w-75">
  <p>This div takes up 75% of the available width.</p>
</div>
```

### Background Colors

```html
<div class="print-bg-light">
  <p>This div has a light gray background when printed.</p>
</div>

<div class="print-bg-dark print-text-white">
  <p>This div has a dark background with white text when printed.</p>
</div>
```

### Page Break Controls

```html
<h2 class="avoid-break-after">Section Title</h2>
<p>This paragraph will stay with its heading.</p>

<table class="avoid-break-inside">
  <!-- Table content that should not be split across pages -->
</table>

<div class="break-before">
  <h2>New Chapter</h2>
  <p>This begins a new page.</p>
</div>
```

### Float Controls

```html
<img src="small-image.jpg" alt="Descriptive text" class="print-float-right">
<p>This text will wrap around the image, which is floated to the right.</p>
<div class="print-clear"></div>
```

## Complete Example

Here's a more complete example showing how multiple features work together:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Project Status Report</title>
    <link rel="stylesheet" href="print.css" media="print">
</head>
<body data-document-title="Project Status Report - Q1 2025">
    <h1>Project Alpha Status Report</h1>
    <p>Reporting period: January-March 2025</p>
    
    <div class="print-callout">
        <p><strong>Executive Summary:</strong> Project Alpha is currently on schedule 
        and within budget. Key milestones for Q1 have been achieved.</p>
    </div>
    
    <h2>Project Metrics</h2>
    <div class="two-columns">
        <p>Overall completion is at 68%, which is 3% ahead of projected timeline. 
        Team velocity has increased by 12% since the previous quarter, largely due 
        to improved development processes and reduced technical debt.</p>
        
        <p>Budget utilization stands at 62% of allocated resources, putting the project 
        2% under budget projections. This margin allows for contingency planning for 
        upcoming integration challenges in Q2.</p>
    </div>
    
    <div class="avoid-break">
        <h3>Key Performance Indicators</h3>
        <table>
            <thead>
                <tr>
                    <th>Metric</th>
                    <th>Target</th>
                    <th>Current</th>
                    <th>Status</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Task Completion</td>
                    <td>65%</td>
                    <td>68%</td>
                    <td>On Track</td>
                </tr>
                <tr>
                    <td>Budget Utilization</td>
                    <td>64%</td>
                    <td>62%</td>
                    <td>Under Budget</td>
                </tr>
                <tr>
                    <td>Team Velocity</td>
                    <td>85 points</td>
                    <td>92 points</td>
                    <td>Exceeding</td>
                </tr>
            </tbody>
        </table>
    </div>
    
    <div class="page-break"></div>
    
    <h2>Risk Assessment</h2>
    <div class="print-box">
        <h4 class="print-m-0">Current Risk Level: <span class="print-text-lg">MODERATE</span></h4>
    </div>
    
    <h3>Active Risks</h3>
    <table class="print-table-compact">
        <thead>
            <tr>
                <th>Risk Factor</th>
                <th>Impact</th>
                <th>Probability</th>
                <th>Mitigation</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>API Integration Delays</td>
                <td>High</td>
                <td>Medium</td>
                <td>Early testing with mock endpoints initiated</td>
            </tr>
            <tr>
                <td>Database Performance</td>
                <td>High</td>
                <td>Low</td>
                <td>Scaling plan developed; monitoring implemented</td>
            </tr>
        </tbody>
    </table>
    
    <h2>Next Steps</h2>
    <ol>
        <li>Complete API integration testing by April 15th</li>
        <li>Conduct second round of user acceptance testing</li>
        <li>Prepare deployment documentation</li>
        <li>Schedule training sessions for end users</li>
    </ol>
    
    <div class="print-callout print-mt-2">
        <p><strong>Note:</strong> Planning for the next quarterly review meeting will 
        begin in the first week of June.</p>
    </div>
    
    <div class="print-only print-mt-2 print-text-right print-text-sm">
        <p>Generated on: 2025-02-26 23:17:31<br>
        User: phaedra-casadio-2</p>
    </div>
</body>
</html>
```

This example demonstrates how the print stylesheet transforms a standard HTML document into a professional, print-ready report with proper page layout, typography, and organization.
