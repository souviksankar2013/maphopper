<span id="title-text">Isoschrone API Mapping Documentation</span>
========================================================================================


-   **bold** = Default Value
-   *italic* = function
-   ***bold\_italic*** = mapping not possible
-   `[i] = `Given JSONObject in the JSONArray
-   `< ... >` = final property that holds value(s)
-   "Request Parameter" = data that is passed along in a request to the
    proxy, but not used by Graphhopper directly. This information is
    only used in the mappings. Serves the purpose of filling holes of
    information that is not included in a Graphhopper response

**Mapbox Isochrone Response Object**

<table>
<thead>
<tr class="header">
<th>Mapbox</th>
<th>needed type</th>
<th>Used Graphhopper Data</th>
<th>type</th>
<th>Conversion</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>features</td>
<td>GeoJSON Feature Collection</td>
<td><br />
</td>
<td><br />
</td>
<td><br />
</td>
<td><br />
</td>
</tr>
</tbody>
</table>

**Feature Object**

<table style="width:100%;">
<colgroup>
<col style="width: 28%" />
<col style="width: 14%" />
<col style="width: 24%" />
<col style="width: 7%" />
<col style="width: 13%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>Mapbox</th>
<th>needed type</th>
<th>Used Graphhopper Data</th>
<th>type</th>
<th>Conversion</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>type</code></td>
<td>String</td>
<td><br />
</td>
<td><br />
</td>
<td><strong>Feature</strong></td>
<td><br />
</td>
</tr>
<tr class="even">
<td><code>properties</code></td>
<td>Properties Object</td>
<td><br />
</td>
<td><br />
</td>
<td><br />
</td>
<td><br />
</td>
</tr>
<tr class="odd">
<td><code>geometry</code></td>
<td>Geometry Object</td>
<td><br />
</td>
<td><br />
</td>
<td><br />
</td>
<td><br />
</td>
</tr>
</tbody>
</table>

**Properties Object**

<table>
<thead>
<tr class="header">
<th>Mapbox</th>
<th>needed type</th>
<th>Used Graphhopper Data</th>
<th>type</th>
<th>Conversion</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>contour</code></td>
<td>Integer</td>
<td><p><code>polygons[i].properties.&lt;bucket&gt;</code></p>
<p>Request Parameter: <code>buckets</code></p></td>
<td>Integer</td>
<td><p><em>getContourMinutes()</em></p>
<p>returns total time multiplied by fraction (current bucket in totalAmountOfBuckets)</p>
<p>example:<br />
total_time = 60 minutes, amountOfBuckets = 2,</p>
<p>minutes_first_contour = (1/2) * 60 = 30</p></td>
<td>Buckets: describes the amount of different intervals for which a polygon is created</td>
</tr>
<tr class="even">
<td><code>color</code></td>
<td>String (#..)</td>
<td>Request Parameter: <code>contours_colors</code></td>
<td>Array&lt;String&gt;</td>
<td><p><em>getContourColor()</em></p>
<p>returns specified color in passed contours_colors Array for current bucket (Default = <code>#ff0000</code> (red))</p></td>
<td>Colors are not specified in a GH request. The contours_colors parameter is just used by the mapper, and not by GH itself.</td>
</tr>
<tr class="odd">
<td><code>opacity</code></td>
<td>Double</td>
<td><br />
</td>
<td>Double</td>
<td><strong>0.33</strong></td>
<td>This is not parameterized since Mapbox also uses <strong>0.33</strong> as a default with no option to change</td>
</tr>
<tr class="even">
<td><code>fill</code></td>
<td>String (#...)</td>
<td>(See<code> .color</code>)</td>
<td><br />
</td>
<td><br />
</td>
<td><br />
</td>
</tr>
<tr class="odd">
<td><code>fill-opacity</code></td>
<td>Double</td>
<td>(See<code> .opacity</code>)</td>
<td><br />
</td>
<td><br />
</td>
<td><br />
</td>
</tr>
<tr class="even">
<td><code>fillColor</code></td>
<td>String (#...)</td>
<td>(See<code> .color</code>)</td>
<td><br />
</td>
<td><br />
</td>
<td><br />
</td>
</tr>
<tr class="odd">
<td><code>fillOpacity</code></td>
<td>Double</td>
<td>(See<code> .opacity</code>)</td>
<td><br />
</td>
<td><br />
</td>
<td><br />
</td>
</tr>
</tbody>
</table>

**Geometry Object**

<table>
<thead>
<tr class="header">
<th>Mapbox</th>
<th>needed type</th>
<th>Used Graphhopper Data</th>
<th>type</th>
<th>Conversion</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>geometry.coordinates</code></td>
<td>Array&lt;Double&gt;</td>
<td><code>polygons[i].geometry.&lt;coordiantes&gt;</code></td>
<td>Array&lt;Double&gt;</td>
<td>No conversion needed</td>
<td><br />
</td>
</tr>
<tr class="even">
<td><code>geometry.type</code></td>
<td>String</td>
<td><br />
</td>
<td>String</td>
<td><strong>Polygon</strong></td>
<td><br />
</td>
</tr>
</tbody>
</table>


Document generated by Confluence on 05.Feb.2019 9:40

[Atlassian](http://www.atlassian.com/)
