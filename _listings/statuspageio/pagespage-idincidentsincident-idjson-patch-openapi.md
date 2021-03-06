---
swagger: "2.0"
x-collection-name: StatusPage.io
x-complete: 0
info:
  title: StatusPage.io Update an incident (only applies to realtime and scheduled
    incidents)
  version: 1.0.0
  description: Update an incident (only applies to realtime and scheduled incidents)
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /pages/[page_id]/incidents.json:
    get:
      summary: Get a list of all incidents
      description: Get a list of all incidents
      operationId: get-a-list-of-all-incidents
      x-api-path-slug: pagespage-idincidentsjson-get
      responses:
        200:
          description: OK
      tags:
      - Incidents
    post:
      summary: Create a realtime incident
      description: Create a realtime incident
      operationId: create-a-realtime-incident
      x-api-path-slug: pagespage-idincidentsjson-post
      parameters:
      - in: query
        name: incident[backfilled]
        description: Must be set to t
        type: string
      - in: query
        name: incident[backfill_date]
        description: Date of incident in YYYY
        type: string
      - in: query
        name: incident[component_ids]
        description: List of components whose subscribers should be notified (only
          applicable for pages with component subscriptions enabled)
        type: string
      - in: query
        name: incident[impact_override]
        description: Override calculated impact value, one of none|minor|major|critical
          (optional)
        type: string
      - in: query
        name: incident[message]
        description: The initial message, created as the first incident update (optional)
        type: string
      - in: query
        name: incident[name]
        description: The name of the incident
        type: string
      - in: query
        name: incident[scheduled_auto_completed]
        description: Automatically transition incident to Completed at end (optional,
          t or f, defaults to f)
        type: string
      - in: query
        name: incident[scheduled_auto_in_progress]
        description: Automatically transition incident to In Progress at start (optional,
          t or f, defaults to f)
        type: string
      - in: query
        name: incident[scheduled_for]
        description: time the scheduled maintenance should begin (ISO8601 format)
        type: string
      - in: query
        name: incident[scheduled_remind_prior]
        description: Remind subscribers 60 minutes before scheduled start (optional,
          t or f, defaults to f)
        type: string
      - in: query
        name: incident[scheduled_until]
        description: time the scheduled maintenance should end (ISO8601 format)
        type: string
      - in: query
        name: incident[status]
        description: The status, one of investigating|identified|monitoring|resolved
          (optional, defaults to investigating if left blank)
        type: string
      - in: query
        name: incident[wants_twitter_update]
        description: Post the new incident to twitter (t or f, defaults to f)
        type: string
      responses:
        200:
          description: OK
      tags:
      - Incidents
  /pages/[page_id]/incidents/unresolved.json:
    get:
      summary: Unresolved Only
      description: Unresolved Only
      operationId: unresolved-only
      x-api-path-slug: pagespage-idincidentsunresolvedjson-get
      responses:
        200:
          description: OK
      tags:
      - Incidents
  /pages/[page_id]/incidents/scheduled.json:
    get:
      summary: Scheduled Only
      description: Scheduled Only
      operationId: scheduled-only
      x-api-path-slug: pagespage-idincidentsscheduledjson-get
      responses:
        200:
          description: OK
      tags:
      - Incidents
  /pages/[page_id]/incidents/[incident_id].json:
    patch:
      summary: Update an incident (only applies to realtime and scheduled incidents)
      description: Update an incident (only applies to realtime and scheduled incidents)
      operationId: update-an-incident-only-applies-to-realtime-and-scheduled-incidents
      x-api-path-slug: pagespage-idincidentsincident-idjson-patch
      parameters:
      - in: query
        name: at the same time to avoid two separate incident updates being generated.
        type: string
      - in: query
        name: ENDPOINT
        type: string
      - in: query
        name: incident[component_ids]
        description: List of components whose subscribers should be notified (only
          applicable for pages with component subscriptions enabled)
        type: string
      - in: query
        name: incident[impact_override]
        description: Override calculated impact value, one of none|minor|major|critical
          (optional)
        type: string
      - in: query
        name: incident[message]
        description: The body of the new incident update that will be created (optional)
        type: string
      - in: query
        name: incident[name]
        description: The name of the incident
        type: string
      - in: query
        name: incident[status]
        description: The status, one of investigating|identified|monitoring|resolved
          (if realtime) or scheduled|in_progress|verifying|completed (if scheduled)
        type: string
      - in: query
        name: incident[wants_twitter_update]
        description: Post the new incident update to twitter (t or f, defaults to
          f)
        type: string
      - in: query
        name: MUTABLE
        type: string
      - in: query
        name: PATCH /pages/[page_id]/incidents/[incident_id].json
        type: string
      responses:
        200:
          description: OK
      tags:
      - Incidents
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---