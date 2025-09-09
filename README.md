
# Automations to drive Migration & Adoption programs

I've successfully retrieved the content from Tom Mcintire's personal space on the Autodesk wiki. This page documents how to use Airtable automations for driving migration and adoption programs. Here's the complete content:

## Overview

**Status**: This is a draft work in progress

**BLUF (Bottom Line Up Front)**: Automations provide a data-driven notification mechanism from Airtable to drive action from adopting teams programmatically based on the status of the adopting team's effort to adopt the migration.

## What are "Automations"

Automations are workflows executed against data in an Airtable base, triggered by either:
- State changes in data 
- Time-based events

The resulting workflows can:
- Update data in the Airtable base
- Dispatch emails
- Send Slack messages
- Perform other functions

*Reference*: [Automations Overview](https://support.airtable.com/docs/automations-overview-articles) (external link to Airtable.com)

## Purpose of Automations in the Program

- Provide consistent reminders to adopters to execute on migration programs with actionable information based on their current adoption status
- Include escalation paths in messaging automatically as needed
- Reduce the effort required by the managing TPM to "nag" teams to execute
- Manage data workflows based on state changes in data

## Elements of a Good Automated Action Message

### 1. Who is receiving this, and in what context:
List of the service, relevant owners being included (including escalation paths), and current risk level. This allows immediate understanding of context.

### 2. BLUF (Bottom Line Up Front) / Call to Action:
A one-liner describing why the user should continue reading and care about the message. Critical for engagement within the first 10 seconds.

### 3. Details:
More detailed information once the recipient has engaged.

#### How do I access my data in Airtable?
Provide links to the data so users can see status and make updates to user-editable fields.

#### Specifics of variants of the effort:
Different implementation requirements (e.g., Lambda/Serverless vs CloudOSv3) with decision trees.

### 4. How do I comply?
Specific steps needed for compliance, potentially including decision trees based on current status.

### 5. What if I have Questions?
References to documentation and direct contact methods for support.

## Sample Email Messages

The page references two sample email templates:
- [Sample Email for a service which is not currently tracked](https://wiki.autodesk.com/x/uP1Srw)
- [Sample Email Message for a Service which is currently tracked, but not up to date on effort to complete migration](https://wiki.autodesk.com/x/q-1Srw)

## Mechanics of Authoring Messages

### Step-by-Step Process:

1. **Add an Automation**: Select ***Automations*** at top center, then ***Create new...***

2. **Set a trigger**: First step - what causes the automation to occur (e.g., timer)

3. **Generate a Query**: Add **Find records** action to determine message recipients (e.g., all services with "Critical Risk" level)

4. **Iterate through records**: Add **Repeat for each in (list of records)** step

5. **Send email via Outlook**: Add **Outlook: Send email** step to the iterator

### Authoring the Text:

- Airtable uses Markdown format (not WYSIWYG)
- Recommendation: Use external Markdown editor, save as .md file, then copy/paste into Airtable
- Add custom fields from search query using the **+** sign
- Handle multi-level expansions (e.g., "DevOps Service Owner > Name")

### Preview the Message:
Use **Generate a preview** button to check content and formatting before deployment.

## Key Features

The page includes multiple screenshots showing:
- The Airtable automation interface
- Field selection and token insertion
- Message preview functionality
- Step-by-step configuration process
