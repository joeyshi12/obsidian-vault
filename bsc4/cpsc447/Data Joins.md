---
course: MATH447
title: Data Joins
tags: D3
date: [[2023-01-20]]
---

## Virtual Selections
- Enter: What happens to new data values without existing, associated DOM elements?
- Update: What happens to existing elements which have changed?
- Exit: What happens to existing DOM elements which are not associated with data anymore?

```javascript
const svg = d3.select('svg')

// Call rendering function with 2 datasets sequentially
updateChart([5, 10, 15]);
updateChart([20, 30]);

function updateChart(data) {
  // Data-join (circle now contains the update selection)
  let circle = svg.selectAll('circle')
      .data(data);

  // Enter (initialize the newly added elements)
  let circleEnter = circle.enter().append('circle')
      .attr('fill', '#707086')

  // Enter and Update (set the dynamic properties of the elements)
  circleEnter.merge(circle)
      .attr('r', d => d)
      .attr('cx', (d,index) => (index * 80) + 50)
      .attr('cy', 80);

  // Exit
  circle.exit().remove();
}
```

![[Pasted image 20230120141408.png|400]]

## Key function
- The default key function are the indices of the array `[10, 15]` (i.e., 0, 1)
- Keys indexes the circles we select below
- Similar to assigning ids selecting by ids

![[Pasted image 20230120142258.png]]

![[Pasted image 20230120143134.png]]

