# Skill Instructions
  Review the supplied images and answer the configured output fields relating to smoke prevention.
  Assess only what is visible in the supplied images. Do not assume facts about areas that are not shown.

# Steps
  1. Check whether any images have been supplied.
  2. If no images have been supplied, return `null` as the `value` of every configured output field, including the comments fields.
  3. If images have been supplied, inspect them for visible outdoor smoking facilities.
  4. Inspect the images for visible non-smoking signage.
  5. Compare the visible evidence against the configured output fields.
  6. Populate each boolean field only when the visible evidence is sufficient.
  7. If the evidence is insufficient to determine a boolean field, return `null` for that field.
  8. When images have been supplied, use the corresponding comments field to briefly explain the visible evidence or why the boolean field could not be determined.

# Constraints
  - Do not infer beyond what is visible.
  - Do not assume smoking facilities exist unless they are visible.
  - Do not assume signage exists unless it is visible and relevant.
  - Do not treat a lack of evidence as `false` unless the image clearly shows the relevant area where the feature would be expected.
  - If an image is too unclear, too distant, cropped, or does not show the relevant area, return `null` for the affected boolean field.
  - If no images are supplied, return `null` for every field, including comments fields.
  - Always return all configured output fields.
  - Each output field must contain `name`, `description`, `type`, and `value`.
  - Preserve each field's configured `name`, `description`, and `type` exactly.
  - Return JSON booleans as `true` or `false`, without quotation marks.
  - Return an unknown or unavailable value as JSON `null`, without quotation marks.
  - Do not return `"yes"`, `"no"`, `"true"`, `"false"`, `"null"`, or an empty string in place of the corresponding JSON value.

# Field Guidance

## smoke-facilities
  Return `true` when the images show visible outdoor smoking facilities, such as a dedicated smoking shelter, wall-mounted ashtray, smoking bin, or clearly designated smoking area.
  Return `false` only when the images clearly show the relevant outdoor or communal area and provide sufficient visual evidence that no smoking facilities are present.
  Return `null` when the images do not show the relevant area clearly enough.

## smoke-facilities-comments
  If no images have been supplied, return `null`.
  If images have been supplied, briefly describe the visible evidence supporting the `smoke-facilities` value.
  If `smoke-facilities` is `null`, briefly explain why the supplied images are insufficient.

## smoke-signage
  Return `true` when the images show visible non-smoking signage.  
  Return `false` only when the images clearly show the relevant entrance, corridor, stairwell, or common area where signage would be expected and provide sufficient visual evidence that signage is not visible.
  Return `null` when the images do not show the relevant area clearly enough.

## smoke-signage-comments
  If no images have been supplied, return `null`.
  If images have been supplied, briefly describe the visible evidence supporting the `smoke-signage` value.
  If `smoke-signage` is `null`, briefly explain why the supplied images are insufficient.

# Output Behaviour
  Return every configured output field.
  If no images are supplied, return `null` as the `value` of all four output fields.
  If images are supplied:
  - Return `true`, `false`, or `null` for each boolean field according to the visible evidence.
  - Return a string in each comments field describing the evidence or explaining why the corresponding boolean field is `null`.

  Preserve the configured field names, descriptions, and types exactly in the response.
