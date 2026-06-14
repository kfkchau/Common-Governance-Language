````md
# 00 Master Database Principle

## Core Principle

The master database is the source of truth.

Everything in CGL is information.

Profiles, authority, capability, version, and status are not primitive truth. They are views generated from the master database by scanning records under rules.

## Master Database Rule

```text
Master database exists.

Everything is information.

Every object is information.

Every rule is information.

Every activity is information.

Every message is information.

Every relationship is information.

Every field is information.

Every profile is a view over information records.

Every authority claim is a view over information records.

Every capability claim is a view over information records.

Every version is a view over event history.

Every deletion is removal from an active view unless a special master-destruction protocol exists.
````

## Why This Matters

CGL should not store a profile as the final truth.

Example:

```text
Admin profile is not the root truth.

Admin profile is generated from:
  record: create Admin actor
  record: create Admin tunnel
  record: link Admin to tunnel
  record: give Admin instruction authority
  record: add Admin signature/proof method
```

The profile is only the current combined view.

## Deletion Principle

Normal delete should mean:

```text
Create a new activity record saying the object is removed from the active view.
```

It should not mean:

```text
Erase the master record.
```

Example:

```text
ACT-100:
  actor: SYSTEM
  action: REMOVE-FROM-VIEW
  object: RULE-123
  target: CURRENT-ACTIVE-RULE-SET
```

The rule no longer appears in the active rule view, but the historical master record remains.

## Version Principle

Version is also a view.

```text
Version at time T = database state generated from all relevant records up to time T.
```

So version can be derived from event/activity history.

No object needs to carry a magic version field as primitive truth if the event chain is reliable.

---

# 01 Foundational Import Pack

## Purpose

The foundational import pack is the first CGL package loaded by the PC/runtime before the CGL software system can govern itself.

It contains the minimum activity/rule templates required to create the CGL system, create Admin, create the message tunnel, create root rules, and hand off control to the software system.

## Pack Contents

The foundational pack should contain at least:

```text
READ
FOLLOW
CREATE-INFO
CREATE-ACTIVITY
CREATE-RELATIONSHIP
CREATE-RULE
CREATE-ACTOR
CREATE-TUNNEL
WRITE-ACTIVITY
CHECK-RULE
CHECK-CONTRADICTION
BLOCK
```

These are not normal programming functions.

They are foundational CGL rule/activity templates.

## READ

```text
READ:
  Actor: SYSTEM
  Action: move information into system understanding
  Object: information resource
  Target: system active context
```

READ is information movement.

It moves information into cognitive/digital/system understanding.

## FOLLOW

```text
FOLLOW:
  Actor: SYSTEM
  Action: apply rule
  Object: rule information
  Target: created activity, created conclusion, or created record
```

FOLLOW means the system applies a rule object.

## CREATE-INFO

```text
CREATE-INFO:
  Actor: SYSTEM
  Action: create information resource
  Object: provided content
  Target: master database
```

CREATE-INFO creates an information object in the master database.

## CREATE-ACTIVITY

```text
CREATE-ACTIVITY:
  Actor: SYSTEM
  Action: create activity information
  Object: Actor/Action/Object/Target structure
  Target: master database
```

CREATE-ACTIVITY creates an activity record.

## CREATE-RELATIONSHIP

```text
CREATE-RELATIONSHIP:
  Actor: SYSTEM
  Action: create relationship information
  Object: source relation target
  Target: relationship database / master database
```

Relationships are records, not invisible assumptions.

## CREATE-RULE

```text
CREATE-RULE:
  Actor: SYSTEM
  Action: create rule information
  Object: rule content
  Target: rule information records
```

Rule creation must itself be recorded as a system activity.

## CREATE-ACTOR

```text
CREATE-ACTOR:
  Actor: SYSTEM or PC/runtime during boot
  Action: create actor information
  Object: actor ID / actor info
  Target: master database
```

Actor profile is later generated as a view from database records.

## CREATE-TUNNEL

```text
CREATE-TUNNEL:
  Actor: SYSTEM or PC/runtime during boot
  Action: create communication tunnel information
  Object: tunnel record
  Target: master database
```

A tunnel is the information path through which messages can validly move.

## WRITE-ACTIVITY

```text
WRITE-ACTIVITY:
  Actor: SYSTEM
  Action: write activity event
  Object: activity information
  Target: master database
```

SYSTEM must be able to record activity broadly.

This is not permission for all actors to perform all activities.

It is permission for SYSTEM to record evidence of activities.

## CHECK-CONTRADICTION

```text
CHECK-CONTRADICTION:
  Actor: SYSTEM
  Action: compare proposed rule/change against active rule set
  Object: proposed rule/change
  Target: contradiction conclusion
```

This prevents activation of self-destroying or contradictory rule sets.

## BLOCK

```text
BLOCK:
  Actor: SYSTEM
  Action: prevent activity path
  Object: proposed activity
  Target: blocked state / rejection event
```

BLOCK creates evidence that a path was refused.

---

# 02 Boot Actor Setup

## Purpose

This document defines the boot actors and the handoff from the PC/runtime to the CGL software system.

## Boot Actors

There are three relevant actors at boot:

```text
PC_RUNTIME
SYSTEM
ADMIN
```

## PC_RUNTIME

PC_RUNTIME is the external setup actor.

It imports the foundational CGL pack and creates the first CGL objects.

PC_RUNTIME is not the long-term governance actor.

Its job is:

```text
import foundational pack
create master database
create SYSTEM object
create ADMIN object
create ADMIN-to-SYSTEM tunnel
create root rules
handoff control to SYSTEM
```

## SYSTEM

SYSTEM is the CGL software execution/governance actor.

SYSTEM:

```text
reads information
follows rules
creates information
creates activity records
creates relationships
creates rules
checks contradictions
blocks invalid activity
generates views over the master database
```

SYSTEM is the only actor that should write governed database state after boot.

Other actors send messages/instructions.

## ADMIN

ADMIN is the root instruction-authority actor.

ADMIN does not directly mutate the database.

ADMIN sends information to SYSTEM through an authorised tunnel.

SYSTEM reads the message, verifies rules, follows instruction, and creates records.

## Boot Handoff

The handoff is:

```text
PC_RUNTIME creates the boot system.
PC_RUNTIME creates SYSTEM.
PC_RUNTIME creates ADMIN.
PC_RUNTIME creates tunnel and root rules.
PC_RUNTIME hands control to SYSTEM.
SYSTEM opens ADMIN tunnel.
ADMIN can now build baseline layer by sending messages.
```

---

# 03 Message Tunnel Model

## Purpose

The message tunnel model defines how Admin or other actors send instruction-information to System.

## Message Is Information

A message is an information resource.

Its action is always information movement, so the message does not need a separate action field.

## Minimal Message Schema

```text
message_id
sender_actor_id
tunnel_id
object_id
target_id
timestamp
signature
```

## Field Meaning

```text
message_id:
  unique ID of message information

sender_actor_id:
  actor who sent the message

tunnel_id:
  communication tunnel used

object_id:
  information object/content being sent

target_id:
  target actor/system/context

timestamp:
  time of message creation or receipt

signature:
  proof that message came from sender
```

## What Message Does Not Need

Message does not need:

```text
action
authority
status
linked event
parent message
```

Reason:

```text
action = always move information

authority = derived by checking rules/relationships/events

status = derived from event records

linked event = relationship record

parent message = relationship record
```

## Message Relationships

Parent/reply/supersede/contradict should be stored as relationship records.

Examples:

```text
MSG-002 replies-to MSG-001
MSG-003 supersedes MSG-001
MSG-004 contradicts MSG-002
MSG-005 caused ACT-010
```

## Tunnel

A tunnel is an information path.

A valid tunnel links:

```text
sender actor
target actor
permitted message class
proof/signature method
root authorisation rule
```

Example:

```text
ADMIN_TUNNEL:
  sender: ADMIN
  target: SYSTEM
  permitted object: instruction information
  proof: admin signature
```

---

# 04 Activity Record Model

## Purpose

The activity record model defines how CGL records what happens.

## Core Activity Structure

CGL activity is based on four elements:

```text
Actor
Action
Object
Target
```

## Minimal Activity Schema

```text
activity_id
actor_id
action_id
object_id
target_id
timestamp
source_message_id
```

## Field Meaning

```text
activity_id:
  unique activity record ID

actor_id:
  actor that performed the activity

action_id:
  action performed

object_id:
  object/resource/information acted on

target_id:
  target/result/context of the activity

timestamp:
  time of activity record

source_message_id:
  message that caused the activity, if any
```

## Relationship Records Around Activity

Do not overload the activity row.

Use relationship records for:

```text
activity checked rule
activity produced information
activity modified information
activity caused another activity
activity blocked another activity
activity created relationship
activity created rule
activity read message
activity followed rule
```

Examples:

```text
ACT-001 checked-rule RULE-ADMIN-TUNNEL
ACT-001 produced CONCLUSION-MSG-AUTHORISED
ACT-001 caused ACT-002
ACT-002 created INFO-ROLE-FINANCE-MANAGER
```

## EVT

EVT is happened-information.

An activity record is the basis of EVT.

EVT answers:

```text
what happened
who acted
what action happened
what object was acted on
what target was affected
what message caused it
what records were created
```

---

# 05 Rule as Information Model

## Purpose

This document defines rules as information objects in the master database.

## Rule Is Information

A rule is an information object.

It should not be treated as hidden code.

A rule can be:

```text
created
read
followed
grouped
activated
removed from active view
contradicted
superseded
reported
```

## Rule Object

A rule object should minimally include:

```text
rule_info_id
rule_content_object_id
```

Other properties are derived through relationships and events.

## Rule Tags

A rule may be tagged as:

```text
positive
negative
requirement
permission
block
integrity
translation
calculation
view
```

Tags are also information/relationship records.

## Positive Rule

Positive rule example:

```text
(+)
ADMIN may send information to SYSTEM through ADMIN_TUNNEL.
```

## Negative Rule

Negative rule example:

```text
(-)
No valid ADMIN message -> SYSTEM must not create requested governance information.
```

## Rule Activation

A rule being created is not the same as a rule being active.

Active rule set is a view over records.

Example:

```text
Rule created in EVT-010.
Rule activated in EVT-011.
Rule removed from active view in EVT-100.
```

## Rule Removal

Rule removal should usually mean:

```text
remove rule from active view
```

not:

```text
erase rule from master database
```

## Rule Groups

Rules can be grouped into packs:

```text
rule pack
policy pack
baseline pack
math pack
logic pack
domain pack
```

A pack is a grouped information object.

---

# 06 REQ / EVT / CAP Model

## Purpose

This document defines the three root CGL information classifications.

```text
REQ
EVT
CAP
```

## REQ

REQ is rule/requirement information.

REQ is not merely "must/may/should/must not."

REQ is a rule object, and enforcement strength can be assessed by an effort-to-outcome module.

## REQ and Effort/Outcome

Effort/outcome does not define REQ itself.

It measures enforcement intensity.

Example:

```text
REQ:
  Customer provides passport copy.

Effort:
  high

Outcome:
  fraud risk reduction

Effort/outcome assessment:
  strong enforcement only if transaction risk is high
```

So:

```text
REQ = rule/requirement information

Effort/outcome module =
  decides how much enforcement the REQ deserves
```

## EVT

EVT is happened-information.

It records activities.

Examples:

```text
ADMIN sent message.
SYSTEM read message.
SYSTEM verified message.
SYSTEM created rule.
SYSTEM blocked invalid instruction.
SYSTEM removed rule from active view.
```

## CAP

CAP is capability reporting over the database.

CAP is not primitive authority.

CAP is a view/reporting function over activity-format database records.

Examples:

```text
Five purchase events of 10 cars each
-> CAP report: organisation has recorded car-buying activity totalling 50 cars.

Records show role can approve refunds under active rule set
-> CAP report: role has refund approval capability under condition X.

Records show system has tunnel to Admin
-> CAP report: Admin communication capability exists.
```

CAP can report:

```text
actor capability
resource capability
role capability
organisation capability
system capability
workflow capability
capacity from event history
capacity from active rules
capacity from available resources
```

---

# 07 Authorisation by Rule Chain

## Purpose

Authority should not be a magic field.

Authority should be inferred from the master database by scanning rules, relationships, messages, and events.

## Core Principle

```text
Authority = CAP/view over rule records + relationship records + event records.
```

A message does not contain authority.

A rule chain establishes whether a message or activity is authorised.

## Positive Chain

Example:

```text
(+)
ADMIN sends information through ADMIN_TUNNEL
-> SYSTEM may read message

(+)
SYSTEM reads valid ADMIN message
-> SYSTEM may create requested information

(+)
SYSTEM creates requested information
-> SYSTEM records activity
```

## Negative Chain

Example:

```text
(-)
No ADMIN message
-> SYSTEM must not create requested governance information

(-)
Message not through ADMIN_TUNNEL
-> SYSTEM must not create requested governance information

(-)
Sender not ADMIN or authorised actor
-> SYSTEM must not create requested governance information

(-)
No authority check
-> no state-changing activity

(-)
No event record
-> no valid state-changing activity
```

## Authorisation Relationship

Authorisation is established by the chain:

```text
sender
message
tunnel
target
rule
system read
system check
system follow
system create
system record
```

## No Authority Field Required

Do not add:

```text
message.authority
actor.authority_level
```

as primitive truth.

Those are views from records.

## Actor Authority

Actor authority is derived from records such as:

```text
actor exists
actor linked to role
role linked to permission rule
permission rule active
permission rule created by authorised system activity
condition satisfied
```

---

# 08 Boot Integrity and Contradiction

## Purpose

The foundational layer must prevent CGL from destroying the minimum conditions needed for CGL to function.

## Integrity Principle

SYSTEM must not activate a rule set that destroys boot conditions.

## Minimum Boot Conditions

```text
SYSTEM actor exists.
ADMIN actor or valid successor authority exists.
ADMIN-to-SYSTEM or valid instruction tunnel exists.
Message authority checking exists.
Event/activity recording exists.
Master database persists.
Contradiction checking exists.
Rule activation/removal is recorded.
```

## Contradictory or Dangerous Instructions

SYSTEM should reject or quarantine instructions that produce:

```text
Admin removes own authority without valid successor.
Admin creates circular authority with no root source.
Admin disables event recording.
Admin disables authority checking.
Admin creates rule allowing unauthorised messages to be followed.
Admin creates infinite authority loop.
Admin creates active rule contradiction in same scope.
Admin creates rule set that prevents SYSTEM from recording activities.
Admin creates rule set that erases the master database.
```

## Delete Principle

Deleting from a current view is allowed if governed.

Erasing master records should be impossible or require special destruction/recovery protocol.

## Contradiction Record

Rejected or quarantined instructions should still create event records.

Example:

```text
EVT:
  SYSTEM rejected MSG-200
  reason: proposed rule disables event recording
```

## Admin Constraint

ADMIN is root operational authority, but foundational integrity constraints preserve CGL’s ability to function.

This is not disobedience to Admin.

It is the system enforcing the boot conditions that make Admin instruction meaningful.

---

# 09 Boot Sequence

## Purpose

This document defines the exact boot order for CGL as software/database/governance system.

## Boot Sequence

```text
1. PC/runtime imports FOUNDATIONAL_CGL_PACK.

2. PC/runtime creates master database.

3. PC/runtime creates SYSTEM object.

4. PC/runtime creates ADMIN object.

5. PC/runtime creates ADMIN communication tunnel.

6. PC/runtime adds relationship:
   ADMIN -> may send info through -> ADMIN_TUNNEL

7. PC/runtime adds relationship:
   ADMIN_TUNNEL -> targets -> SYSTEM

8. PC/runtime creates root positive rules:
   (+) ADMIN may send information to SYSTEM through ADMIN_TUNNEL.
   (+) SYSTEM may read information from ADMIN_TUNNEL.
   (+) SYSTEM follows valid ADMIN message.
   (+) SYSTEM may create information records.
   (+) SYSTEM may create activity records.
   (+) SYSTEM may create relationship records.
   (+) SYSTEM may create rule information.

9. PC/runtime creates root negative rules:
   (-) no valid admin message -> no system-created governance info.
   (-) invalid tunnel -> no system-created governance info.
   (-) unauthorised sender -> no system-created governance info.
   (-) no authority check -> no state-changing activity.
   (-) no event record -> no valid state-changing activity.
   (-) no contradiction check -> no activation of new rule.

10. PC/runtime creates master activity-writing rule:
    SYSTEM may write activity record where:
      actor = any
      action = any
      object = any
      target = any

    This means SYSTEM may record any activity as evidence.
    It does not mean any actor may perform any activity.

11. PC/runtime creates contradiction/integrity rule:
    SYSTEM rejects active rule set that destroys boot conditions.

12. PC/runtime hands off control to CGL software system.

13. CGL SYSTEM opens ADMIN tunnel.

14. ADMIN sends first baseline-building message through ADMIN_TUNNEL.

15. SYSTEM reads message.

16. SYSTEM verifies sender, tunnel, signature, target, and rule chain.

17. SYSTEM follows valid message.

18. SYSTEM creates baseline layer records as instructed.

19. SYSTEM records all activities as EVT.

20. SYSTEM updates CAP/reporting views where relevant.
```

## Boot Result

After boot, CGL has:

```text
master database
SYSTEM actor
ADMIN actor
message tunnel
root positive rules
root negative rules
activity recording
rule creation ability
relationship creation ability
contradiction checking
event preservation
admin handoff channel
```

At this point the foundational layer is active, and Admin can build the baseline layer by sending authorised messages.

---

# 10 Baseline Layer Boundary

## Purpose

The baseline layer is not the foundation.

The baseline layer is the first useful toolkit built after foundation is active.

## Baseline Includes

```text
basic logic rules
basic math rules
object creation tools
field creation tools
index/group tools
role creation tools
rule creation tools
permission rules
view/report generation rules
import/export rules
code translation primitives
```

## Baseline Does Not Need To Exist Before Boot

The foundation only needs enough to:

```text
receive admin instruction
verify authority
create information
create activity
create rule
create relationship
record events
protect boot integrity
```

Everything else can be built by Admin through System.

## Baseline Build Example

Admin sends:

```text
Build baseline math pack.
```

SYSTEM:

```text
reads message
verifies authority
creates math rule objects
creates math pack group
records events
updates views
```

---

# 11 Advanced Layer Boundary

## Purpose

The advanced layer contains domain/universal activity packs.

It should not be built from business buzzwords.

It should be built from universal activity/resource patterns.

## Bad Advanced Labels

Do not start with:

```text
supply chain
global procurement
finance operations
HR
customer success
```

These are labels, not primitives.

## Better Universal Packs

Use patterns such as:

```text
movement of money across border
movement of goods between custodians
movement of information between actors
movement of authority
movement of ownership
movement of obligation
creation of agreement
fulfilment of agreement
failure of agreement
identity verification
eligibility determination
risk acceptance
dispute handling
regulated approval
record retention
```

## Example: Cross-Border Money Movement

Required objects:

```text
payer
payee
payer jurisdiction
payee jurisdiction
currency sent
currency received
amount
exchange rate
bank account
payment rail
legal jurisdiction
tax rule
sanction rule
identity verification rule
approval authority
record requirement
failure path
```

Required rule packs:

```text
identity rule pack
currency rule pack
exchange rate rule pack
tax rule pack
sanctions rule pack
approval rule pack
banking rail rule pack
recordkeeping rule pack
exception/failure rule pack
notification rule pack
```

Specific country/org rules then plug in as overlays.

---

# 12 Final Corrected Foundation

## One-Block Definition

```text
CGL foundational layer is a boot governance system where:

The master database is the source of truth.

Everything is information.

PC/runtime imports the foundational CGL pack.

PC/runtime creates SYSTEM.

PC/runtime creates ADMIN.

PC/runtime creates an ADMIN-to-SYSTEM message tunnel.

PC/runtime creates positive and negative root rules that authorise:
  ADMIN sends information to SYSTEM.
  SYSTEM reads authorised Admin information.
  SYSTEM follows valid Admin message.
  SYSTEM creates information/activity/relationship/rule records.

PC/runtime creates root record rule:
  SYSTEM can record activity broadly.

PC/runtime creates root integrity rule:
  SYSTEM cannot activate contradictory or self-destroying rule sets.

PC/runtime hands off to CGL software SYSTEM.

ADMIN builds the baseline layer by sending messages through the tunnel.

SYSTEM reads, checks, follows, creates records, and updates views.

Profiles, authority, capability, status, and version are not primitive truth.
They are generated views over the master database.

REQ is rule/requirement information.

Effort/outcome logic measures enforcement strength for REQ.

EVT is happened activity information.

CAP is reporting/view information over the database.
```

## Critical Design Sentence

```text
CGL does not begin with functions.
CGL begins with authorised information movement into SYSTEM and recorded SYSTEM activity over a master database.
```

```

Download: [cgl_foundational_boot_design.md](sandbox:/mnt/data/cgl_foundational_boot_design.md)
```
