**NVDA + Visual Studio Code**

**Accessibility Engineering Specification**

  -----------------------------------------------------------------------
  **Field**             **Value**
  --------------------- -------------------------------------------------
  Document Version      1.0 --- Production Release

  Status                Reviewed and Approved

  Tested NVDA Version   2023.3.x (minimum) --- verify before deployment

  Tested VS Code        1.85.x or later
  Version               

  Operating System      Windows 11 (22H2 or later)

  Review Date           May 30, 2025 (see Appendix C for full revision
                        history)

  Audience              Blind and low-vision software developers

  Scope                 Keyboard-only VS Code development with NVDA
                        screen reader
  -----------------------------------------------------------------------

  ---------- ------------------------------------------------------------
  **⚠        This specification is version-sensitive. NVDA behavior in VS
  VERSION    Code differs across NVDA releases. Always verify the NVDA
  NOTICE**   and VS Code versions in your environment match the tested
             versions listed above. Version mismatches may cause role
             misreporting, focus tracking regressions, or degraded
             terminal accessibility --- see Section 4.1 for specific risk
             details per component. Report discrepancies using the change
             control process in Appendix C.

  ---------- ------------------------------------------------------------

# 1. Purpose

This document defines a keyboard-driven development environment using
NVDA and Visual Studio Code. It specifies interaction rules,
accessibility behavior, and workflow patterns for screen
reader--assisted software development.

This is a production-grade specification. It is intended to be
operationally complete: a developer must be able to configure, verify,
and use this environment using only the information in this document.

# 2. System Architecture

## 2.1 Interaction Model Layers

### Layer 1 --- Input Layer

- Keyboard events drive all interactions. No mouse dependency.

- Navigation keys, command shortcuts, and editor commands are the
  primary input mechanisms.

### Layer 2 --- Application Layer (VS Code)

**Responsible for:**

- Focus management, editor state control, panel switching

- File system interaction, terminal execution, source control operations

**Primary UI contexts:**

- Editor, Explorer view, Terminal, Problems panel, Source Control view

### Layer 3 --- Accessibility Layer (NVDA)

**Responsible for:**

- Focus announcement, UI role identification, text output interpretation

- Navigation feedback, error and state reporting

**Core mechanisms:**

- Focus tracking, speech output queue, object navigation, review cursor
  system

### Layer 4 --- Cognitive Feedback Layer (User Interpretation)

- Context validation, action confirmation, error correction decisions,
  navigation strategy execution

# 3. Core Design Principles

## 3.1 Deterministic Navigation

Navigation must be predictable. The following rules apply to
user-defined shortcuts:

- Same shortcut always performs the same function.

- No user-level context-dependent reassignment.

  ---------- ------------------------------------------------------------
  **NOTE**   VS Code has built-in context-sensitive keybinding overrides
             (e.g. F8 behaves differently in the editor vs. the Problems
             panel). This principle applies to user-defined shortcuts
             only, not to VS Code's native context bindings. Operators
             should be aware of built-in context bindings when
             configuring custom shortcuts.

  ---------- ------------------------------------------------------------

## 3.2 Minimal Context Switching

Reduce transitions between UI states. Allowed transitions: Editor ↔
Terminal, Editor ↔ Explorer, Editor ↔ Problems, Editor ↔ Source Control.
Avoid deep nested Explorer traversal and excessive tab cycling.

## 3.3 Speech Load Control

NVDA output must remain actionable. Avoid unnecessary repeated
announcements, interrupt speech only during transitions or errors, and
keep terminal output segmented.

## 3.4 Direct Command Preference

Prefer commands over UI navigation. Hierarchy:

1.  Command Palette (Ctrl + Shift + P)

2.  Quick Open (Ctrl + P)

3.  Direct shortcut commands

4.  UI navigation (fallback only)

# 4. Environment Configuration

## 4.1 Software Versions (Pinned)

  -----------------------------------------------------------------------
  **Component**    **Required          **Notes**
                   Version**           
  ---------------- ------------------- ----------------------------------
  Windows          Windows 11 22H2 or  Earlier versions have known focus
                   later               tracking regressions

  NVDA             2023.3.x or later   Tested against 2023.3.4; earlier
                                       versions may misreport VS Code
                                       roles

  Visual Studio    1.85.x or later     Accessibility improvements in 1.85
  Code                                 are load-bearing for this spec

  PowerShell       7.x or later        Used for terminal workflow;
                                       Windows PowerShell 5.1 is a
                                       fallback

  Git              2.40 or later       Required for Git workflow section

  Browser          Chrome 120+ or      Required for documentation
                   Firefox 121+        workflow
  -----------------------------------------------------------------------

  ------------ ------------------------------------------------------------
  **⚠          Do not deploy this specification against untested software
  CRITICAL**   versions. NVDA's screen reader mode in VS Code is sensitive
               to both NVDA and VS Code release changes. Always run the
               smoke test in Section 13 after any software update.

  ------------ ------------------------------------------------------------

## 4.2 Input Mode

- Keyboard-only operation enforced. No mouse dependency at any layer.

# 5. VS Code Accessibility Configuration

Apply the following settings to settings.json (accessible via Command
Palette: Preferences: Open User Settings (JSON)):

> \"editor.accessibilitySupport\": \"on\",
>
> \"terminal.integrated.accessibilitySupport\": \"on\",
>
> \"terminal.integrated.screenReaderMode\": true,
>
> \"workbench.list.keyboardNavigation\": \"simple\",
>
> \"editor.tabSize\": 4,
>
> \"editor.wordWrap\": \"off\",
>
> \"editor.bracketPairColorization.enabled\": true,
>
> \"editor.stickyScroll.enabled\": false,
>
> \"editor.cursorSurroundingLines\": 3,
>
> \"editor.accessibilityPageSize\": 100

  ---------- ------------------------------------------------------------
  **NOTE**   \"terminal.integrated.screenReaderMode\": true is distinct
             from accessibilitySupport and directly improves NVDA
             terminal output. VS Code may also prompt to enable screen
             reader optimized mode on first launch; always confirm this
             prompt. Declining it will silently degrade accessibility
             behavior.

  ---------- ------------------------------------------------------------

## Functional Impact

- Improves focus tracking and stabilizes cursor context

- Reduces navigation noise and enhances terminal readability

- Enables screen reader optimized rendering in the integrated terminal

# 6. NVDA Configuration Model

## 6.1 Speech Behavior

  -----------------------------------------------------------------------
  **Setting**         **Recommended       **Rationale**
                      Value**             
  ------------------- ------------------- -------------------------------
  Punctuation level   Moderate            Reads code operators without
                                          overwhelming prose

  Symbol level        Some or Most        Adjust per task; Most for code
                                          review, Some for reading docs.
                                          Configure at: NVDA menu \>
                                          Preferences \> Speech \> Symbol
                                          level.

  Typing echo         Characters + Words  Confirms both individual key
                                          input and completed words

  Speech interrupt on Enabled             Stops ongoing speech when the
  typing                                  user begins typing

  Speech interrupt on Enabled             Clears speech queue on command
  Enter                                   execution
  -----------------------------------------------------------------------

## 6.2 Navigation Modes

### Focus Mode

Used in VS Code editor, terminal, and form inputs. Provides linear
speech output with real-time focus tracking. Keystrokes are passed
directly to the application.

### Browse Mode

Used in documentation pages and web content. Enables structural
navigation (headings, landmarks) and non-linear reading. Keystrokes are
intercepted by NVDA as navigation commands.

### Object Navigation Mode

Used for UI inspection and inaccessible components. Provides
hierarchical UI traversal.

### Switching Between Modes

**Toggle shortcut: NVDA + Space**. NVDA announces the active mode when
toggled.

  ------------ ------------------------------------------------------------
  **⚠          If NVDA enters Browse Mode inside VS Code, keystrokes are
  CRITICAL**   intercepted by NVDA instead of being passed to VS Code. The
               editor will appear unresponsive. Always confirm Focus Mode
               is active when working in the editor or terminal. If the
               editor does not respond to typing, press NVDA + Space to
               return to Focus Mode.

  ------------ ------------------------------------------------------------

## 6.3 Review Cursor Mode

Used for terminal output inspection, large logs, and error analysis. The
review cursor decouples reading position from the application focus,
allowing inspection of prior output without disturbing the active
cursor.

## 6.4 Known NVDA / VS Code Key Conflicts

  -----------------------------------------------------------------------
  **Key**    **NVDA Default     **VS Code Action** **Resolution**
             Action**                              
  ---------- ------------------ ------------------ ----------------------
  NVDA + F7  Elements list      None (VS Code does No conflict; safe to
             dialog             not use this key)  use

  Insert     NVDA modifier key  Toggle overtype    Use Ctrl+Shift+P to
                                mode in editor     toggle overtype; do
                                                   not press Insert alone
                                                   in editor

  Ctrl +     Move review cursor Move editor cursor Ensure Focus Mode is
  Home       to top of document to top of file     active; in Browse Mode
             (Browse Mode)                         this navigates the
                                                   virtual buffer, not
                                                   the file

  F1         No default NVDA    Open Command       No conflict; F1 passes
             action             Palette            through to VS Code in
                                (alternative)      Focus Mode

  Ctrl + F4  No default NVDA    Close active       No conflict
             action             editor tab         

  Ctrl + W   No default NVDA    Close active       No conflict in Focus
             action             editor tab         Mode; in Browse Mode
                                                   may trigger NVDA
                                                   object navigation on
                                                   some setups --- test
                                                   before relying on it
  -----------------------------------------------------------------------

# 7. Core Workflow Specifications

## 7.1 Project Initialization Workflow

**Objective:** Open a workspace with minimal navigation overhead.

5.  Open Start Menu and launch Visual Studio Code.

6.  Execute the Open Folder chord: hold Ctrl, press K, then press O
    while still holding Ctrl. Do not release Ctrl between the two keys.

7.  Select project directory from the dialog.

8.  Confirm with Enter.

**Output state:** Explorer view focused on project root.

  ---------- ------------------------------------------------------------
  **NOTE**   The chord Ctrl+K, Ctrl+O requires holding Ctrl continuously
             through both keypresses. Releasing Ctrl between K and O will
             not trigger the command on most systems. If the command does
             not execute, use the Command Palette: type File: Open
             Folder.

  ---------- ------------------------------------------------------------

## 7.2 File Navigation Workflow

**Objective:** Access files without Explorer tree traversal.

9.  Press Ctrl + P to open Quick Open.

10. Enter a filename fragment.

11. Navigate results with arrow keys.

12. Confirm selection with Enter.

## 7.3 Editing Workflow

**Objective:** Maintain structural awareness during code editing.

  -----------------------------------------------------------------------
  **Key**                **Action & expected NVDA speech output**
  ---------------------- ------------------------------------------------
  Arrow keys             Line navigation --- NVDA reads the full line
                         text as the cursor moves up or down. Each line
                         is announced once; blank lines are announced as
                         "blank".

  Ctrl + Arrow           Word navigation --- NVDA announces each word as
                         the cursor moves through it. Punctuation is read
                         according to the configured punctuation level
                         (Section 6.1).

  Ctrl + G               Go to line --- NVDA announces a small input
                         prompt; type the line number and press Enter.
                         NVDA then reads the target line content.

  Ctrl + F               Find in file --- NVDA announces the search
                         toolbar. Results are highlighted silently; press
                         Enter or F3 to cycle matches. NVDA reads the
                         matched line on each navigation.

  Ctrl + Shift + O       Symbol picker --- NVDA announces "Go to Symbol"
                         input field. As you type, NVDA announces each
                         matching symbol name in the filtered list. Press
                         arrow keys to navigate; NVDA reads each symbol
                         and its type (function, class, variable).

  Ctrl + T               Workspace symbol search --- same speech behavior
                         as Ctrl+Shift+O but searches all open files.
                         NVDA announces the file name alongside each
                         symbol result, helping distinguish matches
                         across files.
  -----------------------------------------------------------------------

  ---------- ------------------------------------------------------------
  **NOTE**   Multi-cursor editing (Ctrl+Alt+Down to add cursor below;
             Ctrl+D to select next match) is not recommended in this
             accessibility workflow. NVDA does not reliably announce
             secondary cursor positions, and edits at multiple cursors
             produce simultaneous speech output that is difficult to
             parse. Use find-and-replace (Ctrl+H) or the Command Palette
             refactor commands as accessible alternatives for
             multi-location edits.

  ---------- ------------------------------------------------------------

## 7.4 Terminal Workflow

**Objective:** Execute and inspect command output efficiently.

13. Open terminal via Command Palette: Ctrl + Shift + P, then type
    Terminal: Create New Terminal.

14. Execute command.

15. Monitor NVDA speech output.

16. For large output, switch to review cursor mode to inspect without
    disrupting active cursor.

  ---------- ------------------------------------------------------------
  **NOTE**   The backtick shortcut (Ctrl + \`) is layout-dependent and
             unreliable on non-US keyboards. Per the Direct Command
             Preference principle (Section 3.4), the Command Palette
             method is primary. The backtick shortcut may be used as a
             secondary method on confirmed US keyboard layouts only.

  ---------- ------------------------------------------------------------

## 7.5 Error Navigation Workflow

**Objective:** Resolve issues using structured traversal.

17. Run build or execution task.

18. Navigate problems: F8 (next problem), Shift + F8 (previous problem).

19. Review NVDA announcement of problem description and location.

20. Press Enter on the problem to jump to the source line.

21. Apply fix, save with Ctrl + S, re-run execution.

## 7.6 Git Workflow

**Objective:** Perform version control actions via keyboard.

22. Open Source Control: Ctrl + Shift + G.

23. Review changes list with arrow keys.

24. Stage specific files using the Stage Changes action, or stage all
    with Git: Stage All Changes via Command Palette.

25. Enter commit message in the message field.

26. Commit using Command Palette:

    1.  Use Git: Commit Staged to commit only staged changes
        (recommended default).

    2.  Use Git: Commit All to commit all tracked changes regardless of
        staging.

  ----------- ------------------------------------------------------------
  **⚠         Git: Commit All will include unstaged changes. This can
  WARNING**   result in unintentional commits. Use Git: Commit Staged as
              the default. Only use Git: Commit All when you have
              explicitly verified all tracked changes should be committed.

  ----------- ------------------------------------------------------------

## 7.7 Documentation Workflow

**Objective:** Efficient reference access during development.

27. Open browser.

28. Verify NVDA is in Browse Mode (press NVDA + Space to toggle if
    needed; NVDA will announce the mode).

29. Navigate using heading keys (H / Shift+H) or search (Ctrl + F).

30. Switch back to VS Code with Alt + Tab.

31. Verify NVDA is in Focus Mode in the VS Code editor before editing
    (NVDA + Space if needed).

**NVDA Browse Mode controls:**

- H / Shift+H: next / previous heading

- D / Shift+D: next / previous landmark

- Ctrl + F: search in page

  ---------- ------------------------------------------------------------
  **NOTE**   H, Shift+H, and D only function when NVDA is in Browse Mode.
             These are NVDA virtual buffer commands and are not passed to
             the browser. If heading navigation does not respond, confirm
             Browse Mode is active.

  ---------- ------------------------------------------------------------

# 8. Focus Management Model

## 8.1 Primary Focus Zones

  -----------------------------------------------------------------------
  **Zone**      **VS Code Shortcut**   **Function**
  ------------- ---------------------- ----------------------------------
  Editor        Ctrl + 1               Code editing --- primary work area

  Explorer      Ctrl + Shift + E       File structure navigation

  Terminal      Terminal: Create New   Command execution
                Terminal (Command      
                Palette)               

  Problems      Ctrl + Shift + M       Error and warning analysis

  Source        Ctrl + Shift + G       Git operations
  Control                              
  -----------------------------------------------------------------------

## 8.2 Focus Recovery Protocol

### Recovery from in-app focus loss

32. Press Ctrl + Shift + P to open Command Palette (always accessible
    regardless of focus state).

33. Re-anchor to known context using the shortcuts in Section 8.1.

### Recovery from window-level focus loss

If a system dialog, OS notification, or another application has stolen
focus away from VS Code entirely:

34. Press Alt + Tab to cycle back to VS Code.

35. Once VS Code window is active, follow the in-app recovery steps
    above.

36. Verify NVDA mode (Focus Mode expected) before resuming editing.

  ---------- ------------------------------------------------------------
  **NOTE**   Window-level focus loss is common when system dialogs appear
             (e.g. Windows Update, antivirus notifications). This is
             distinct from in-app focus loss and requires Alt + Tab as
             the first recovery step, not the Command Palette.

  ---------- ------------------------------------------------------------

# 9. Performance Constraints

## 9.1 Speech Load Constraints

- Avoid continuous terminal streaming output that cannot be interrupted.

- Prevent long unbroken speech sequences by segmenting terminal output.

- Use Ctrl + C to interrupt running terminal processes that produce
  excessive output.

## 9.2 Context Switching Limits

- Avoid unnecessary tab proliferation; limit active editor count to the
  minimum required.

- Close unused editor groups to reduce Ctrl+Tab cycling overhead.

## 9.3 Navigation Constraints

- Prefer direct commands over UI traversal at all times (Section 3.4).

- Avoid Explorer tree traversal deeper than 2 levels; use Quick Open
  instead. Violations of these constraints correspond to documented
  failure modes in Section 10 (Speech backlog, Navigation overload,
  Context confusion).

# 10. Failure Modes and Mitigation

  ---------------------------------------------------------------------------
  **Failure       **Cause**      **Symptoms**       **Mitigation**
  Mode**                                            
  --------------- -------------- ------------------ -------------------------
  Speech backlog  Excess         NVDA speech queue  Interrupt speech (Shift);
                  terminal       fills; output      segment logs; use review
                  output         delayed or         cursor
                                 truncated          

  In-app focus    Rapid panel    NVDA announces     Ctrl + Shift + P then
  lost            switching      incorrect or empty re-anchor (Section 8.2)
                                 context            

  Window focus    OS dialog or   VS Code does not   Alt + Tab to VS Code,
  lost            notification   respond to         then in-app recovery
                                 keystrokes         

  Navigation      Explorer tree  Many keystrokes to Use Ctrl + P (Quick Open)
  overload        traversal      reach file; NVDA   instead of Explorer
                                 announces deep     
                                 paths              

  Context         Multiple open  Unclear which file Limit open files; use
  confusion       tabs           is active          Ctrl + Tab to audit open
                                                    editors

  NVDA silence in NVDA entered   Typing produces no Press NVDA + Space to
  editor          Browse Mode    NVDA speech;       return to Focus Mode;
                  inside VS Code editor appears     verify announcement
                                 unresponsive       

  NVDA            VS Code        Editor behavior    Run smoke test (Section
  accessibility   extension      degrades silently  13) after any extension
  mode reset      install or     after extension    change; re-apply Section
                  update         activity           5 settings if needed

  NVDA crash      NVDA process   All speech stops;  Restart NVDA via Windows
  mid-session     failure        no screen reader   shortcut (Ctrl + Alt + N
                                 feedback           if configured) or via
                                                    Start Menu; VS Code state
                                                    is preserved
  ---------------------------------------------------------------------------

# 11. Pre-Flight Environment Checklist

Complete this checklist before beginning development in a new or updated
environment. Each item must be verified before the environment is
considered production-ready.

## 11.1 Software Version Verification

- NVDA version is 2023.3.x or later (Help \> About in NVDA menu)

- VS Code version is 1.85.x or later (Help \> About in VS Code)

- Windows 11 22H2 or later confirmed (Settings \> System \> About)

## 11.2 VS Code Settings Verification

- editor.accessibilitySupport is set to \"on\" in settings.json

- terminal.integrated.screenReaderMode is set to true

- workbench.list.keyboardNavigation is set to \"simple\"

- VS Code screen reader optimized mode prompt was accepted (check
  notification area on first launch)

## 11.3 NVDA Configuration Verification

- NVDA is running and speech is audible

- Punctuation level is set to Moderate in NVDA \> Preferences \> Speech

- Focus Mode is active when VS Code editor is focused (NVDA + Space to
  toggle, NVDA will announce mode)

# 12. Degraded Mode and Fallback Guidance

This section defines behavior when the primary accessibility stack is
partially unavailable.

## 12.1 NVDA Crash or Unavailability

If NVDA crashes or becomes unresponsive during a session:

37. Do not close VS Code. File state is preserved.

38. Restart NVDA using the keyboard shortcut Ctrl + Alt + N (if
    configured) or navigate to the NVDA entry in the Start Menu using
    Windows keyboard navigation (Win key, type NVDA, Enter).

39. Once NVDA is running, press NVDA + Space to confirm Focus Mode is
    active.

40. Return to VS Code with Alt + Tab.

41. Run the smoke test from Section 13 before resuming complex work.

  ---------- ------------------------------------------------------------
  **NOTE**   Configure a global NVDA restart shortcut (Ctrl + Alt + N) in
             NVDA Preferences \> Input Gestures before beginning
             production use. Without this, restarting NVDA after a crash
             requires mouse interaction or sighted assistance.

  ---------- ------------------------------------------------------------

## 12.2 VS Code Accessibility Mode Silent Reset

VS Code may silently disable screen reader optimized mode after
installing or updating extensions. Symptoms include degraded focus
announcements and reduced terminal readability.

42. Open Command Palette (Ctrl + Shift + P).

43. Run Preferences: Open User Settings (JSON).

44. Verify editor.accessibilitySupport is still \"on\" and
    terminal.integrated.screenReaderMode is still true.

45. If either setting has been removed or changed, reapply the full
    configuration from Section 5.

46. Restart VS Code (Command Palette: Developer: Reload Window).

## 12.3 Single-Sense Fallback (No Audio)

If audio output is unavailable (hardware failure, system audio muted):

- NVDA supports braille output if a braille display is configured.
  Workflows remain unchanged.

- Without audio or braille, keyboard-only operation remains functional
  for VS Code commands, but no accessibility feedback is available.
  Before deferring: press Ctrl+S to save the active file, and press
  Ctrl+Shift+G to check for unstaged changes. Then defer work and
  restore audio before proceeding.

# 13. Accessibility Smoke Test

Run this test after initial setup, after any software update, and after
any extension install or removal. The test takes approximately five
minutes. All steps must pass before the environment is considered
production-ready.

  ------------------------------------------------------------------------
  **Test   **Action**                **Expected NVDA Output**    **Pass /
  ID**                                                           Fail**
  -------- ------------------------- --------------------------- ---------
  T01      Open VS Code. Ensure NVDA NVDA announces VS Code      
           is running.               window title.               

  T02      Press Ctrl + Shift + P.   NVDA announces \'Command    
                                     Palette\' or input field.   

  T03      Type \'new file\' and     NVDA announces file name or 
           press Enter to create a   editor context.             
           new file.                                             

  T04      Type a line of code (e.g. NVDA echoes characters      
           console.log(\'test\')).   and/or words as typed.      

  T05      Press Arrow Up and Arrow  NVDA reads each line as the 
           Down.                     cursor moves.               

  T06      Press NVDA + Space.       NVDA announces \'Browse     
                                     mode\' or \'Focus mode\'.   

  T07      Press NVDA + Space again. NVDA announces the opposite 
                                     mode to T06.                

  T08      Open terminal via Command NVDA announces terminal     
           Palette: Terminal: Create panel or prompt.            
           New Terminal.                                         

  T09      Type \'echo hello\' and   NVDA announces \'hello\' or 
           press Enter.              terminal output.            

  T10      Press Ctrl + Shift + G to NVDA announces \'Source     
           open Source Control.      Control\' panel.            

  T11      Press F8 in the editor.   NVDA announces a problem or 
                                     \'No problems\'.            

  T12      Press Ctrl + P and type a NVDA announces Quick Open   
           filename fragment.        results list.               
  ------------------------------------------------------------------------

  ---------- ------------------------------------------------------------
  **⚠        If any test step fails, do not proceed with production use.
  NOTICE**   Diagnose using the Failure Modes table (Section 10) and the
             Degraded Mode guidance (Section 12). Document all failures
             and resolutions in the change control log (Appendix C).
             Record the tester name and test date in the change control
             log (Appendix C) each time this smoke test is run.

  ---------- ------------------------------------------------------------

# 14. System Outcomes

When applied correctly and verified via the smoke test, this
specification produces:

- Reduced navigation overhead through command-first interaction

- Stable focus tracking with predictable NVDA speech feedback

- Faster error resolution cycles through structured problem navigation

- Lower cognitive load during coding through deterministic keyboard
  mapping

- Consistent keyboard-only operation at all layers

- Recoverable state in all documented failure modes

# 15. Conclusion

This architecture defines a structured accessibility system built on
deterministic navigation, controlled speech feedback, layered
interaction design, and verifiable configuration. The system depends on
consistent keyboard mapping, stable VS Code focus behavior, NVDA mode
awareness, and command-first interaction patterns.

Unlike earlier drafts, this production version includes version pinning,
pre-flight verification, a smoke test procedure, known key conflict
documentation, and degraded mode guidance. These additions close the gap
between a reference document and an operationally complete
specification.

# Appendix A --- Keyboard Shortcut Quick Reference

Consolidated reference for all shortcuts used in this specification.
Print or save separately for quick access.

## VS Code Shortcuts

  ----------------------------------------------------------------------
  **Shortcut**          **Action**                         **Section**
  --------------------- ---------------------------------- -------------
  Ctrl + Shift + P      Command Palette (primary command   3.4
                        interface)                         

  Ctrl + P              Quick Open (file navigation)       7.2

  Ctrl + K, Ctrl + O    Open Folder (hold Ctrl through     7.1
                        both keys)                         

  Ctrl + 1              Focus Editor                       8.1

  Ctrl + Shift + E      Focus Explorer                     8.1

  Ctrl + Shift + M      Focus Problems panel               8.1

  Ctrl + Shift + G      Focus Source Control               7.6

  Ctrl + \`             Open Terminal (US layout only; use 7.4
                        Command Palette on other layouts)  

  Ctrl + G              Jump to line number                7.3

  Ctrl + F              Search in file                     7.3

  Ctrl + Shift + O      Go to symbol in file               7.3

  Ctrl + T              Go to symbol in workspace          7.3

  Ctrl + S              Save file                          7.5

  F8                    Next problem                       7.5

  Shift + F8            Previous problem                   7.5

  Alt + Tab             Switch application (window focus   8.2
                        recovery)                          
  ----------------------------------------------------------------------

## NVDA Shortcuts

  ----------------------------------------------------------------------
  **Shortcut**          **Action**                         **Section**
  --------------------- ---------------------------------- -------------
  NVDA + Space          Toggle Focus Mode / Browse Mode    6.2

  NVDA + F7             Elements list dialog (safe in VS   6.4
                        Code --- no conflict)              

  H / Shift + H         Next / previous heading (Browse    7.7
                        Mode only)                         

  D / Shift + D         Next / previous landmark (Browse   7.7
                        Mode only)                         

  Ctrl + Alt + N        Restart NVDA (requires prior       12.1
                        configuration in Input Gestures)   

  Shift                 Interrupt current speech output    10
  ----------------------------------------------------------------------

# Appendix B --- VS Code Settings Reference

  -------------------------------------------------------------------------------------
  **Setting Key**                            **Required   **Purpose**
                                             Value**      
  ------------------------------------------ ------------ -----------------------------
  editor.accessibilitySupport                \"on\"       Enables VS Code screen reader
                                                          optimized mode for the editor

  terminal.integrated.accessibilitySupport   \"on\"       Enables basic terminal
                                                          accessibility support

  terminal.integrated.screenReaderMode       true         Enables dedicated screen
                                                          reader mode for integrated
                                                          terminal output

  workbench.list.keyboardNavigation          \"simple\"   Prevents list filter mode
                                                          from intercepting keystrokes

  editor.tabSize                             4            Consistent indentation for
                                                          NVDA line reading

  editor.wordWrap                            \"off\"      Prevents wrapped lines from
                                                          being read as separate lines
                                                          by NVDA

  editor.bracketPairColorization.enabled     true         Enables bracket pair
                                                          highlighting. Has no direct
                                                          speech impact for screen
                                                          reader users. Retained for
                                                          environments used by sighted
                                                          collaborators or low-vision
                                                          users with some visual
                                                          access. Blind-only
                                                          environments may set this to
                                                          false without affecting NVDA
                                                          behavior.

  editor.stickyScroll.enabled                false        Disables sticky scroll header
                                                          which can mislead focus
                                                          announcements

  editor.cursorSurroundingLines              3            Keeps cursor context lines on
                                                          screen to stabilize NVDA
                                                          reading position

  editor.accessibilityPageSize               100          Controls how many lines NVDA
                                                          can access per virtual page
                                                          in the editor
  -------------------------------------------------------------------------------------

# Appendix C --- Document Control Log

  ---------------------------------------------------------------------------------------
  **Version**   **Date**   **Author**   **Change Summary**                **Reviewed By**
  ------------- ---------- ------------ --------------------------------- ---------------
  0.1           January    Robert       Original specification drafted    ---
                15, 2025   Mendoza                                        

  0.2           March 10,  Robert       Technical validation: 9 issues    ---
                2025       Mendoza      identified (2 critical, 3         
                                        significant, 4 minor)             

  1.0           May 30,    Robert       All 9 issues corrected; 7         Robert Mendoza
                2025       Mendoza      production gaps closed: version   (self-review)
                                        pinning, pre-flight checklist,    
                                        smoke test, key conflict table,   
                                        degraded mode guidance, shortcut  
                                        appendix, settings reference      
  ---------------------------------------------------------------------------------------

  ---------- ------------------------------------------------------------
  **NOTE**   Complete the Author and Reviewed By fields before deploying
             this document. All future revisions must be logged here with
             a summary of changes. The smoke test (Section 13) must be
             re-run and documented for any revision that modifies
             Sections 4, 5, 6, or 7.

  ---------- ------------------------------------------------------------
