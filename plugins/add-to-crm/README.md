# Add to CRM for Claude Code

Find work contact details and add people and companies to your own CRM from the conversation.

This plugin connects Claude Code to the Add to CRM connector at `https://mcp.addtocrm.com/mcp` and adds one skill,
`prospect-to-crm`, for going from "who should I talk to?" to records in your CRM.

**Install** (Claude Code 2.1.275 or later):

```
/plugin marketplace add crm-inputs/mcp
/plugin install add-to-crm@addtocrm
```

Then connect your Add to CRM account when Claude asks. You sign in to Add to CRM once; your CRM credentials stay
with Add to CRM and Claude never sees them.

**Needs:** an Add to CRM account with a CRM connected (set up at https://addtocrm.com).

**Control:** tools that change your CRM are marked as writes, so Claude can ask you before it runs them. Disconnect
any time under Connected AI apps in your Add to CRM account.

Support: https://addtocrm.com/contact · Privacy: https://addtocrm.com/privacy · Terms: https://addtocrm.com/terms · Licence: MIT
