# Add to CRM for AI assistants

[Add to CRM](https://addtocrm.com) finds work contact details and adds people and companies to your own CRM.
This is its [Model Context Protocol](https://modelcontextprotocol.io) server: connect it to Claude, ChatGPT,
Codex or any other MCP client and your assistant can look someone up, search for prospects, check whether a
person is already in your CRM, and add the ones you choose, without leaving the conversation. It works with
29+ CRMs. You connect your CRM once in Add to CRM; your CRM credentials stay there and the assistant never sees them.

| | |
|---|---|
| Endpoint | `https://mcp.addtocrm.com/mcp` |
| Transport | Streamable HTTP (stateless) |
| Authentication | OAuth 2.1: you sign in to your Add to CRM account when the assistant asks |
| Server name | `com.addtocrm/crm` |
| Version | 1.0.0 |
| Website | https://addtocrm.com |

This repository holds the registry entry, the Claude Code plugin and the documentation. The server runs at
Add to CRM; there is nothing to install or host. You need an Add to CRM account with a CRM connected.

## Add it to your assistant

**Claude Code**

```bash
claude mcp add --transport http addtocrm https://mcp.addtocrm.com/mcp
```

or install the plugin, which adds the connector and a skill for going from a target to records in your CRM:

```
/plugin marketplace add crm-inputs/mcp
/plugin install add-to-crm@addtocrm
```

**Claude (web and desktop)**: Settings, Connectors, Add custom connector, then paste
`https://mcp.addtocrm.com/mcp`.

**ChatGPT**: add a custom MCP server (chatgpt.com/plugins, then Add custom MCP server), paste
`https://mcp.addtocrm.com/mcp` and choose OAuth. Availability depends on your ChatGPT plan and workspace settings.

**Codex**

```bash
codex mcp add addtocrm --url https://mcp.addtocrm.com/mcp
codex mcp login addtocrm
```

Each assistant opens a sign-in window for your Add to CRM account the first time it needs one.

## Tools

| Tool | What it does |
|---|---|
| `get_account` | Shows which CRM is connected, the lookup credits left and anything that would stop a lookup or an add |
| `get_profile` | Shows the signed-in account's name and e-mail address |
| `find_contact_details` | Looks up one person by name and company, e-mail address or profile link |
| `find_company_details` | Looks up one company from its domain or public page link |
| `search_prospects` | Searches for people by title, seniority, location and company details |
| `search_companies` | Searches for companies by name, keywords, location, headcount or domain |
| `find_person_in_crm` | Checks whether a person is already in your CRM, without enriching them |
| `search_crm` | Searches the people and companies in your CRM |
| `get_crm_record` | Reads one CRM record in full |
| `add_person_to_crm` | Adds one person to your CRM, with your field mapping, tags and duplicate checks |
| `add_company_to_crm` | Adds one company to your CRM |
| `add_people_to_crm` | Adds up to 100 people from a search to your CRM in one job |
| `get_bulk_add_status` | Reports how a bulk add is going |
| `confirm_possible_match` | Records that a possible match in your CRM is, or is not, the same person |
| `log_crm_activity` | Logs a note, call, meeting or task on a CRM record |
| `update_crm_record` | Changes a person's or company's details on a CRM record that was read first |
| `list_lists` | Lists your saved lists |
| `save_to_list` | Saves people to a list |

Tools that change your CRM are marked as writes, so your assistant can ask you before it runs them. Nothing
here sends e-mail or messages, contacts anyone, or deletes CRM data.

## Your data

What the server returns, how it is used and how to disconnect are in the
[Privacy policy](https://addtocrm.com/privacy) and the [Terms](https://addtocrm.com/terms). You can disconnect an
assistant at any time under Connected AI apps in your Add to CRM account.

Support: https://addtocrm.com/contact

## Licence

The contents of this repository are MIT licensed, see [LICENSE](LICENSE). That licence covers this repository
only, not the service or its data: see [NOTICE](NOTICE).
