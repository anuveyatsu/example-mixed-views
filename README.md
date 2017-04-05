S&P 500 index data including level, dividend, earnings and P/E ratio on a monthly basis since 1870. The S&P 500 (Standard and Poor's 500) is a free-float, capitalization-weighted index of the top 500 publicly listed stocks in the US (top 500 by market cap).

## Views

To create graphs for your tabular DataPackage, the datapackage.json should include the views attribute that defines data views.

<script src="https://gist.github.com/anuveyatsu/881edf757c2ee3fe08b439d6c489c5ed.js"></script>

### Simple Graph Specifications

On line 76 we define the first view that uses "Simple Graph Spec", `specType` inside `views` attribute is set to `simple` - line 79.

There are only 3 properties enough to define graph specifications. They should be set inside `spec` attribute - line 80.

<table class="table table-bordered table-striped resource-summary">
  <thead>
   <tr>
     <th>Attribute</th>
     <th>Type</th>
     <th>Description</th>
   </tr>
  </thead>
  <tbody>
    <tr>
      <th>type</th>
      <td>String</td>
      <td>line, bar, pie (defaults to line)</td>
    </tr>
    <tr>
      <th>group</th>
      <td>String</td>
      <td>Field name, that will be used as abscissa (usually date field)</td>
    </tr>
    <tr>
      <th>series</th>
      <td>Array</td>
      <td>Field name(s) that will be used as ordinate</td>
    </tr>
  </tbody>
</table>

### Vega Graph Specifications

On line 86, we define the second view with vega spec. To use "Vega Graph Specification" `specType` inside `views` attribute should be set to `vega` - line 89. You can use almost the same specifications inside `spec` attribute, that are used for setting the vega graphs. Only difference is that in `data` property, all `url` and `path` attributes are moved out. Instead of that, `source` attribute is used to reference a dataset - line 97.

### Other attributes of a "view" property

Outside of `spec` attribute there are some other important parameters to note:

<table class="table table-bordered table-striped resource-summary">
  <thead>
   <tr>
     <th>Attribute</th>
     <th>Type</th>
     <th>Description</th>
   </tr>
  </thead>
  <tbody>
    <tr>
      <th>name</th>
      <td>String</td>
      <td>Unique identifier for view within list of views (lines 51 and 62)</td>
    </tr>
    <tr>
      <th>title</th>
      <td>String</td>
      <td>Title for the graph (lines 52 and 63)</td>
    </tr>
    <tr>
      <th>resources</th>
      <td>Array</td>
      <td>Data sources for this spec. It can be either resource name or index. By default it is the first resource (lines 53 and 64)</td>
    </tr>
    <tr>
      <th>specType</th>
      <td>String</td>
      <td>Available options: simple, vega, plotly <strong>(Required)</strong></td>
    </tr>
  </tbody>
</table>
