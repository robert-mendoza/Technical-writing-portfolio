# Google Drive File Management Process

**Process Documentation**

| Field | Detail |
|---|---|
| **Document Title** | Google Drive File Management Process |
| **Document Type** | Process Documentation |
| **Version** | 1.3 |
| **Author** | Robert Mendoza |
| **Review Date** | May 8, 2026 |
| **Approval Status** | Draft |

## 1. Purpose

This document defines the standard process for creating, organizing, managing, updating, sharing, and maintaining files and folders in Google Drive. The objective is to ensure consistent file management, improve collaboration, and support efficient document retrieval.

## 2. Scope

This process applies to all users who store, manage, and share documents within Google Drive. It covers file creation, folder organization, version control, file sharing, data sensitivity handling, access revocation, maintenance, and archival activities.

## 3. Objectives

The process aims to:

- Maintain a structured document repository.
- Reduce duplicate and outdated files.
- Improve document accessibility.
- Support collaboration among users.
- Ensure proper file version management.
- Match sharing permissions to data sensitivity.

## 4. Roles and Responsibilities

| Role | Responsibility |
|---|---|
| **Document Owner** | Creates, updates, and manages files; assigns sharing permissions at the file level. |
| **Collaborator** | Reviews, edits, or comments on shared files within the access level granted. |
| **Administrator** | Oversees access permissions and storage management; conducts quarterly sharing-permission audits (see Section 7); monitors storage quota usage; revokes access during user offboarding (see Section 6.1). |
| **End User** | Accesses and uses documents according to assigned permissions. |

*Table 1. Roles and responsibilities.*

## 5. Process Overview

The sequence below reflects all ten processes detailed in Section 6, in order.

1. Create Folder Structure
2. Upload Files
3. Create New Documents
4. Apply File Naming Convention
5. Organize Files
6. Share Files and Folders
7. Update Existing Files
8. Manage File Versions
9. Archive Obsolete Files
10. Delete Files

### 5.1 Data Sensitivity and Confidentiality

**Purpose**

Ensure that the sharing method and permission level applied to a file or folder match the sensitivity of its content.

**Classification Levels**

- **Public** — Suitable for "Anyone with the link" (Viewer) where external visibility is intended.
- **Internal** — Restricted to named individuals within the organization; link sharing limited to "Anyone in the organization" where supported.
- **Confidential** — Named, email-based sharing only; no "Anyone with the link" access; Editor access limited to the Document Owner and direct collaborators.
- **Restricted** — Named, email-based sharing only, with external sharing requiring Administrator approval; access list reviewed at every quarterly audit.

**Expected Outcome**

Files are shared using a method appropriate to their sensitivity, reducing the risk of unauthorized access.

## 6. Process Details

### Process 1: Create Folder Structure

**Purpose**

Establish a logical and organized repository for files.

**Recommended Folder Structure**

- Google Drive
    - Projects
        - Project A
        - Project B
    - SOP Documents
    - User Guides
    - Accessibility Reports
    - Training Materials
    - Archive

**Procedure**

1. Open Google Drive.
2. Select "New."
3. Choose "Folder."
4. Enter a descriptive folder name.
5. Click "Create."
6. Create subfolders as necessary.

**Expected Outcome**

Folders are organized according to business or project requirements.

### Process 2: Upload Files

**Purpose**

Store existing documents within Google Drive.

**Procedure**

1. Open the target folder.
2. Select "New."
3. Choose "File Upload" or "Folder Upload."
4. Select files from the local computer.
5. Wait for upload completion.

**Expected Outcome**

Files are successfully uploaded and available within the designated folder.

### Process 3: Create New Documents

**Purpose**

Create documents directly within Google Drive.

**Procedure**

1. Open the target folder.
2. Select "New."
3. Choose the desired document type — Google Docs, Google Sheets, Google Slides, Google Forms, Google Drawings, or other supported Google Workspace types.
4. Enter content.
5. Google Drive automatically saves changes.

**Expected Outcome**

New documents are created and stored within the correct folder.

### Process 4: Apply File Naming Convention

**Purpose**

Ensure files are easy to identify and locate.

**Naming Standard**

`DocumentType_ProjectName_Version_Date`

**Example:** `SOP_GoogleDriveManagement_1.0_2026-06-20`

**Procedure**

1. Determine the document type abbreviation (e.g., SOP, RPT, GDE).
2. Identify the associated project or business area name.
3. Apply the current version number in major.minor format (e.g., 1.0, 1.1, 2.0), without a "v" prefix.
4. Apply the date in YYYY-MM-DD format.
5. Combine elements using the naming standard above.

**Rules**

- Use descriptive names.
- Avoid special characters.
- Maintain consistent formatting.
- Include version numbers when applicable, formatted as shown in the example above so filenames match the template exactly.

**Expected Outcome**

Files follow a standardized naming convention.

### Process 5: Organize Files

**Purpose**

Maintain a structured document repository.

**Procedure**

1. Select the file.
2. Right-click.
3. Select "Move."
4. Choose the destination folder.
5. Confirm the move.

**Expected Outcome**

Files are stored within the appropriate folder.

### Process 6: Share Files and Folders

**Purpose**

Enable collaboration while maintaining security.

**Procedure**

1. Select the file or folder.
2. Right-click and select "Share."
3. To share with specific people: enter their email addresses and assign a permission level — Viewer, Commenter, or Editor — then select "Send."
4. To share via link: select "Get link," set the access level (Restricted, or Anyone with the link), and assign a permission level before copying and distributing the link.
5. Confirm that the permission level matches the data sensitivity classification of the file (see Section 5.1).

> **Note:** Avoid "Anyone with the link" access for Confidential or Restricted files (see Section 5.1). Prefer named, email-based sharing so access can be individually tracked and revoked.

**Expected Outcome**

Authorized users receive appropriate access permissions, and sharing method is matched to data sensitivity.

### 6.1 Access Revocation (Offboarding)

**Purpose**

Ensure that file and folder access is promptly removed when a user leaves a project, team, or the organization.

**Procedure**

1. Document Owner or Administrator identifies all files and folders the departing user owns or has access to.
2. Ownership of files required by the team is transferred to another active user before the departing user's access is removed.
3. The departing user is removed from all individual file and folder sharing lists.
4. Any "Anyone with the link" shares created by the departing user are reviewed and reset to restricted access where appropriate.
5. Administrator confirms removal and logs the offboarding action for audit purposes.

**Expected Outcome**

Former users retain no residual access to organizational files or folders.

### Process 7: Update Existing Files

**Purpose**

Maintain current and accurate documentation.

**Procedure**

1. Open the file.
2. Make necessary updates.
3. Review changes.
4. Allow changes to save automatically.
5. Update the version number in the filename if the naming convention described in Process 4 requires it.

**Expected Outcome**

The latest document version is available to users.

### Process 8: Manage File Versions

**Purpose**

Maintain document history and traceability.

**Procedure**

1. Open the file.
2. Select "File," then "Version History," then "See Version History."
3. Review previous versions.
4. Restore a version if required.
5. For business-critical versions, select "Keep forever" to prevent automatic cleanup.

> **Note:** Native Google Docs, Sheets, and Slides retain detailed, automatically saved version history. Uploaded files (e.g., Word, Excel, PDF) retain a more limited set of versions by default, and older revisions may be cleaned up over time. Pin critical versions of uploaded files using "Keep forever" to ensure they remain recoverable.

**Expected Outcome**

Document revisions are traceable and recoverable, for both native and uploaded file types.

### Process 9: Archive Obsolete Files

**Purpose**

Reduce clutter while preserving historical records.

**Procedure**

1. Identify inactive files (e.g., files with no edits for 12 months, or files associated with closed projects or superseded documentation).
2. Move files to the Archive folder.
3. Update archive records if applicable.
4. Restrict editing permissions if necessary.

**Expected Outcome**

Inactive documents remain accessible without affecting active repositories.

### Process 10: Delete Files

**Purpose**

Remove unnecessary documents.

**Procedure**

1. Verify the file is no longer required. Obtain written authorization from the Administrator or Document Owner before proceeding to permanent deletion.
2. Select the file, right-click, and select "Remove."
3. Allow the file to remain in Trash as a recovery buffer, unless immediate permanent deletion is authorized.
4. If permanent deletion is authorized and required immediately, manually empty Trash.

> **Note:** Files in Trash are automatically and permanently deleted after 30 days. This window serves as the default recovery buffer referenced in the Accidental Deletion mitigation in Section 7.

**Expected Outcome**

Obsolete files are removed from the repository, with a recovery window preserved unless immediate permanent deletion is required.

## 7. Risks and Mitigation

| Risk | Impact | Mitigation |
|---|---|---|
| Duplicate files | Confusion and version conflicts | Implement naming conventions; consolidate duplicates during folder reviews. |
| Incorrect permissions | Unauthorized access | Quarterly Administrator permission reviews; restrict link-sharing for confidential files (see Section 5.1). |
| Accidental deletion | Data loss | Use version history and backups; rely on the 30-day Trash recovery window before files are permanently purged. |
| Poor folder organization | Difficulty locating files | Maintain folder standards; periodic structure audits. |
| Unrevoked access after offboarding | Unauthorized access by former users | Follow the access revocation procedure in Section 6.1 whenever a user leaves a project or the organization. |

*Table 2. Identified risks and mitigations. Administrator permission audits occur quarterly.*

## 8. Key Performance Indicators (KPIs)

| KPI | Target | Measurement Method | Owner |
|---|---|---|---|
| File Retrieval Time | < 2 minutes | User-reported retrieval tests | Administrator |
| Folder Compliance Rate | 95% | Periodic folder structure audits | Administrator |
| Duplicate File Incidents | < 5% | Drive scan during quarterly review | Administrator |
| Document Update Compliance | 100% | Version history review | Document Owner |
| Quarterly Permission Audit Completion | 100% | Audit log completion records | Administrator |
| Storage Quota Utilization | Below 90% of allocated capacity | Google Drive storage dashboard | Administrator |

*Table 3. Key performance indicators.*

## 9. Best Practices

- Use descriptive folder names.
- Maintain consistent naming conventions.
- Review access permissions regularly.
- Archive outdated files once they meet the inactivity criteria defined in Process 9.
- Avoid storing duplicate documents.
- Use version history rather than creating multiple copies.
- Organize documents according to business function or project.
- Match sharing method to data sensitivity classification.
- Revoke access promptly when users leave a project or the organization.

## 10. Process Completion Criteria

The process is considered successful when:

- Files are uploaded successfully.
- Documents follow naming standards.
- Files are stored in the correct folders.
- Access permissions are assigned correctly and match data sensitivity.
- Version history is maintained.
- Obsolete files are archived or removed appropriately.
- Access is revoked promptly for offboarded users.

## Revision History

| Version | Date | Description |
|---|---|---|
| **1.0** | 2026-06-20 | Initial draft. |
| **1.1** | 2026-06-21 | Major revision: added data sensitivity and offboarding sections; expanded KPIs and Administrator responsibilities; corrected formatting and cross-references throughout. |
| **1.2** | 2026-06-22 | Applied validation findings: removed author placeholder; corrected Process 7 cross-reference label; added inactivity criterion to Process 9; clarified deletion authorization in Process 10; broadened Process 3 to include all Google Workspace document types; added Measurement Method and Owner columns to KPI table; condensed revision history entries. |
| **1.3** | 2026-07-15 | Applied validation findings: removed the manual Table of Contents in favor of MkDocs' auto-generated navigation/outline; corrected the Process 4 naming-convention section so the "Rules" bullets sit under their own heading instead of trailing after the Expected Outcome line; converted the process-flow diagram and all tables to clean Markdown formatting for consistent rendering. |
