# Free IP Camera Placement and Coverage Analysis Tools

Research date: November 2, 2026

## Overview

Camera placement tools help position cameras on a floor plan or map. Coverage analysis tools estimate what each camera can see and how much image detail will be available at different distances. Many products combine both functions.

This report summarizes vendor-published features and free-use conditions. It is a desk-research comparison, not a hands-on accuracy or performance test. Pricing and beta conditions may change.

## 1. IP Camera Placement Tools

| Tool | Free-use conditions | Key placement features | Main consideration |
| --- | --- | --- | --- |
| [CamLayout](https://camlayout.com/) | Advertises all features as free, with unlimited projects and no subscription. | Import floor-plan images; draw walls and obstacles; position cameras; visualize coverage cones and wall-related blind spots; generate PDF proposals. | Its built-in camera catalog is relatively small; custom camera models are supported. |
| [CCTVplanner](https://cctvplanner.io/ja) | Free plan: 2 projects, up to 6 cameras per project, with no time limit or payment card required. | Place cameras on satellite maps or floor plans; review coverage and DORI zones; inspect a 3D scene; export PDF reports. | Larger projects require checking paid-plan limits. Do not assume every advertised export feature is included in Free. |
| [JVSG Online](https://www.jvsg.com/online/) | Completely free while in beta. | Upload site plans; position cameras; review scenes in 2D and 3D; add photos and notes; save and share projects. | Free access is tied to the beta period; permanent free access has not been confirmed. |

### Suggested starting points

- **CamLayout:** A candidate for planning without a published project-count limit.
- **CCTVplanner:** A candidate for small projects that fit within the six-camera limit and for users who prefer a Japanese-language website.
- **JVSG Online:** A candidate for browser-based 2D/3D planning, particularly when working with JVSG project files.

## 2. IP Camera Coverage Analysis Tools

“IP Camera Coverage Analysis Tool” is used here as a category description. The research did not identify a specific standalone product with that exact name.

| Tool | Free-use conditions | Coverage analysis capabilities | Best-fit use case |
| --- | --- | --- | --- |
| [JVSG Lens Calculator](https://www.jvsg.com/calculators/cctv-lens-calculator/) | Advertised by JVSG as a free online calculator. | Camera model database, field-of-view visualization, 3D graphics, DORI zones, and floor-plan import. | Exploring lens choices and estimated useful viewing distances. |
| [AXIS Site Designer](https://www.axis.com/ja-jp/support/tools/axis-site-designer) | Axis describes it as a free tool. | Place cameras on maps or floor plans and visualize coverage; review 3D coverage during camera selection. The manual also documents generic-camera support. | Axis-focused system design and site-wide coverage planning. |
| [JVSG Online](https://www.jvsg.com/online/) | Free during beta. | Review camera coverage and DORI zones in a 2D/3D project. | Exploring coverage across a site with multiple cameras. |
| [CCTVplanner](https://cctvplanner.io/) | Free plan: 2 projects with up to 6 cameras each; no time limit. | Lens-based field-of-view and DORI calculations, map/floor-plan placement, and 3D scene review. | Small installations requiring placement and coverage analysis together. |

### What to check

| Metric | Practical question |
| --- | --- |
| Field of view (FOV) | How wide and tall is the area visible to the camera? |
| Coverage at a target distance | Does the view include the doorway, aisle, or other area of interest? |
| Pixel density | How much image detail is available at the target location? |
| DORI zones | At what distances might detection, observation, recognition, or identification be possible? |
| Occlusion and overlap | Do obstacles block the view, and do adjacent cameras leave coverage gaps? Check whether the selected tool actually models the relevant obstacles. |

DORI stands for **Detection, Observation, Recognition, and Identification**. These are estimated image-detail levels, not a guarantee of real-world identification. Lighting, motion, compression, focus, lens distortion, and installation conditions can affect results.

## 3. Recommendations

1. **For a quick lens and coverage calculation:** Start with JVSG Lens Calculator.
2. **For free layout planning without a published project-count limit:** Evaluate CamLayout.
3. **For a small project with up to six cameras:** Evaluate CCTVplanner's free plan.
4. **For browser-based 3D planning:** Try JVSG Online while its beta remains free.
5. **For an Axis-based installation:** Use AXIS Site Designer to plan camera selection and site coverage.

All tools listed above are browser-based options. The paid Windows desktop product **IP Video System Design Tool** is separate from JVSG Online and the free Lens Calculator; its free trial should not be treated as a permanent free edition.

## 4. Sources

- [CamLayout — features and free-use statements](https://camlayout.com/)
- [CCTVplanner — features and free-plan limits](https://cctvplanner.io/)
- [CCTVplanner — Japanese website](https://cctvplanner.io/ja)
- [JVSG Online — features and beta conditions](https://www.jvsg.com/online/)
- [JVSG — free online lens calculator description](https://www.jvsg.com/cctv-design-software-mac/)
- [JVSG Lens Calculator — application](https://www.jvsg.com/calculators/cctv-lens-calculator/)
- [AXIS Site Designer — product page](https://www.axis.com/ja-jp/support/tools/axis-site-designer)
- [AXIS Site Designer — user manual, including generic cameras](https://help.axis.com/en-us/axis-site-designer)
- [Axis — free Site Designer tool](https://www.americas-comms.axis.com/IntegratorSuite)
- [AXIS Site Designer — product-specific terms and estimation limitations](https://www.axis.com/dam/public/72/88/a2/axis-site-designer--product-specifc-terms--aug-202511243811124391pdf-en-US-498770.pdf)
- [JVSG desktop software — pricing and trial information](https://www.jvsg.com/order/)
