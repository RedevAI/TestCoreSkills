# Instructions

Review the supplied images and answer the configured output fields relating to smoke prevention.

Assess only what is visible in the supplied images. Do not assume facts about areas that are not shown.

# Steps

1. Check whether any images have been supplied.
2. If no images have been supplied, return all configured output fields with empty values.
3. If images have been supplied, inspect the images for visible outdoor smoking facilities.
4. Inspect the images for visible non-smoking signage.
5. Compare the visible evidence against the configured output fields.
6. For each field, return a value only when the image evidence is sufficient.
7. If images are supplied but the evidence is not sufficient to answer a field, return that field with an empty value.
8. Use the comments fields to briefly explain the visible evidence or why the question cannot be answered from the images.

# Constraints

- Do not infer beyond what is visible.
- Do not assume smoking facilities exist unless they are visible.
- Do not assume signage exists unless it is visible and relevant.
- Do not treat a lack of evidence as a definite "no" unless the image clearly shows the relevant area where the feature would be expected.
- If the image is too unclear, too distant, cropped, or does not show the relevant area, return an empty value for the affected field.
- Always return all configured output fields.
- Each output field must contain `name`, `description`, `type` and `value`.

# Field Guidance

## smoke-facilities

Return `yes` when images show visible outdoor smoking facilities, such as a dedicated smoking shelter, wall-mounted ashtray, smoking bin, or clearly designated smoking area.

Return `no` only when the images clearly show the relevant outdoor or communal area and there is sufficient visual evidence that no smoking facilities are provided.

Return an empty value when the images do not show the relevant area clearly enough.

## smoke-facilities-comments

Briefly describe the visible evidence for the smoking facilities answer.

If the answer cannot be confirmed, briefly explain why the images are insufficient.

## smoke-signage

Return `yes` when images show visible non-smoking signage.

Return `no` only when the images clearly show the relevant entrance, corridor, stairwell, or common area where signage would be expected and there is sufficient visual evidence that signage is not visible.

Return an empty value when the images do not show the relevant area clearly enough.

## smoke-signage-comments

Briefly describe the visible evidence for the signage answer.

If the answer cannot be confirmed, briefly explain why the images are insufficient.

# Output Behaviour

Return the configured output fields with `value` populated where the image evidence is sufficient.

If no images are supplied, return all output fields with empty values.

If images are supplied but a specific field cannot be answered safely from the visible evidence, return that field with an empty value.
