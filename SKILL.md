---
name: xiangsu-effect-creation
description: Create, revise, preview, and save portrait AR camera effects in Xiangsu (像塑), including frame overlays, filters, makeup, and other visual assets. Use when working on a Xiangsu effect project; not for general image editing or effects for other platforms.
---

# Xiangsu Effect Creation

Create the effect the user described in the currently open Xiangsu project when they ask to work in it. Keep the main camera view usable, follow the requested tone, and finish with a refreshed preview and a saved project.

## Workflow

1. **Understand the project and brief.** Check the active project, scene, assets, and preview before editing. Keep working in the user's open project when requested. If the user provides an archive or prior AI attempt, inspect it for reusable requirements, dimensions, assets, or decisions; skip it when it adds no value.
2. **Plan the visual hierarchy.** For portrait frames, keep the face and central camera area clear. Make decorative elements readable against both light and dark footage. Add backing panels only where they help contrast and fit the brief. Treat undo requests as a return to the last accepted visual state; identify every layer of the change, including anything baked into the source image.
3. **Use rights-safe assets.** Prefer assets created for the effect or official assets whose free-use terms are verified. Do not assume an asset is shareable because it is visible in the editor or included in a project. Avoid recognizable protected characters, logos, and copied artwork. Keep source files and record asset origin, license, and required attribution for any third-party material.
4. **Build in the native project.** Prefer Xiangsu tools/MCP when available, following their current tool instructions and the complete SceneEditing skill before using `edit_by_dsl`. Inspect the target object and component before changing bindings. For an image import, `import_resource` creates a project asset but does not bind it automatically: use the returned resource GUID and the actual texture property discovered on the target component.
5. **Iterate against the live preview.** After visible changes, refresh the Xiangsu preview and inspect the returned image. Confirm that transparency, placement, face visibility, and colors match the intended version. A successful command or save is not visual verification.
6. **Save and confirm.** Save the active project in place unless the user asked for another destination. Confirm the project reports saved and unchanged after the save, and report the project and preview locations clearly.

## Important asset refresh and rollback behavior

- Replacing a PNG on disk may leave Xiangsu showing its cached imported texture. When an updated image does not appear in the live preview, import the current source file through Xiangsu, bind the newly returned GUID to the existing Image component, then refresh and inspect the preview. Do not treat writing the project asset file alone as proof that the editor reloaded it.
- When reverting a visual edit, inspect both scene objects and the source image. A panel or trim may be part of the raster image itself, so removing an extra layer or undoing scene changes may not restore the earlier look. Rebind the restored image and verify the live preview before saving.
- Avoid leaving duplicate assets when practical. Before deleting an older asset, verify that no scene object or material still references it. Preserve the working source file used to generate custom visuals.

## Visual and effect choices

- Add filters, face retouch, makeup, or facial artwork only when the brief calls for them. Keep skin and makeup adjustments moderate, check them on the preview face, and make sure global color changes do not darken the overall image unintentionally.
- Prefer original illustrations and shapes. For custom raster overlays, keep a reusable source (for example, a drawing script or editable vector) alongside the exported PNG when it materially helps future revisions.
- Confirm frame placement and scale against the active preview format rather than assuming a fixed canvas size. Use transparent backgrounds for overlays unless the user asked for a full-scene background.

## Reference

Read [references/production-workflow.md](references/production-workflow.md) when you need the detailed asset, iteration, and handoff checklist.
