# Requirement Sets

Requirement sets are used for advanced requirements to limit access to an action or a certain resource.

## Usage of Requirement Sets

- Packets
- Html Pages

## Attributes

| Attribute | Description                             |
|-----------|-----------------------------------------|
| Name      | Unique nae to identify the set          |
| Formula   | Formula, which is going to be evaluated |

## Add / Edit

Requirement Sets and Requirements can be added and edited through the designated `Requirements` page.

## Requirements

| Attribute | Description                                  |
|-----------|----------------------------------------------|
| Type      | Type of requirement                          |
| Operator  | Operator of requirement                      |
| Key       | Relation to other resources (e.g. Packet-id) |
| Value     | Desired value (permission level 42)          |

### Available Types
This list gives an overview of all available types with their respective operations

- Group member (EQ, NEQ)
- Permission level (EQ, NEQ, LEQ, GEQ, LT, GT)
- Permission level within a specific **[serverbundle](server.md)**
- Property (HAVE, NHAVE)
- Property within a specific **[serverbundle](server.md)**
- User Attribute (EQ, NEQ, LEQ, GEQ, LT, GT, HAVE, NHAVE)
- Packet (ACTIVE, INACTIVE, NEVER_ACTIVE, ONLY_ACTIVE, ONLY_INACTIVE)
- Date (EQ, NEQ, LEQ, GEQ, LT, GT)
- User-Self (NEQ, EQ)

### Formula and Example Use cases

With the formula multiple requirements can be chained together. A logical formula can be created.

Requirement Sets can be for example used for the limitation of access to custom **[HTML pages](html_pages.md)**.
This way only players who have bought a certain packet or have a certain rank (e.g. VIP) can access the page.

