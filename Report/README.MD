#Report 

![Report Full](https://github.com/GuiilhermeLorenzetti/CloudWalk/raw/main/imagem/report%20-%20full.png)

#Video

Link -> https://www.youtube.com/watch?v=DhFziGEYdI8


At the top of the report, users can use slicers to filter the view according to their interests. You can select a specific product, entity, payment method, or date range.

![Slicer](https://github.com/GuiilhermeLorenzetti/CloudWalk/raw/main/imagem/slicer.png)

Just below, we have the main indicators (big numbers), which provide an overview of the most relevant KPIs. The goal here is to enable a quick understanding of the business's health. The available data refers to the year 2025, but the structure is already prepared for “Same Period Last Year” comparisons, which will allow users to observe variations relative to the same period in the previous year.

Due to time constraints, I haven’t added it yet, but it would be possible to enhance the indicators with raw values + percentage variation, as well as use color formatting to highlight positive or negative trends.

![Big Numbers](https://github.com/GuiilhermeLorenzetti/CloudWalk/raw/main/imagem/big_number.png)

If the user wishes to explore any of the main indicators in more detail, they can select it from the side menu:

![Artifacts](https://github.com/GuiilhermeLorenzetti/CloudWalk/raw/main/imagem/artifacts.png)

The selected indicator will be reflected across all visuals below the selection.

![Analytical Report](https://github.com/GuiilhermeLorenzetti/CloudWalk/raw/main/imagem/analytical.png)

For more complex analyses, the report includes the “Report” tab, which simulates a pivot table structure. In this tab, the user can choose which metrics and dimensions to cross, providing flexibility to answer specific questions.

In production environments, it’s common to apply techniques to reduce processing usage in this area (such as measures with conditional visibility, automatic filters, or dynamic aggregations). However, I chose to keep the navigation simpler here, avoiding unnecessary clicks in the user's journey.

