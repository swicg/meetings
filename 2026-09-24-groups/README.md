# ActivityPub Groups Task Force 2026-09-24

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- @mayel@bonfire.cafe
- @ivan@bonfire.cafe
- Matthias Pfefferle <acct:pfefferle@mastodon.social>
- a <trwnh.com> (they/them)

## Agenda

- Introductions and administrative
  - [Code of conduct](https://www.w3.org/policies/code-of-conduct/)
  - [CLA](https://www.w3.org/community/about/process/cla/)
- Implementation progress and demos
- https://github.com/social-web-foundation/assembly.pub
- https://assembly.pub/
- Updates to report
- Old business
   - https://github.com/swicg/groups/pull/59
- New business
   - Wiped history. In [this commit](https://github.com/swicg/groups/commit/d2d5051fbbbcf6c534f23e820d93bd99c90f4db0), @trwnh  deleted hundreds of lines of code and text, without discussion, with a different solution than they put into their own report. I'd like to discuss this incident, how we work together, and the role of the task force leads in choosing different solutions.
   - Per https://github.com/swicg/groups/issues/58#issue-5293110546 -- "Auth is still an open question" for any endpoints we end up defining. Even in the default case, we need to clarify how to authorize requests to the inbox endpoint (POST/GET).
   - Per https://github.com/swicg/groups/issues/52#issuecomment-5063796717 -- how do we define which activities are within the group context and which ones aren't? Default/naive pattern is to just mix them in the inbox with no separation on the receiving end, and no clear indication on the object either (context? audience?). This can maybe be implicitly determined via a POST to a special collection...
   - (if we have time) https://github.com/swicg/groups/issues/46 provides the main way to publish activities to various activity streams (other than outbox/inbox). How do we manage the provisioning of arbitrary streams (like what others might call "spaces"?)

## Minutes

###  Implementation progress and demos
- https://github.com/social-web-foundation/assembly.pub
- https://assembly.pub/
- Mayel: Bonfire is federating public groups 1b12 + threadiverse-compatible + mobilizon
  - Testing with other live servers

### Updates to report

- None so far
- <dfn> tag now defines "group" instead of "entitativity"
  
### Old business

- https://github.com/swicg/groups/pull/59
- mayel: PR documents interaction policies and covers which parts applies to groups.
- Evan: do we have confirmation from gotosocial that it's officially been submitted to the CG?
- mayel: They agreed to the PR but we need to confirm if they have signed the CLA
- TODO: Evan to confirm with T&S TF about progress on using `interactionPolicy`
- mayel: interaction policies on group vs interaction policies on objects. In some ways you are operating on the groups' outbox.
- Evan: maybe more semantic to have it on the collection instead of on the group?
- mayel: I mention that in the issue as well, #26 on vocabulary vs just the general principle. We also need to define a vocabulary of verbs and things
- Evan: this follows from the user stories, right? not covered in the PR?
- mayel: yes it follows from user stories, but vocab is in the issue right now because it needs more discussion.
- MP: Can we define in ActivityPub new identifiers for permission values, like "as:Private"?
- a: how would that be different than using collections in the permission values?

- PROPOSE: resolve existing comments on PR 59 and merge to the main document. 
- RESOLVED
- Mayel and a to work through comments and merge at will, no need for further consensus.
- mayel: some comments are larger points about interactionPolicy/RDF so would be good to move those to the issue 

### New business

#### Wiped history

- EP: wiped history
- Group started in 2024
- 2025 - explainer with proposed solutions for the user stories
- report draft
- user stories -> report draft
- proposed solutions were removed but not moved to the report draft

a: I strongly object to the framing of the commit in question. The commit simply moved user stories to the ReSpec HTML document. Other content in the README was deleted, but it specified information written unilaterally by Evan with no discussion or consensus. Shortly afterward, the Groups TF started having regular meetings to gather consensus and discuss user stories and issues.

EP: the proposals in the current report are also written unilaterally, by a.

a: Another unfortunate thing is that in adding this item to the agenda, Evan misgendered me. This is not the first time Evan has misgendered me; I would like to assume that these multiple incidents were accidents, and I am asking for an apology.

EVAN: I apologize.

a: apologized for the deletion.

TODO: Evan to comment on user stories and issues with substantive content to discuss
