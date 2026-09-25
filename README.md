# PolyUMI project page

Static project page for *PolyUMI: Accessible Visual–Tactile–Audio Data Collection
for Object Inference and Manipulation*.

## Deploying to GitHub Pages

1. Copy `index.html`, `assets/` and `.nojekyll` into the repository you want to
   publish from (either a `polyumi.github.io` repo, or a `gh-pages` branch /
   `/docs` folder of the main repo).
2. Repo → Settings → Pages → Source: the branch and folder you used.
3. The site appears at `https://<org>.github.io/<repo>/`.

All asset paths are relative, so the page works from a project subpath as well
as from a user/org root. Filenames are lowercase — GitHub's servers are
case-sensitive even though macOS and Windows are not.

## Files you still need to add

- `assets/Slip_control_w6x.mp4` — slip control section.
The page renders without them, but those video players will be empty. Both
filenames are case-sensitive on GitHub's servers even though they aren't on
macOS or Windows.

## Tuning the layout

- **Hero size** — `.hero { --hero-max-w: 880px; --hero-pad: 44px }` near the top
  of the stylesheet. Lower `--hero-max-w` for a more compact hero (760px is
  noticeably smaller), raise it toward 1100px for a dominant one.
- **System overview figure** — sits in `.wrap-wide` (1340px) instead of the
  1120px body column so it reads slightly larger. Change the class to `wrap` to
  bring it in line.
- **Tall clips** — a `figure.cap-h` caps its video by height (`--cap`, default
  480px) and centres it, for clips that would otherwise run very tall at full
  column width. Used for the slip control and shaking videos.
- **Comparison table** — uses `table.compact` for tighter rows. Drop the class
  for the normal spacing.
- **Shape recognition figures** — fixed height via `.shape-pair { --shape-h }`
  so the tactile strip and the confusion matrix sit in equal-height cards.
- **Logo** — `.title-wrap { --mark-h; --mark-gap }`. Above 1180px the logo is
  parked outside the right edge of the centred title block; below that it drops
  to a centred row above the title.
- **Colour** — the page is flat white; sections are separated by hairlines
  only. `--tint` is set to `#FFFFFF`; give it a value if you ever want the
  bands back. The three modality colours appear as a 4px `.accent-rule` at the
  top and bottom of the page, and as a per-experiment highlight: a result block
  appear in the modality chips on each result block and as the `.accent-rule`
  at the top (4px) and bottom (14px) of the page.
- **Finger transfer clip** — portrait, so `.transfer-pair` caps it by height
  (`--transfer-h`) instead of width and gives the facts column the wider share.
- **Rollout videos** — the board-wiping clip is 16:9 and the lightbulb clip is
  portrait, so `.rollout-pair` weights the columns 2.3 : 1 to bring both players
  to about the same rendered height. Re-export either clip at a different
  aspect and that ratio needs adjusting.

## Before going live

- Confirm the repo URL `https://github.com/polyumi/PolyUMI-platform` is correct
  (it appears in the nav, the button row and the footer).

## Assets

| File | Source |
| --- | --- |
| `assets/hero.jpg` | `hero_v2_nofade.jpg`, resized to 2200 px wide |
| `assets/system.jpg` | `system_v2.jpg`, resized to 3000 px wide |
| `assets/vista-model.png` | `vista_model_2.png` |
| `assets/tactile-shapes.png` | `polyumi_tactile_shapes.png` |
| `assets/shape-confusion.png` | `polyumi_shape_results_wobjects_3.png` |
| `assets/shake-setup.png` | `polyumi_shake_setup_audio_2_switched.png` |
| `assets/audio-confusion.png` | `polyumi_audio_classification_results.png` |
| `assets/slip-setup.png` | `polyumi_slip_setup_3.png` |
| `assets/success-rates.png` | `success_rates_h275.png` |
| `assets/polyumi-overview.mp4` | `polyumi_video_3min.mp4` (unchanged, 19 MB) |
| `assets/polyumi_board_wiping_1.mp4` | re-encoded to 720p, 26 MB → 630 KB |
| `assets/Slip_control_w6x.mp4` | cropped to 1300×1080 then scaled to 1100 wide, audio stripped |
| `assets/polyumi_shaking_1.mp4` | cropped to the gripper and box (1120×630 from 1920×1080) |
| `assets/PolyTouch_finger_transfer.mp4` | pillarbox cropped away (1920×1080 → 610×1080), audio stripped |
| `assets/polyumi_lightbulb.mp4` | rotation baked in, cropped at the bottom to 576×780, audio stripped |
| `assets/poster-boardwiping.jpg`, `assets/poster-lightbulb.jpg` | poster frames at 1 s |
| `assets/video-poster.jpg` | frame at 4 s of the video |
| `assets/polyumi_manuscript.pdf` | `PolyUMI_Manuscript_0.pdf` |
| `assets/polyumi-logo.png` | `polyumi_logo_4.png`, unchanged |
| `assets/logo.svg` | mark redrawn from the logo as vector, transparent background |
| `assets/apple-touch-icon.png` | 180 px icon from the logo |

Figures with transparent backgrounds were flattened onto white so they stay
legible inside the page's cards.

## Background colours, for logo work

| Where | Hex |
| --- | --- |
| Page background, cards, tables, footer | `#FFFFFF` |
| Hairlines and card borders | `#E6E2EE` |
| Body text / ink | `#1B1430` |
| Modality blue / pink / orange (from the logo) | `#5E84EA` / `#DD9DD8` / `#F09035` |

The logo appears on white in the header and the sticky bar, so an opaque white
background no longer shows a box. A transparent background is still worth
having — it keeps the logo usable on the `#FAF9FC` bands and on slides.

`assets/logo.svg` is a vector redraw of the three modality shapes on a
transparent background — unused by the page, kept in case it's a useful
starting point.
