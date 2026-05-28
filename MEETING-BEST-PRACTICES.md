## Best practices for SWICG-related meetings

### Task forces

#### Before the meeting

* The task force lead picks a meeting time.

* The task force lead sets up an online meeting space for that time. Many SWICG people prefer https://meet.jit.si.
  There isn't really a room to reuse, so pick a room that works for the event.

* The task force lead creates an issue in the Github repo of the task force with the draft agenda
  for the meeting. (Example: https://github.com/swicg/activitypub-e2ee/issues/82)

* The task force lead notifies one of the SWICG chairs that the meeting will take place with

  * Date, time, timezone, expected duration
  * Location (e.g. Jitsi URL)
  * Meeting title (e.g. "Meeting of the xyz Task Force")
  * Link to the Github issue tracker that contains the agenda (for repeat meetings, it might be easier to link to
    just the issue list and let people find the right issue for the next meeting themselves. Whatever works
    for the particular task force.))

* The SWICG chair puts the meeting on the W3C calendar.

* The task force lead sends the same info to the SWICG mailing list. Invite people to comment on the Github
  issue with the agenda if they have additions/suggestions.

* Consider publishing the meeting more broadly on the social web to attract attendees if that would be helpful.

#### During the meeting

* The task force lead makes sure an online document has been set up for note taking. The document should be
  editable by multiple people. Some services that have been used:

  * https://pad.w3.org -- hosted by the W3C, requires W3C login
  * HedgeDoc
  * HackMD
  * CryptPad
  * https://notes.socialcg.org/ -- run by Emelia, request an account if you like

* The task force lead shares that document in the meeting chat and identifies one or more people who will help with
  taking notes.

* Alternatively, or in addition, the meeting can be recorded. The recording and/or automated transcript
  of the recording is then published.

* The task force lead reminds attendees of the W3C Code of Conduct, and W3C IP policy.

#### After the meeting

* The task force lead turns the meeting notes into a pull request for the SWICG meeting repo at:
  https://github.com/swicg/meetings

* OR, the task force lead turns the meeting notes into a pull request for their own repository.

* Use the `meetings/YYYY-MM-DD-taskforce-meeting.md` naming scheme.

* A SWICG chair approves the pull request.

