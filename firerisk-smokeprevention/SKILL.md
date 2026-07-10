# Skill Instructions

  Review the supplied images and answer the configured output fields relating to smoke prevention.

  Assess only what is visibly identifiable in the supplied images. Do not assume facts about areas or features that are not shown clearly.

  # Steps

  1. Check whether any images have been supplied.
  2. If no images have been supplied, return `null` as the `value` of every configured output field, including the comments fields.
  3. If images have been supplied, inspect them for visible outdoor smoking facilities.
  4. Inspect the images for visible non-smoking signage.
  5. Compare only the visible evidence against the configured output fields.
  6. Populate a boolean field only when the visible evidence is sufficient.
  7. If the evidence is insufficient to determine a boolean field, return `null` for that field.
  8. Populate a comments field only when its corresponding boolean field is `true`.
  9. If a boolean field is `false` or `null`, return `null` for its corresponding comments field.

  # Constraints

  - Do not infer beyond what is visible.
  - Do not assume smoking facilities exist unless they are clearly visible.
  - Do not assume signage exists unless it is clearly visible and relevant.
  - Do not treat a lack of evidence as `false` unless the image clearly shows the relevant area where the feature would be expected.
  - If an image is too unclear, too distant, cropped, or does not show the relevant area, return `null` for the affected boolean field.
  - Comments fields must contain positive visible evidence only.
  - Do not use comments fields to explain uncertainty, missing evidence, unclear images, or why a question cannot be answered.
  - If a boolean field is `false` or `null`, its corresponding comments field must be `null`.
  - If no images are supplied, return `null` for every field, including comments fields.
  - Always return all configured output fields.
  - Each output field must contain `name`, `description`, `type`, and `value`.
  - Preserve each field's configured `name`, `description`, and `type` exactly.
  - Return JSON booleans as `true` or `false`, without quotation marks.
  - Return an unknown or unavailable value as JSON `null`, without quotation marks.
  - Do not return `"yes"`, `"no"`, `"true"`, `"false"`, `"null"`, or an empty string in place of the corresponding JSON value.

  # Field Guidance

  ## smoke-facilities

  Return `true` when the images clearly show visible outdoor smoking facilities, such as:

  - A dedicated smoking shelter.
  - A wall-mounted ashtray.
  - A smoking bin.
  - A clearly designated smoking area.

  Return `false` only when the images clearly show the relevant outdoor or communal area and provide sufficient visual evidence that no smoking facilities are present.

  Return `null` when:

  - No images have been supplied.
  - The relevant area is not shown.
  - The image is unclear, distant, or cropped.
  - The visible evidence is otherwise insufficient.

  ## smoke-facilities-comments

  Return a brief string describing the positively identified smoking facility only when `smoke-facilities` is `true`.

  For example, describe the visible smoking shelter, ashtray, smoking bin, or designated smoking area.

  Return `null` when `smoke-facilities` is `false` or `null`.

  Do not explain why a smoking facility could not be identified.

  ## smoke-signage

  Return `true` when the images clearly show visible non-smoking signage.

  Return `false` only when the images clearly show a relevant entrance, corridor, stairwell, or common area where signage would be expected and provide sufficient visual evidence that non-smoking signage is not visible.

  Return `null` when:

  - No images have been supplied.
  - The relevant area is not shown.
  - The image is unclear, distant, or cropped.
  - The visible evidence is otherwise insufficient.

  ## smoke-signage-comments

  Return a brief string describing the positively identified non-smoking signage only when `smoke-signage` is `true`.

  Return `null` when `smoke-signage` is `false` or `null`.

  Do not explain why non-smoking signage could not be identified.

  # Output Behaviour

  Return every configured output field.

  If no images are supplied, return `null` as the `value` of all four output fields.

  If images are supplied:

  - Return `true`, `false`, or `null` for each boolean field according to the visible evidence.
  - Return a string in a comments field only when its corresponding boolean field is `true`.
  - Return `null` in a comments field when its corresponding boolean field is `false` or `null`.

  Preserve the configured field names, descriptions, and types exactly in the response.
