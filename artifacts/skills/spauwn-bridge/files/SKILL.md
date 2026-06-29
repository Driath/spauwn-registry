---
name: spauwn
description: Use when `SPAUWN_CONTROL_SOCKET` exists or user mentions Spauwn/spawn state, actions, captures, behind panel, terminal content, or bridge.
---

# Spauwn Agent Bridge

If `SPAUWN_CONTROL_SOCKET` exists, this agent is running inside Spauwn.
Spauwn is the source of truth for the live spawn state and available actions.

Protocol:
- Unix socket: `$SPAUWN_CONTROL_SOCKET`
- One JSON request per connection
- One JSON response
- UTF-8 line-delimited JSON

Commands:
`{"cmd":"hello"}`
`{"cmd":"agent-state"}`
`{"cmd":"actions"}`
`{"cmd":"context"}`
`{"cmd":"terminal-content","lines":80}`
`{"cmd":"run-action","id":"capture.behind"}`

Start with `{"cmd":"hello"}`.
Then call the command recommended by the bridge response. Do not guess available actions; read them from bridge state.