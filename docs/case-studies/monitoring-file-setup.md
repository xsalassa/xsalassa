# Daily checkpoint preparation with Google Apps Script

The selected PRD script prepares a dated monitoring workbook and coordinates the schedules and checks around it. The diagram below follows the copied implementation, including its early return when today's file already exists.

## Actual PRD flow

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="../../assets/flows/monitoring-file-setup-dark.png">
  <img src="../../assets/flows/monitoring-file-setup.png" width="1080" height="614" alt="Actual PRD daily-checkpoint flow: validate, schedule, locate file, preserve existing file or create and populate a new workbook, then save links and runtime state">
</picture>

[Editable Mermaid source](../../assets/flows/monitoring-file-setup.mmd). This is a code-based flow summary, not a production execution trace.

1. `copyTemplateDaily` reads generic Script Properties, opens the template and validates its structure.
2. It refreshes the schedule, classifies the date and resolves PIC assignments. Nonworking dates use the next working day's first PIC for both roles. Three or more consecutive nonworking dates form a long holiday.
3. It locates or creates the year/month Drive folders and checks for today's daily file.
4. **Existing file:** validate it, refresh runtime properties, log `ALREADY_EXISTS`, preserve its contents and return. This branch does not rebuild sheets or continue to master-link updates.
5. **New file:** create an empty spreadsheet, copy the template sheets without its bound script, apply the weekday/nonworking profile, populate dates/PICs, update formulas and master links, and save runtime/history information.

Weekends and holidays select different workbook profiles; they do not automatically stop daily-file preparation. This source does not implement the earlier article's Monday creation of multiple historical daily files.

## Later monitoring checks

| Check | Selected source behavior |
| --- | --- |
| Looker | Scheduled checks with a separate nonworking-day policy |
| File status | Scheduled check against BigQuery-backed metadata |
| Platform monitoring | Separate weekday and nonworking-day handlers |
| Airflow status | Manual from the sidebar; trigger setup removes old scheduled Airflow handlers |
| Holiday edits | On-edit schedule refresh and pending-change warning |
| Daily file | Optional time trigger or manual invocation |

These are configured entry points, not proof that the triggers or external integrations were enabled.

## Code and validation

The selected Apps Script modules and runtime components document template preparation, trigger configuration, day classification and schedule handling. Organization labels, project/workspace identifiers, selected branch codes and notification addresses use generic aliases. Workbook data, source documents, deployment identity and live Script Properties are excluded.

Five local Node tests cover calendar classification, long holidays/next-workday behavior, recipient parsing, subject separators, HTML includes and macro resolution. No hosted Apps Script run, permission grant, email, API call or workbook write was performed. Test partial creation, duplicate invocations, conflicting schedules and quotas in a dedicated synthetic environment before adapting.

## Earlier article

Xsalassa, [How to Avoid Repetitive Manual Work with One Google Apps Script](https://medium.com/edts/how-to-avoid-repetitive-manual-work-with-one-google-apps-script-5b776674407a), published May 8, 2026. The article is background for the template-copy pattern; the diagram and behavior above come from the later selected PRD code. The historical article log capture is documented separately in visual provenance and is not a fresh run log.
