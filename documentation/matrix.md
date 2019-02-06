
<span id="title-text">Matrix API Mapping Documentation</span>
====================================================================================

-   **bold** = Default Value
-   *italic* = function
-   ***bold\_italic*** = mapping not possible
-   `[i] = `Given JSONObject in the JSONArray
-   `< ... >` = final property that holds value(s)
-   "Request Parameter" = data that is passed along in a request to the
    proxy, but not used by Graphhopper directly. This information is
    only used in the mappings. Serves the purpose of filling holes of
    information that is not included in a Graphhopper response

**Mapbox Matrix Response Object**

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
<td><code>code</code></td>
<td>String</td>
<td><br />
</td>
<td>String</td>
<td><strong>Ok</strong></td>
<td><br />
</td>
</tr>
<tr class="even">
<td><code>durations</code></td>
<td>Array&lt;Array&lt;Double&gt;&gt;</td>
<td><code>&lt;times&gt;</code></td>
<td>Array&lt;Array&lt;Double&gt;&gt;</td>
<td>No conversion needed</td>
<td>Matrix of durations</td>
</tr>
<tr class="odd">
<td><code>distances</code></td>
<td>Array&lt;Array&lt;Double&gt;&gt;</td>
<td><code>&lt;distances&gt;</code></td>
<td>Array&lt;Array&lt;Double&gt;&gt;</td>
<td>No conversion needed</td>
<td><br />
</td>
</tr>
<tr class="even">
<td><code>sources</code></td>
<td>Array&lt;SourceObject&gt;</td>
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
<td><code>destinations</code></td>
<td>Array&lt;DestinationObject&gt;</td>
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


**Source Object**

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
<td><code>name</code></td>
<td>String</td>
<td><strong><em>No way to get the name of locations from a GH Matrix Response</em></strong></td>
<td>String</td>
<td><strong>' '</strong></td>
<td>Emtpy String</td>
</tr>
<tr class="even">
<td><code>location</code></td>
<td>Properties Object</td>
<td>Request Parameters: <code>point; from_point;</code></td>
<td>Array&lt;String&gt;</td>
<td>conversion to Array&lt;Double&gt;</td>
<td>the sources are not part of a GH response. They are fetched from the request as either <code>point</code> or <code>from_point</code> parameters</td>
</tr>
</tbody>
</table>

**Destination Object**

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
<td><code>name</code></td>
<td>String</td>
<td><strong><em>No way to get the name of locations from a GH Matrix Response</em></strong></td>
<td>String</td>
<td><strong>' '</strong></td>
<td>Emtpy String</td>
</tr>
<tr class="even">
<td><code>location</code></td>
<td>Properties Object</td>
<td>Request Parameters: <code>point; to_point;</code></td>
<td>Array&lt;String&gt;</td>
<td>conversion to Array&lt;Double&gt;</td>
<td>the destinations are not part of a GH response. They are fetched from the request as either <code>point</code> or <code>to_point</code> parameters</td>
</tr>
</tbody>
</table>

Ignored Data from the GH Response:

-   `weights`
-   `info`

Document generated by Confluence on 05.Feb.2019 9:40

[Atlassian](http://www.atlassian.com/)