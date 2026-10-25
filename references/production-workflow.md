# Production workflow

Use this checklist for a Xiangsu portrait effect. Adapt the order to the project; do not introduce optional face or makeup effects if the user only requested a frame.

## Before editing

- Read the active project path, saved/dirty state, scene tree, relevant component properties, asset list, and current preview.
- Locate the exact Image component and current texture GUID for an overlay. Record the accepted starting version so a rollback can target the right change.
- If reviewing a prior project/archive, extract only design decisions, reusable source, technical settings, and rights information relevant to the new brief.
- Make a short visual plan: focal area, frame bounds, title and decorative zones, palette, desired contrast, animation or tracking needs, and optional filter/makeup treatment.

## Create and integrate assets

- Create original decorative art with a reproducible source where possible. Keep the face/camera area transparent for frame overlays.
- For third-party assets, check the official license and whether commercial use, redistribution, and modification are allowed. Preserve attribution or notices if required. Do not use unclear or fan-made assets as though they were official.
- Import the image through the editor's supported asset-import path. Capture the returned GUID, then bind it to the existing component using the field discovered by inspecting that component (`texture`, `mainTexture`, or another supported field).
- Preserve or intentionally set texture resolution and filtering to suit the output. Confirm the imported resource's properties if the result looks softer than the source.
- Add optional filter/makeup components using editor-supported built-ins and documented settings. Keep the visual treatment consistent with the brief and compare it in the live preview.

## Iterate and handle rollback

- Refresh preview after each meaningful visual update. Inspect the whole screen and the face area, not just a cropped source image.
- On revision requests, change only the requested layer where possible. If the user asks to return to a prior version, remove scene-level changes and any baked-in image changes, restore/reimport the accepted source, and rebind it.
- If a disk-level asset replacement is not reflected in the preview, assume the editor may hold an imported cache. Import the updated image as an editor resource, bind the new GUID, and refresh again. Do not claim rollback success from the local PNG alone.
- Check that frame corners do not cover facial landmarks, that text remains legible, and that border accents are visible on both pale and dark clothing/backgrounds.

## Save and handoff

- Save to the existing project path unless a new path was requested.
- Confirm the editor's save result and final project status (`is_saved`, `is_changed`, `scene_dirty`).
- Retain the editable source and exported images needed to continue the work. Keep the project asset list tidy; remove a superseded duplicate only after confirming it has no references.
- Share a fresh live preview and concise summary of what changed, what assets were used, and where the project was saved. Mention third-party attribution when required.
