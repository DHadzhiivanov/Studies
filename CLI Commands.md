# Switch Configuration
---

## VLANs

### Creation & Deletion

**create VLAN**
`create vlan <NAME> {tag <ID>} {description <"description">}`

**delete VLAN**
`delete vlan <NAME>`

**modify tag**
`configure vlan <NAME> tag <ID>`

### Port Assignment

**add untagged (access)** (Auto removes the port from 'Default' VLAN)
`configure vlan <NAME> add ports <PORT_LIST> untagged`

**Add Tagged (Trunk)**
`configure vlan <NAME> add ports <PORT_LIST> tagged`

**Remove Port**:
`configure vlan <NAME> delete ports <PORT_LIST>`

### Monitoring & Verification

**show port and vlan allocation & tags**
`show ports vlan`

**view config**
`show configuration vlan`

---

##