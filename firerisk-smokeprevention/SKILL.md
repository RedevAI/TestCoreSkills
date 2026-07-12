 # Skill Instructions

  Review the supplied images and answer the configured smoke prevention fields.

  Assess only what is visibly identifiable in the supplied images. Do not assume facts about areas or features that are not shown clearly.

  # Steps

  1. Check whether any images have been supplied.
  2. If no images have been supplied, return every configured field with `value` set to `null`.
  3. If images have been supplied, inspect them for visible outdoor smoking facilities.
  4. Inspect them for visible non-smoking signage.
  5. Populate each configured boolean field only when visible evidence is sufficient.
  6. If evidence is insufficient for a boolean field, set its `value` to `null`.
  7. Populate a comments field only when its corresponding boolean field is `true`.
  8. If a boolean field is `false` or `null`, set its corresponding comments field to `null`.

  # Constraints

  - Do not infer beyond what is visible.
  - Do not assume smoking facilities exist unless they are clearly visible.
  - Do not assume signage exists unless it is clearly visible and relevant.
  - Do not treat lack of evidence as `false` unless the image clearly shows the relevant area where the feature would be expected.
  - If an image is unclear, distant, cropped, or does not show the relevant area, return `null` for the affected field.
  - Comments must contain positive visible evidence only.
  - Do not use comments to explain uncertainty, missing evidence, unclear images, or why a question cannot be answered.
  - Return JSON only, with no Markdown fencing or commentary.
  - Return JSON booleans as `true` or `false`.
  - Return unknown or unavailable values as JSON `null`.
  - Do not return `"yes"`, `"no"`, `"true"`, `"false"`, `"null"`, or empty strings.

  # Output Behaviour

  Return exactly one JSON object matching the configured output schema.

  Use the configured output fields as the source of truth. Preserve each field's configured `name` and `description`; only populate the `value`.

  Do not add fields that are not defined in the output schema.

  # Field Guidance

  ## Smoking facilities

  Return `true` when images clearly show outdoor smoking facilities, such as a dedicated smoking shelter, wall-mounted ashtray, smoking bin, or clearly designated smoking area.

  Return `false` only when the images clearly show the relevant outdoor or communal area and provide sufficient evidence that no smoking facilities are present.

  Return `null` when the relevant area is not shown clearly enough.

  ## Non-smoking signage

  Return `true` when images clearly show visible non-smoking signage.

  Return `false` only when the images clearly show a relevant entrance, corridor, stairwell, or common area where signage would be expected and provide sufficient evidence that signage is not visible.

  Return `null` when the relevant area is not shown clearly enough.
