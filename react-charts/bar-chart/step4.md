Add tooltips to the barchart.

1) <strong>Make sure the `App.js` file is still open.</strong>

2) <strong>Locate the `<Chart>` component.</strong>

<pre class="file">
&lt;Chart
  domainPadding={{ x: [30, 25] }}
  height={250}
  width={600}
&gt;
</pre>

3) <strong>Add a `containerComponent` property to that section</strong>

<pre class="file" data-target="clipboard">
containerComponent={
  &lt;ChartVoronoiContainer
    constrainToVisibleArea
    labels={({ datum }) =&gt; `${datum.name}: ${datum.y}`}
  /&gt;
}
</pre>

<strong>Notes:</strong>

- The `containerComponent` property takes a component instance which will be
used to create a container element for standalone charts
- The `ChartVoronoiContainer` component adds the ability to associate
a mouse position with the data point(s) closest to it.
This is useful for adding a tooltip.

Once the preview reloads - it should look like this:

<img src="bar-chart/assets/tooltips.png" alt="Chart with tooltips"
style="box-shadow: rgba(3, 3, 3, 0.2) 0px 1.25px 2.5px 0px;" />
