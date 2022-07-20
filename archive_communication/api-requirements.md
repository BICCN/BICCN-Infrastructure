# API Requirements

This document outlines some general requirements for APIs that would be necessary
for communication between BCDC, data archives, and other partners for one- or
two-way communication. These requirements don't mandate a specific implementation, 
but do make some assumptions around higher level design:

## Assumptions
- This document and the examples make a few assumptions about the APIs:
    - APIs communicate via JSON over HTTP
    - APIs roughly follow REST principles

## General Requirements

<table class="tg">
<thead>
  <tr>
    <th class="tg-g7sd">#</th>
    <th class="tg-g7sd">Requirement</th>
    <th class="tg-g7sd">Description</th>
    <th class="tg-g7sd">Priority</th>
    <th class="tg-g7sd">Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-lboi">1</td>
    <td class="tg-lboi">Individual user authentication</td>
    <td class="tg-lboi">If the API requires authentication, an individual user can authenticate themselves with an API Key or OAuth access token to interact with the API.</td>
    <td class="tg-lboi">Should have</td>
    <td class="tg-lboi">
        <ul>
            <li>Preferred OAuth mechanism would be ORCID.</li>
        </ul>
    </td>
  </tr>
  <tr>
    <td class="tg-lboi">2</td>
    <td class="tg-lboi">Service account authentication</td>
    <td class="tg-lboi">A downstream service can authenticate with an API Key to automate interactions with the API.</td>
    <td class="tg-lboi">Must have</td>
    <td class="tg-lboi"></td>
  </tr>
  <tr>
    <td class="tg-lboi">3</td>
    <td class="tg-lboi">Consistent, persistent identifier for objects</td>
    <td class="tg-lboi">A user or service should be able to access an object using the same identifying URI each time.</td>
    <td class="tg-lboi">Must have</td>
    <td class="tg-lboi"></td>
  </tr>
  <tr>
    <td class="tg-lboi">4</td>
    <td class="tg-lboi">Object schema documentation</td>
    <td class="tg-lboi">Objects fetched from API contain links to the schema used to generate/validate objects.</td>
    <td class="tg-lboi">Must have</td>
    <td class="tg-lboi">
        <ul>
            <li>JSONSchema preferred</li>
        </ul>
    </td>
  </tr>
  <tr>
    <td class="tg-lboi">5</td>
    <td class="tg-lboi">Versioned data schemas</td>
    <td class="tg-lboi">Schemas should have versions so as the schemas change, we can track which schema was used to generate/validate objects.</td>
    <td class="tg-lboi">Should have</td>
    <td class="tg-lboi">
        <ul>
            <li>JSONSchema preferred</li>
        </ul>
    </td>
  </tr>
  <tr>
    <td class="tg-lboi">6</td>
    <td class="tg-lboi">Related objects are easily findable from a given object</td>
    <td class="tg-lboi">Objects contain resource IDs or resource URIs for related objects.</td>
    <td class="tg-lboi">Must have</td>
    <td class="tg-lboi">
        <ul>
            <li> Supports use case <a href="api-use-cases.md"> Data inventory – new project</a>
            <li><a href="#related-objects">See example</a></li>
        </ul>
    </td>
  </tr>
  <tr>
    <td class="tg-lboi">7</td>
    <td class="tg-lboi">Consistent response status codes</td>
    <td class="tg-lboi">API responses should contain appropriate, standardized status codes.</td>
    <td class="tg-lboi">Must have</td>
    <td class="tg-lboi">
        <ul>
            <li>
                <a href="https://datatracker.ietf.org/doc/html/rfc2616"> 
                    Proposed standard: IETF RFC 2616
                </a>
            </li>
        </ul>
    </td>
  </tr>
  <tr>
    <td class="tg-lboi">8</td>
    <td class="tg-lboi">API endpoint documentation</td>
    <td class="tg-lboi">Public endpoints should be documented with expected request params and sample responses.</td>
    <td class="tg-lboi">Must have</td>
    <td class="tg-lboi"></td>
  </tr>
  <tr>
    <td class="tg-lboi">9</td>
    <td class="tg-lboi">Filtering results</td>
    <td class="tg-lboi">Results for API calls can be filtered via query string or filters specified in the request body.</td>
    <td class="tg-lboi">Nice to have</td>
    <td class="tg-lboi">
        <ul>
            <li><a href="#filtering-results">See example</a></li>
        </ul>
    </td>
  </tr>
  <tr>
    <td class="tg-lboi">10</td>
    <td class="tg-lboi">Searching by BCDC identifier</td>
    <td class="tg-lboi">A user should be able to find a resource using the resource's BCDC identifier</td>
    <td class="tg-lboi">Must have</td>
    <td class="tg-lboi">
        <ul>
            <li>
                Supports use case: <a href="api-use-cases.md"> Data inventory – registered projects </a>
            </li>
        </ul>
    </td>
  </tr>
  <tr>
    <td class="tg-lboi">11</td>
    <td class="tg-lboi">Searching by metadata</td>
    <td class="tg-lboi">Search for data sets using parameters like grant number, species, technique, etc.</td>
    <td class="tg-lboi">Nice to have</td>
    <td class="tg-lboi">
        <ul>
            <li><a href="#searching"> See example </a></li>
            <li>Supports use case: <a href="api-use-cases.md"> Search – filter for projects</a></li>
            <li> Supports use case: <a href="api-use-cases.md">Search – filter for samples</a></li>
        </ul>
    </td>
  </tr>
  <tr>
    <td class="tg-lboi">12</td>
    <td class="tg-lboi">Validation exceptions</td>
    <td class="tg-lboi">If a dataset did not pass schema validation or meet a data standard, the API should message an exception when querying the dataset.</td>
    <td class="tg-lboi">Should have</td>
    <td class="tg-lboi">
        <ul>
            <li>Supports use case <a href="api-use-cases.md"> Validation </a></li>
        </ul>
    </td>
  </tr>
</tbody>
</table>

## NeMO Specific Requirements

<table class="tg">
<thead>
  <tr>
    <th class="tg-yla0">#</th>
    <th class="tg-yla0">Requirement</th>
    <th class="tg-yla0">Description</th>
    <th class="tg-yla0">Priority</th>
    <th class="tg-yla0">Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-cly1">1</td>
    <td class="tg-cly1">NeMO landing page and manifest metadata are available from data collection resource</td>
    <td class="tg-cly1">Once a data collection resource is found, a user should be able to navigate to the corresponding landing page and the manifest from the data collection’s metadata.</td>
    <td class="tg-cly1">Must have</td>
    <td class="tg-cly1"></td>
  </tr>
  <tr>
    <td class="tg-cly1">2</td>
    <td class="tg-cly1">NeMO collection identifier searchable or filterable using metadata</td>
    <td class="tg-cly1">A user should be able to find a data collection identifier using metadata such as technique, author, grant etc.</td>
    <td class="tg-cly1">Nice to have</td>
    <td class="tg-cly1"></td>
  </tr>
</tbody>
</table>

## Examples

### Related objects
---


```json
GET https://example.com/api/project/project1

{
    "id": "project1",
    "title": "Some title",
    "description": "Some description",
    "dataCollections": [
        {
            "id": "dataCollection1",
            "uri": "https://example.com/api/dataCollection/dataCollection1",
        },
        {
            "id": "dataCollection2",
            "uri": "https://example.com/api/dataCollection/dataCollection2",
        }
    ]
}
```

```json
GET https://example.com/api/dataCollection/dataCollection1

{
    "id": "dataCollection1",
    "title": "Some other title",
    "description": "Some other description",
    "projects": [
        {
            "id": "project1",
            "uri": "https://example.com/api/project/project1"
        },
        {
            "id": "project2",
            "uri": "https://example.com/api/project/project2"
        }
    ],
    "assets": [
       {
         "id": "imageFile1",
         "uri": "https://example.com/api/asset/imageFile1"
       },
       {
        "id": "fastqFile1",
        "uri": "https://example.com/api/asset/fastqFile1"
       }
    ]
}
```

```json
GET https://example.com/api/asset/imageFile1

{
    "id": "imageFile1",
    "filename": "some_filename.tiff",
    "extension": ".tiff",
    "dataCollections": [
        {
            "id": "dataCollection1",
            "uri": "https://example.com/api/dataCollection/dataCollection1",
        },
        {
            "id": "dataCollection2",
            "uri": "https://example.com/api/dataCollection/dataCollection2",
        }
    ]
}
```

### Filtering results
---
```json
//Filtering via query string
GET https://example.com/api/assets?dataCollection=dataCollection1&fileType=txt

{
    "assets": [
        {
            "id": "asset1",
            "title": "Sample title",
            "uri": "https://example.com/api/asset/asset1",
            "dataCollections" : [
                {
                    "id": "dataCollection1",
                    "uri": "https://example/com/api/dataCollection/dataCollection1"
                }
            ]
            "fileType": "txt"
        },
        {
            "id": "asset2",
            "title": "Sample title",
            "uri": "https://example.com/api/asset/asset2",
            "dataCollections" : [
                {
                    "id": "dataCollection1",
                    "uri": "https://example/com/api/dataCollection/dataCollection1"
                }
            ]
            "fileType": "txt"
        }
    ]
}

```
### Searching
---
```json
GET https://example.com/api/search?q=marmoset

{
    "projects": [
        {
            "id": "project1",
            "uri": "https://example.com/api/project/project1"
        }
    ],
    "dataCollections": [
        {
            "id": "dataCollection1",
            "uri": "https://example.com/api/dataCollection/dataCollection1"
        }
    ],
    ...
}

```



