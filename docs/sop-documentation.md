**STANDARD OPERATING PROCEDURE**

**Using NVDA with Google Docs**

  -----------------------------------------------------------------------
  **Document Number**   SOP-NVDA-GD-001
  --------------------- -------------------------------------------------
  **Title**             Standard Operating Procedure -- NVDA with Google
                        Docs

  **Version**           1.2

  **Effective Date**    June 18, 2026

  **Review Date**       June 18, 2027 (Annual Review)

  **Document Owner**    Accessibility Team

  **Classification**    Internal Use

  **Status**            Active
  -----------------------------------------------------------------------

## Revision History

  ------------------------------------------------------------------------
  **Version**    **Date**       **Author**      **Description of Change**
  -------------- -------------- --------------- --------------------------
  1.0            Jan 10, 2026   Accessibility   Initial release.
                                Team            

  1.1            Jun 18, 2026   Document Review Corrected duplicate
                                                sections; added missing
                                                Section 7.6; resolved
                                                numbering conflict;
                                                completed truncated
                                                content; expanded
                                                definitions; aligned
                                                shortcut references.

  1.2            Jun 18, 2026   Document Review Corrected screen reader
                                                enable shortcut
                                                (Ctrl+Alt+Z); corrected
                                                Section 3 definition;
                                                fixed Section 7.6 heading
                                                menu path (Ctrl+Alt+1--6);
                                                corrected Section 7.8
                                                comment shortcut
                                                distinction; added NVDA
                                                shortcut conflict warning
                                                in Section 5; corrected
                                                troubleshooting shortcut
                                                (NVDA+4/5 → NVDA+S);
                                                clarified Section 7.3
                                                focus entry; updated
                                                Appendix A.
  ------------------------------------------------------------------------

# Table of Contents

# 1. Purpose

This Standard Operating Procedure (SOP) establishes a consistent method
for accessing, reading, navigating, editing, and reviewing documents in
Google Docs using NVDA (NonVisual Desktop Access).

The procedure is intended to improve productivity, ensure accessibility,
and support users who rely on screen reader technology for document
creation and collaboration.

The objectives of this procedure are to:

- Promote consistent use of Google Docs with NVDA.

- Improve efficiency in document authoring and review activities.

- Support accessibility compliance requirements, including WCAG 2.2.

- Reduce user errors caused by inconsistent navigation methods.

- Provide guidance for accessibility validation and quality assurance
  activities.

# 2. Scope

This procedure applies to:

- Blind and visually impaired users.

- Accessibility testers.

- Technical writers.

- Documentation specialists.

- Educators and students using NVDA.

- Employees creating or reviewing documents in Google Docs.

This SOP covers basic and intermediate tasks performed within Google
Docs using NVDA.

# 3. Definitions

  -----------------------------------------------------------------------
  **Term**                     **Definition**
  ---------------------------- ------------------------------------------
  **NVDA**                     NonVisual Desktop Access -- a free,
                               open-source screen reader for Microsoft
                               Windows.

  **Google Docs**              A cloud-based word processing application
                               developed by Google, accessible at
                               docs.google.com.

  **Screen Reader Support**    A Google Docs feature (enabled via
                               Ctrl+Alt+Z on Windows) that optimizes
                               document interaction for screen reader
                               users.

  **Browse Mode**              An NVDA mode that allows navigation of web
                               content using single-key commands (H, K,
                               L, T, G, etc.). Active by default in web
                               browsers.

  **Focus Mode**               An NVDA mode that passes keystrokes
                               directly to the application, enabling text
                               entry. Toggled with NVDA+Space
                               (Insert+Space).

  **Heading**                  A structural element (H1--H6) used to
                               organize content within a document.

  **Suggestion Mode**          A Google Docs collaboration feature that
                               allows proposed changes to be reviewed
                               before acceptance.

  **Alternative Text (Alt      A text description added to images and
  Text)**                      non-text content so screen readers can
                               convey the information to users who cannot
                               see the image.

  **WCAG**                     Web Content Accessibility Guidelines -- a
                               set of internationally recognized
                               standards published by the W3C for making
                               web content accessible.

  **Heading Hierarchy**        The logical, sequential ordering of
                               heading levels (H1 \> H2 \> H3) in a
                               document to convey structure and enable
                               efficient navigation.

  **ARIA**                     Accessible Rich Internet Applications -- a
                               W3C specification that defines how to make
                               web content and applications more
                               accessible to users with disabilities.
  -----------------------------------------------------------------------

# 4. Roles and Responsibilities

### User

The user shall:

- Follow the procedures described in this document.

- Verify document accuracy before distribution.

- Report accessibility issues to appropriate personnel.

### Accessibility Reviewer

The reviewer shall:

- Verify document accessibility.

- Validate heading structure.

- Confirm compatibility with NVDA.

### System Administrator

The administrator shall:

- Maintain browser updates.

- Support software installations.

- Resolve technical issues related to accessibility tools.

# 5. Prerequisites

Before beginning this procedure, verify that:

- NVDA is installed and operational.

- Internet connectivity is available.

- A Google account is active.

- Google Chrome or Mozilla Firefox is installed.

- Keyboard access is available.

- The user has permission to access the target document.

- The NVDA startup keyboard shortcut has been checked for conflicts with
  Google Docs (see note below).

  -----------------------------------------------------------------------
  **⚠ NOTE:** The default NVDA desktop shortcut (Ctrl+Alt+N) conflicts
  with Google Docs navigation commands. Before using NVDA with Google
  Docs, right-click the NVDA desktop shortcut, open Properties \>
  Shortcut tab, and change the shortcut key to a non-conflicting
  combination such as Ctrl+Alt+Slash. This is required by Google\'s
  official accessibility guidance.
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# 6. Supported Environment

  -----------------------------------------------------------------------
  **Component**           **Supported Version**   **How to Verify**
  ----------------------- ----------------------- -----------------------
  NVDA                    Latest Stable Release   Help \> About NVDA
                          (2024.4+)               

  Google Chrome           Latest Stable Release   Chrome \> Help \> About
                          (122+)                  Google Chrome

  Mozilla Firefox         Latest Stable Release   Help \> About Firefox
                          (123+)                  

  Windows                 Windows 10 (22H2) or    Settings \> System \>
                          Windows 11              About

  Google Docs             Current Web Version     No version number; use
                                                  supported browsers
                                                  above
  -----------------------------------------------------------------------

# 7. Procedure

## 7.1 Launching Google Docs

### Objective

Open a Google Docs document using a supported web browser.

### Procedure

1.  Launch Google Chrome or Mozilla Firefox.

2.  Navigate to docs.google.com.

3.  Sign in using your Google account.

4.  Open an existing document or create a new document.

### Expected Result

The document opens successfully and keyboard focus is available within
the editing area.

## 7.2 Enabling Screen Reader Support

### Objective

Enable accessibility features optimized for NVDA.

### Procedure

1.  Open the desired document in a supported browser.

2.  Press Ctrl + Alt + Z (Windows) to toggle screen reader support on.

3.  Listen for the confirmation message: \"Screen reader support
    enabled.\"

4.  Alternatively, go to Tools \> Accessibility settings, check \'Turn
    on screen reader support\', and press Enter.

### Expected Result

Google Docs announces that screen reader support has been enabled. NVDA
will now correctly identify headings, lists, tables, and links within
the document.

## 7.3 Reading Document Content

### Objective

Review document content using NVDA.

### Procedure

1.  Press NVDA + Space to switch NVDA to Focus Mode, then click or press
    Enter inside the document body to place the text cursor.

2.  Use the Up Arrow and Down Arrow keys to read line by line.

3.  Press NVDA + Down Arrow to begin continuous reading from the current
    position.

4.  Press Ctrl at any point to stop continuous reading.

5.  Review content for accuracy and completeness.

### Expected Result

NVDA reads document content correctly and continuously, announcing each
line and paragraph.

## 7.4 Navigating Document Structure

### Objective

Navigate efficiently through document elements using NVDA Browse Mode
commands.

### Procedure

Ensure NVDA is in Browse Mode (press NVDA + Space to toggle if needed).
Navigate using the following commands:

  ------------------------------------------------------------------------
  **Command**            **Action**               **Notes**
  ---------------------- ------------------------ ------------------------
  H                      Next Heading             Navigates to the next
                                                  heading of any level.

  Shift + H              Previous Heading         Navigates to the
                                                  previous heading.

  K                      Next Link                Moves to the next
                                                  hyperlink.

  Shift + K              Previous Link            Moves to the previous
                                                  hyperlink.

  L                      Next List                Jumps to the next
                                                  bulleted or numbered
                                                  list.

  Shift + L              Previous List            Jumps to the previous
                                                  list.

  T                      Next Table               Moves to the next table
                                                  in the document.

  Shift + T              Previous Table           Moves to the previous
                                                  table.

  G                      Next Graphic / Image     Moves to the next image
                                                  or graphic element.

  Shift + G              Previous Graphic         Moves to the previous
                                                  graphic.

  NVDA + Space           Toggle Browse / Focus    Switch between Browse
                         Mode                     Mode (navigation) and
                                                  Focus Mode (text entry).

  NVDA + F7              Elements List            Opens a dialog listing
                                                  all headings, links,
                                                  form fields, and tables
                                                  for quick navigation.
  ------------------------------------------------------------------------

### Expected Result

The user can navigate document sections and elements efficiently without
reviewing every line.

## 7.5 Editing Document Content

### Objective

Create or modify document content using the keyboard.

### Procedure

1.  Press NVDA + Space to switch NVDA to Focus Mode, enabling direct
    text entry.

2.  Move the cursor to the desired location using Arrow keys, or Ctrl +
    Home / Ctrl + End to jump to the document start or end.

3.  Enter new text or modify existing content as required.

4.  Review changes using NVDA reading commands: press NVDA + Down Arrow
    for continuous reading, or use Arrow keys for line-by-line review.

5.  Press NVDA + Space to return to Browse Mode when editing is
    complete.

### Expected Result

Content is entered accurately and can be reviewed using NVDA reading
commands. NVDA announces inserted and deleted text as changes are made.

## 7.6 Applying and Verifying Headings

### Objective

Apply correct heading levels and verify heading structure using NVDA.

### Procedure

1.  Place the cursor on the paragraph to be designated as a heading.

2.  Apply the heading using a direct keyboard shortcut: press Ctrl +
    Alt + 1 for Heading 1, Ctrl + Alt + 2 for Heading 2, up to Ctrl +
    Alt + 6 for Heading 6. Press Ctrl + Alt + 0 to return text to Normal
    style.

3.  Alternatively, open the Format menu (Alt + Shift + O in Firefox;
    Alt + O in Chrome), navigate to Paragraph Styles, and select the
    desired heading level.

4.  After applying headings, press NVDA + Space to enter Browse Mode.

5.  Press H to navigate forward through all headings and verify the
    announced heading level is correct (e.g., NVDA will announce
    \"heading level 1\").

6.  Press NVDA + F7 and select the Headings tab to view the full heading
    hierarchy at once and confirm no levels are skipped.

### Expected Result

Heading levels are correctly applied and announced by NVDA. The heading
hierarchy is logical (H1 \> H2 \> H3) with no skipped levels.

## 7.7 Working with Lists

### Objective

Create accessible bulleted and numbered lists.

### Procedure

1.  Position the cursor where the list should begin.

2.  Apply a bulleted list with Ctrl + Shift + 8, or a numbered list with
    Ctrl + Shift + 7.

3.  Enter list items, pressing Enter after each item.

4.  Press Tab to create a sub-list (nested item); press Shift + Tab to
    return to the previous level.

5.  Press Enter twice or Backspace on an empty list item to exit the
    list.

6.  Verify list structure: press NVDA + Space to enter Browse Mode, then
    press L to navigate to the list and confirm NVDA announces the list
    type and items.

### Expected Result

List items are properly identified and announced by NVDA. NVDA announces
the list type (bulleted or numbered) and the total number of items.

## 7.8 Reviewing Comments and Suggestions

### Objective

Review and respond to collaborative feedback using NVDA.

### Procedure

1.  To insert a new comment, press Ctrl + Alt + M. The comment box will
    open; type the comment and press Tab to reach the Post button, then
    press Enter.

2.  To navigate between existing comments, use Ctrl + Alt + N then C
    (next comment) or Ctrl + Alt + P then C (previous comment).

3.  When focused on a comment anchor in the document, NVDA will announce
    the comment presence. Press NVDA + Space to enter Focus Mode to
    interact with the comment pane.

4.  Read comment content as NVDA announces it. Use J and K to move
    between comments when the comment pane is active.

5.  Press R to reply to the active comment; type the reply and press Tab
    to the Post button.

6.  To review suggested edits (Suggestion Mode), navigate to the
    suggestion and press Enter to view change details. Accept or reject
    using the available toolbar buttons.

### Expected Result

Comments and suggested edits are fully accessible and can be processed
using keyboard navigation and NVDA announcements.

## 7.9 Verifying Accessibility

### Objective

Ensure the document remains accessible before sharing or publishing.

### Procedure

Verify the following elements are in place:

- Headings are used correctly and follow a logical hierarchy (H1 \> H2
  \> H3, no skipped levels).

- Lists are properly structured using Ctrl+Shift+7/8, not created with
  manual hyphens or indentation.

- Tables contain meaningful row or column headers.

- Hyperlinks contain descriptive text (not \'click here\' or bare URLs).

- Images include alternative text describing their content or purpose.

- Document language is set correctly (File \> Language).

### Expected Result

The document complies with accessibility best practices and is fully
navigable using NVDA.

## 7.10 Saving and Closing Documents

### Objective

Confirm document preservation and safely close the document.

### Procedure

1.  Verify all changes have been made.

2.  Confirm automatic saving status by listening for NVDA to announce
    the \'Saving...\' or \'All changes saved\' indicator in the toolbar
    area.

3.  If needed, press Ctrl + S to trigger an immediate sync (Google Docs
    saves automatically; Ctrl+S forces a manual sync).

4.  Close the document tab using Ctrl + W when finished.

### Expected Result

All modifications are successfully saved and confirmed before the
document is closed.

# 8. Troubleshooting

  ------------------------------------------------------------------------
  **Issue**             **Possible Cause**    **Resolution**
  --------------------- --------------------- ----------------------------
  NVDA does not read    Screen reader support Press Ctrl + Alt + Z to
  content               disabled              enable screen reader
                                              support.

  Single-key navigation NVDA is in Focus Mode Press NVDA + Space to switch
  (H, K, L, etc.) not   instead of Browse     back to Browse Mode.
  working               Mode                  

  Cannot type text into NVDA is in Browse     Press NVDA + Space to switch
  document              Mode                  to Focus Mode before typing.

  Slow navigation       Large document size   Refresh the page (F5) or
                                              divide the document into
                                              smaller sections.

  Unexpected or         Browser extension     Disable conflicting browser
  excessive             conflict              extensions and retest.
  announcements                               

  NVDA speech is        NVDA speech mode has  Press NVDA + S to cycle
  unexpectedly silent   been changed          through speech modes (Talk,
  or only beeping                             Beeps, Off) until normal
                                              speech resumes.

  NVDA speech lags      Large document or low Close other applications,
  significantly         system resources      reduce document size, or use
                                              heading navigation instead
                                              of continuous reading.

  Google Docs shortcuts NVDA desktop shortcut Change the NVDA desktop
  conflict with NVDA    uses Ctrl+Alt+N,      shortcut to a
                        which is reserved by  non-conflicting key
                        Google Docs           combination (e.g.
                                              Ctrl+Alt+Slash). See Section
                                              5.

  Document not          Improper document     Review the Accessibility
  accessible (poor      structure             Testing Checklist (Section
  structure)                                  14) and correct heading,
                                              list, table, and image
                                              issues.
  ------------------------------------------------------------------------

# 9. Best Practices

- Use heading levels consistently; never skip levels (e.g., do not jump
  from H1 to H3).

- Avoid excessive manual formatting; use Google Docs built-in styles for
  structure.

- Use descriptive hyperlink text (e.g., \'NVDA User Guide\' not \'click
  here\').

- Provide meaningful alternative text for all images; mark purely
  decorative images appropriately.

- Verify accessibility before sharing or publishing any document.

- Keep NVDA and supported browsers updated to the latest stable release.

- Perform periodic accessibility reviews, especially after significant
  document revisions.

- Test with NVDA in both Browse Mode and Focus Mode to confirm all
  content is accessible.

- Change the NVDA desktop shortcut before using it with Google Docs to
  avoid Ctrl+Alt+N conflicts.

# 10. References

1.  NV Access -- NVDA User Guide. Available at:
    https://www.nvaccess.org/files/nvda/documentation/userGuide.html

2.  Google -- Use Google Docs Editors with a Screen Reader. Available
    at: https://support.google.com/docs/answer/6282736

3.  Google -- Use Google Docs with a Screen Reader. Available at:
    https://support.google.com/docs/answer/1632201

4.  Google -- Keyboard Shortcuts for Google Docs. Available at:
    https://support.google.com/docs/answer/179738

5.  W3C -- Web Content Accessibility Guidelines (WCAG) 2.2,
    October 2023. Available at: https://www.w3.org/TR/WCAG22/

6.  NV Access -- NVDA Releases and Change Log. Available at:
    https://www.nvaccess.org/download/

7.  Organizational Accessibility Policies -- refer to internal policy
    repository for the current version.

# 11. Accessibility Compliance (WCAG 2.2 Mapping)

This procedure supports compliance with the following WCAG 2.2 success
criteria.

  -----------------------------------------------------------------------
  **WCAG 2.2           **Description**      **Application in this SOP**
  Criterion**                               
  -------------------- -------------------- -----------------------------
  1.1.1 Non-text       Alternative text for Users verify image alt text
  Content              images               before publication (Section
                                            7.9).

  1.3.1 Info and       Proper document      Headings, lists, and tables
  Relationships        structure            are used appropriately
                                            (Sections 7.6, 7.7).

  1.3.2 Meaningful     Logical reading      NVDA navigation verifies
  Sequence             order                document reading flow
                                            (Section 7.3).

  2.1.1 Keyboard       Keyboard-only        All procedures are performed
  Accessible           operation            using keyboard commands only.

  2.4.1 Bypass Blocks  Efficient navigation Heading navigation (H key)
                                            enables quick movement past
                                            repeated content.

  2.4.3 Focus Order    Logical focus        Keyboard focus order is
                       sequence             verified during navigation
                                            (Section 7.4).

  2.4.4 Link Purpose   Link text describes  Descriptive hyperlink text is
                       destination          required (Section 7.9, Best
                                            Practices).

  2.4.6 Headings and   Clear document       Heading levels are applied
  Labels               structure            and verified consistently
                                            (Section 7.6).

  2.4.7 Focus Visible  Visible keyboard     Focus tracking is verified
                       focus                during navigation (Section
                                            7.4).

  3.1.1 Language of    Language             Document language must be
  Page                 identification       correctly set (File \>
                                            Language) as verified in
                                            Section 7.9.

  3.3.2 Labels or      Clear guidance for   Forms and controls must
  Instructions         input                contain descriptive labels
                                            accessible to NVDA.

  4.1.2 Name, Role,    Compatibility with   NVDA interaction verifies
  Value                assistive technology that all elements correctly
                                            expose name, role, and value.
  -----------------------------------------------------------------------

### Compliance Verification

Prior to document publication, users shall verify that:

- All headings follow a logical hierarchy with no skipped levels.

- Images contain meaningful alternative text.

- Tables contain appropriate row or column headers.

- Links use descriptive text.

- Lists are properly structured.

- Document language is correctly identified.

- Document content is fully navigable using NVDA.

# 12. Risk and Limitations

## 12.1 Risks

The following risks may impact accessibility or productivity:

  -----------------------------------------------------------------------
  **Risk**              **Impact**            **Mitigation**
  --------------------- --------------------- ---------------------------
  Screen reader support Navigation            Enable screen reader
  disabled              difficulties          support using Ctrl + Alt +
                                              Z.

  NVDA shortcut         Navigation shortcuts  Change the NVDA desktop
  conflicts with Google fail to work          shortcut from Ctrl+Alt+N to
  Docs                                        a non-conflicting key
                                              before use (see Section 5).

  Improper heading      Reduced document      Validate headings before
  structure             accessibility         publication (Section 7.6).

  Missing alternative   Loss of information   Review all images before
  text on images        for screen reader     publishing (Section 7.9).
                        users                 

  Browser               Reduced functionality Use supported browser
  incompatibility                             versions listed in Section
                                              6.

  Unsupported browser   Unpredictable NVDA    Disable incompatible
  extensions            behavior              extensions and retest.
  -----------------------------------------------------------------------

## 12.2 Limitations

The following limitations should be considered:

- Google Docs accessibility features may vary between browser versions.

- Some advanced formatting features may not be fully exposed to screen
  readers.

- Third-party browser extensions may interfere with accessibility
  functionality.

- Large documents may cause slower NVDA response times during
  navigation.

- Certain collaborative editing features may generate excessive speech
  output.

# 13. Change Management Procedure

## 13.1 Purpose

The purpose of change management is to ensure that modifications to this
procedure are documented, reviewed, approved, and communicated to all
affected users.

## 13.2 Change Request Process

1.  Submit Change Request: The requester shall document the proposed
    modification, reason for change, expected impact, and required
    implementation date.

2.  Review: The document owner shall evaluate accessibility impact,
    process impact, user training requirements, and compliance
    implications.

3.  Approval: Changes shall be approved by designated reviewers before
    implementation.

4.  Implementation: Approved changes shall be incorporated into the
    document.

5.  Verification: Accessibility testing shall be conducted to confirm
    the change does not negatively affect users.

6.  Documentation: The Revision History table shall be updated to
    reflect the approved change.

## 13.3 Change Classification

  -----------------------------------------------------------------------
  **Change Type**              **Description**
  ---------------------------- ------------------------------------------
  **Minor Change**             Grammar corrections, spelling fixes, minor
                               formatting updates.

  **Moderate Change**          Procedure updates, workflow modifications,
                               keyboard shortcut corrections.

  **Major Change**             Structural revisions, compliance updates,
                               new accessibility requirements, or
                               addition of new procedures.
  -----------------------------------------------------------------------

# 14. Accessibility Testing Checklist

Complete this checklist before distributing or publishing any document.

  ------------------------------------------------------------------------
  **Document Structure**           **Pass**      **Fail**     **N/A**
  -------------------------------- ------------- ------------ ------------
  Heading hierarchy is logical (H1 ☐             ☐            ☐
  \> H2 \> H3, no skipped levels)                             

  Lists are properly structured    ☐             ☐            ☐
  (not created with manual                                    
  hyphens/spaces)                                             

  Tables contain row or column     ☐             ☐            ☐
  headers                                                     

  Reading order is logical         ☐             ☐            ☐

  Document language is correctly   ☐             ☐            ☐
  identified (File \> Language)                               

  **Non-Text Content**             **Pass**      **Fail**     **N/A**

  All images contain meaningful    ☐             ☐            ☐
  alternative text                                            

  Decorative images are marked     ☐             ☐            ☐
  appropriately (empty alt text or                            
  marked as decorative)                                       

  **Navigation**                   **Pass**      **Fail**     **N/A**

  NVDA can navigate headings       ☐             ☐            ☐
  correctly using H key (Browse                               
  Mode)                                                       

  NVDA can navigate lists          ☐             ☐            ☐
  correctly using L key (Browse                               
  Mode)                                                       

  NVDA can navigate tables         ☐             ☐            ☐
  correctly using T key (Browse                               
  Mode)                                                       

  NVDA can navigate links          ☐             ☐            ☐
  correctly using K key (Browse                               
  Mode)                                                       

  NVDA Elements List (NVDA + F7)   ☐             ☐            ☐
  displays all headings correctly                             

  **Links**                        **Pass**      **Fail**     **N/A**

  All link text is descriptive of  ☐             ☐            ☐
  the link destination                                        

  No generic \'Click Here\' or     ☐             ☐            ☐
  bare URL links exist                                        

  **Review**                       **Pass**      **Fail**     **N/A**

  Continuous reading (NVDA + Down  ☐             ☐            ☐
  Arrow) functions correctly                                  
  throughout document                                         

  Comments are accessible via      ☐             ☐            ☐
  Ctrl+Alt+N then C (next comment                             
  navigation)                                                 

  Suggestions in Suggestion Mode   ☐             ☐            ☐
  are accessible                                              

  Entire document reviewed using   ☐             ☐            ☐
  NVDA from start to finish                                   
  ------------------------------------------------------------------------

  -----------------------------------------------------------------------
  **Tester Name:**                    
  ----------------------------------- -----------------------------------
  **Date Tested:**                    

  **NVDA Version:**                   

  **Browser and Version:**            

  **Overall Result:**                 ☐ Pass ☐ Pass with Exceptions ☐
                                      Fail

  **Comments / Exceptions:**          
  -----------------------------------------------------------------------

# Appendix A -- Complete Keyboard Shortcut Reference

All keyboard shortcuts referenced in this SOP. Shortcuts marked with \*
are Google Docs commands; all others are NVDA commands.

  -----------------------------------------------------------------------
  **Shortcut**            **Function**            **Context**
  ----------------------- ----------------------- -----------------------
  Ctrl + Alt + Z \*       Enable / Toggle Screen  Google Docs (Windows)
                          Reader Support          

  NVDA + Down Arrow       Begin Continuous        NVDA -- Browse Mode
                          Reading                 

  Ctrl                    Stop Continuous Reading NVDA

  NVDA + Space            Toggle Browse / Focus   NVDA
                          Mode                    

  NVDA + S                Cycle Speech Mode (Talk NVDA
                          / Beeps / Off)          

  NVDA + F7               Open Elements List      NVDA -- Browse Mode
                          (Headings, Links,       
                          Tables)                 

  H / Shift + H           Next / Previous Heading NVDA -- Browse Mode

  K / Shift + K           Next / Previous Link    NVDA -- Browse Mode

  L / Shift + L           Next / Previous List    NVDA -- Browse Mode

  T / Shift + T           Next / Previous Table   NVDA -- Browse Mode

  G / Shift + G           Next / Previous Graphic NVDA -- Browse Mode
                          / Image                 

  Ctrl + Alt + 1--6 \*    Apply Heading Level     Google Docs
                          1--6                    

  Ctrl + Alt + 0 \*       Apply Normal (Body)     Google Docs
                          Text Style              

  Ctrl + Shift + 7 \*     Apply Numbered List     Google Docs

  Ctrl + Shift + 8 \*     Apply Bulleted List     Google Docs

  Ctrl + Alt + M \*       Insert New Comment      Google Docs

  Ctrl + Alt + N then C   Navigate to Next        Google Docs (screen
  \*                      Comment                 reader mode)

  Ctrl + Alt + P then C   Navigate to Previous    Google Docs (screen
  \*                      Comment                 reader mode)

  Alt + Shift + O \*      Open Format Menu        Google Docs
  (Firefox) / Alt + O                             
  (Chrome)                                        

  Ctrl + S \*             Force Manual Save /     Google Docs
                          Sync                    

  Ctrl + F \*             Find Text in Document   Google Docs

  Ctrl + H \*             Find and Replace        Google Docs

  Ctrl + W                Close Document Tab      Browser

  Ctrl + Home / Ctrl +    Jump to Start / End of  Google Docs
  End \*                  Document                
  -----------------------------------------------------------------------

# Approval

  ------------------------------------------------------------------------
  **Role**               **Name / Signature**     **Date**
  ---------------------- ------------------------ ------------------------
  **Prepared By**                                 

  **Reviewed By**                                 

  **Approved By**                                 
  ------------------------------------------------------------------------

*Document Number: SOP-NVDA-GD-001 \| Version: 1.2 \| Effective Date:
June 18, 2026*
