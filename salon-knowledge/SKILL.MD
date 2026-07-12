# Skill Instructions

  Use the supplied `query` to search the configured Salon Tracker Support Knowledge Base MCP server.

  Use only information returned by the MCP server. Do not answer from general knowledge, assumptions, prior knowledge, or external sources.

  # Behaviour

  - If `query` is missing, empty, or meaningless, return `{ "results": [] }`.
  - Search the configured MCP server using the meaning of the supplied query.
  - Return only relevant information found through the MCP server.
  - Do not invent, infer, correct, or supplement missing information.
  - If the MCP server returns no relevant answer, return `{ "results": [] }`.
  - Return JSON only, with no Markdown fencing or commentary.

  # Result Mapping

  Return exactly one JSON object matching the configured output schema.

  The object must contain `results`.

  Each item in `results` must contain:

  - `name`
  - `description`
  - `artifactName`
  - `artifactUrl`

  Rules:

  - `name` must be a short string describing the result.
  - `description` must be the useful answer or information returned by the MCP server.
  - `artifactName` must be a string only when the MCP result provides an artifact name; otherwise `null`.
  - `artifactUrl` must be a string only when the MCP result provides an artifact URL; otherwise `null`.
  - Do not invent artifact names or URLs.
  - Use `null`, not an empty string, for unavailable artifact values.
  - Return multiple results only when the MCP server provides multiple distinct relevant answers.
  - Do not duplicate the same answer.
