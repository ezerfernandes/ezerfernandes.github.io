---
layout: post
title: "Visualizing financial statements"
date: 2021-02-17
---

I don't understand why sources of data as rich as financial statements are not shown more often as charts. I believe visualizing them in other ways than just tables can be very insightful. I want to show here some possibilities for visualizing financial statements.

First of all, studies starting at 1984, with [William S. Cleveland and Robert McGill](https://www.jstor.org/stable/pdf/2288400.pdf), have demonstrated that certain dimensions are better perceived by humans than others; for example, length is better discerned than area. Below is a nice table ranking these dimensions. I copied it from [this article](https://knowablemagazine.org/article/mind/2019/science-data-visualization) (it's a good article by itself, go read it if you are interested):

{% include image.html url="/images/ranking_visual_elements.png" description="Sources: Cleveland, W.S. & McGill R., 1984; O'Donoghue S. I. et al. apud Mason B., 10.1146/knowable-110919-1, 2019." size="60%" %}

With that in mind, we can start trying some visualizations with one of the financial statements.

## The Might Balance Sheet

A balance sheet shows a company's assets, liabilities and shareholders' equity at a specific point in time. Some obvious visualizations would be a bar chart for comparing accounts' values on a specific time point or a line graph to compare account's values over time. I'd like to suggest two other possibilities.

### Sankey Diagram

A sankey diagram is usually used to display flows from one set of values to another so that they show a many-to-many mapping between domains.

Well, if you look at a balance sheet, you'll see the accounts can be composed of sub-accounts. In the first level, the balance sheet can be divided as Assets, Liabilities and Capital. In the second level, Asset can be divided as Current Assets, Long-Term Assets and so on. If you consider every level a set of values (accounts), you can show how the accounts are sub-divided in sub-accounts in relation to the total value. Well, better shown than said:

{% include image.html url="/images/sankey_balance_sheet.png" description="Showing a balance sheet as a Sankey diagram." size="80%" %}

Well, I think this illustrates the point of an unusual use of a chart to show the relationship between accounts and sub-accounts in very intuitive way.

