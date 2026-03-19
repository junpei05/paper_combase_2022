# 2D Colormap Viewer for Bacterial Population Behavior

An interactive web application to explore the 2D colormap visualizations presented in **Figure 4** and **Supplementary figures** of Hosoe & Sunagawa et al. (2022).

**App URL:** [https://app2dcolormap-6kdothisijw76lj7hyxl3n.streamlit.app/](https://app2dcolormap-6kdothisijw76lj7hyxl3n.streamlit.app/)

---

## Overview

This app allows users to interactively reproduce and explore the 2D colormaps from the paper. The colormaps visualize the predicted bacterial population behavior (growth or inactivation) across combinations of two environmental conditions, while holding other conditions fixed. 

---

## Related Figures in the Paper

| Figure | Description |
|---|---|
| Figure 4 | 2D colormaps of predicted bacterial behavior under selected pairs of environmental conditions |
| Supplementary | Additional colormaps for other species and condition combinations |

---

## How to Use

1. **Select a bacterial species** from the dropdown menu.
2. **Choose the two environmental conditions** to display on the X and Y axes.
3. **Set the remaining conditions** using the sliders or input fields.
4. The 2D colormap updates automatically to show predicted bacterial behavior across the selected condition space.

---

## Input Parameters

| Parameter | Description | Unit |
|---|---|---|
| Species | Target bacterial species | — |
| Temperature | Storage or processing temperature | °C |
| pH | Acidity of the food environment | — |
| Water activity  | Available moisture in the food | — |
| Other conditions | Additional food environment variables | — |

---

## Output

The app displays a 2D colormap where:

- **Each axis** represents one of the selected environmental conditions.
- **Color** indicates the predicted bacterial population behavior:
  - Warm colors (e.g., red/orange) → growth
  - Cool colors (e.g., blue) → inactivation or no growth
- **Contour lines** mark the boundary between growth and inactivation regions.

---

## Citation

If you use this app or the associated analysis, please cite:

```bibtex
@article{hosoe2022datamining,
  author  = {Hosoe, Jun and Sunagawa, Junpei and Nakaoka, Shinji and Koseki, Shigenobu and Koyama, Kento},
  title   = {Data mining for prediction and interpretation of bacterial population behavior in food},
  journal = {Frontiers in Food Science and Technology},
  volume  = {2},
  pages   = {979028},
  year    = {2022},
  doi     = {10.3389/frfst.2022.979028}
}
```

---

## Related Resources

- [GitHub Repository](https://github.com/junpei05/paper_combase_2022)
- [Paper (DOI: 10.3389/frfst.2022.979028)](https://doi.org/10.3389/frfst.2022.979028)
- [ComBase Database](https://www.combase.cc/)
