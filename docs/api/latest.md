# API Docs - v2.0.0

!!! Info "Tested Siddhi Core version: *<a target="_blank" href="http://siddhi.io/en/v5.1/docs/query-guide/">5.1.1</a>*"
    It could also support other Siddhi Core minor versions.

## Stats

### median *<a target="_blank" href="http://siddhi.io/en/v5.1/docs/query-guide/#aggregate-function">(Aggregate Function)</a>*
<p style="word-wrap: break-word">This extension returns the median of aggregated events.<br>&nbsp;As the calculation of the median is performed with the arrival and expiry of each event, it is not recommended to use this extension for large window sizes.</p>
<span id="syntax" class="md-typeset" style="display: block; font-weight: bold;">Syntax</span>

```
<DOUBLE> stats:median(<INT|LONG|DOUBLE|FLOAT> data)
```

<span id="query-parameters" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">QUERY PARAMETERS</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Default Value</th>
        <th>Possible Data Types</th>
        <th>Optional</th>
        <th>Dynamic</th>
    </tr>
    <tr>
        <td style="vertical-align: top">data</td>
        <td style="vertical-align: top; word-wrap: break-word">The value that needs to be aggregated in order to obtain its median.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">INT<br>LONG<br>DOUBLE<br>FLOAT</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
</table>

<span id="examples" class="md-typeset" style="display: block; font-weight: bold;">Examples</span>
<span id="example-1" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">EXAMPLE 1</span>
```
from InputStream#window.length(5)
select stats:median(value) as medianOfValues
insert into OutputStream;
```
<p style="word-wrap: break-word">This returns the median of the aggregated values as a 'double' value with the arrival and expiry of each event within the sliding window length of five.</p>

