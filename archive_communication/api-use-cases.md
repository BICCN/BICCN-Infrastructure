# API Use Cases

This document outlines use cases for APIs at archives. Requirements supporting the
use cases are documented in a separate [requirements doc](api-requirements.md).


<table id="new-project" class="tg">
<thead>
  <tr>
    <th class="tg-0pky">Use case #</th>
    <th class="tg-0pky">1</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky">Name</td>
    <td class="tg-0pky">Data inventory – new project</td>
  </tr>
  <tr>
    <td class="tg-0pky">Actors</td>
    <td class="tg-0pky">BCDC service account</td>
  </tr>
  <tr>
    <td class="tg-0pky">Description</td>
    <td class="tg-0pky">
        <ul>
            <li>
                BCDC wants to collect the metadata of a new project that has not yet been registered with BCDC, and has already submitted data to an archive.
            </li>
            <li>
                <span>The BCDC service account queries the archive’s API using the archive’s local identifier for the given project to retrieve metadata. 
                See <a href="https://github.com/BICCN/BCDC-Metadata/blob/83b00c19d21a7ef73196936a7b8e66b8637e59ee/design/schema/mappings.csv">schema mapping document</a> for a work in progress map between BCDC and archive schemas.</span>
            </li>
        </ul>
    </td>
  </tr>
</tbody>
</table>

<table id="registered-projects" class="tg">
<thead>
  <tr>
    <th class="tg-0lax">Use case #</th>
    <th class="tg-0lax">2</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">Name</td>
    <td class="tg-0lax">Data inventory – registered projects</td>
  </tr>
  <tr>
    <td class="tg-0lax">Actors</td>
    <td class="tg-0lax">BCDC service account</td>
  </tr>
  <tr>
    <td class="tg-0lax">Description</td>
    <td class="tg-0lax">
        <ul>
            <li>
                BCDC wants to update the metadata of all projects that are currently registered with the BCDC and submitting data to a given archive.
            </li>
            <li>
                <span>
                    The BCDC service account queries the archive’s API using the project’s BCDC identifier to retrieve metadata for a given project. See <a href="https://github.com/BICCN/BCDC-Metadata/blob/83b00c19d21a7ef73196936a7b8e66b8637e59ee/design/schema/mappings.csv">schema mapping document</a> for a work in progress map between BCDC and archive schemas.
                </span>
            </li>
        </ul>
    </td>
  </tr>
</tbody>
</table>

<table id="samples" class="tg">
<thead>
  <tr>
    <th class="tg-0lax">Use case #</th>
    <th class="tg-0lax">3</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">Name</td>
    <td class="tg-0lax">Data inventory – samples</td>
  </tr>
  <tr>
    <td class="tg-0lax">Actors</td>
    <td class="tg-0lax">BCDC service account</td>
  </tr>
  <tr>
    <td class="tg-0lax">Description</td>
    <td class="tg-0lax">
    <ul>
        <li>
            BCDC wants to gather an inventory of all samples submitted to an archive for a given project registered with BCDC.
        </li>
        <li>
            BCDC’s service account queries the archive’s API for a project using either the BCDC identifier or the archive’s local identifier to retrieve a project’s metadata.
        </li>
        <li>
            <span>
                The project’s metadata contains a list of references to samples submitted for the project. The service account queries the API using the sample references and retrieves associated metadata. See <a href="https://github.com/BICCN/BCDC-Metadata/tree/master/Templates/sample_inventory"> specimen templates</a> for example metadata collected by BCDC.
            </span>
        </li>
    </ul>
  </tr>
</tbody>
</table>

<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax">Use case #</th>
    <th class="tg-0lax">4</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">Name</td>
    <td class="tg-0lax">Data inventory – asset manifests</td>
  </tr>
  <tr>
    <td class="tg-0lax">Actors</td>
    <td class="tg-0lax">BCDC service account</td>
  </tr>
  <tr>
    <td class="tg-0lax">Description</td>
    <td class="tg-0lax">
        <ul>
            <li>
                BCDC wants to gather an inventory of all assets submitted to an archive for a given project registered with BCDC.
            </li>
            <li>
                BCDC’s service account queries the archive’s API to using either the BCDC identifier or the archive’s local identifier to retrieve a project’s metadata.
            </li>
            <li>
                The project’s metadata includes a list of references to assets submitted. The service account queries the API using the asset references and retrieves associated metadata. Metadata include:
            </li>
                <ul>
                    <li>asset_id</li>
                    <li>asset_name</li>
                    <li>project_id</li>
                    <li>data_collection_id</li>
                    <li>asset_name</li>
                    <li>sample_id</li>
                    <li>URI</li>
                    <li>Filetype</li>
                    <li>Filesize</li>
                    <li>Checksum</li>
                    <li>Checksum type (SHA256, md5 etc)</li>
                </ul>
        </ul>
  </tr>
</tbody>
</table>

<table class="tg">
    <thead>
    <tr>
        <th class="tg-0lax">Use case #</th>
        <th class="tg-0lax">5</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td class="tg-0lax">Name</td>
        <td class="tg-0lax">Search – filter for projects</td>
    </tr>
    <tr>
        <td class="tg-0lax">Actors</td>
        <td class="tg-0lax">Scientist</td>
    </tr>
    <tr>
        <td class="tg-0lax">Description</td>
        <td class="tg-0lax">
            <ul>
                <li>
                    A scientist wants to find projects that use a particular technique, modality, or contain a specific type of sample.
                </li>
                <li>
                    They query the archive’s API using filters to retrieve a list of projects and associated metadata.
                </li>
            </ul>
    </tr>
    </tbody>
</table>

<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax">Use case #</th>
    <th class="tg-0lax">6</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">Name</td>
    <td class="tg-0lax">Search – filter for samples</td>
  </tr>
  <tr>
    <td class="tg-0lax">Actors</td>
    <td class="tg-0lax">Scientist</td>
  </tr>
  <tr>
    <td class="tg-0lax">Description</td>
    <td class="tg-0lax">
        <ul>
            <li>
                A scientist wants to find samples that were extracted from a specific anatomical region of a particular species of animal.
            </li>
            <li>
                They query the archive’s API using filters to retrieve a list of samples and the associated metadata. Metadata includes a reference either via ID or URI to the associated projects and assets.
            </li>
        </ul>
  </tr>
</tbody>
</table>

<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax">Use case #</th>
    <th class="tg-0lax">7</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">Name</td>
    <td class="tg-0lax">Validation</td>
  </tr>
  <tr>
    <td class="tg-0lax">Actors</td>
    <td class="tg-0lax">BCDC Service Account</td>
  </tr>
  <tr>
    <td class="tg-0lax">Description</td>
    <td class="tg-0lax">
        <ul>
            <li>
                BCDC wants to ingest a project’s samples for the inventory, but the samples submitted did not pass validation during ingest into the archives’ system.
            </li>
            <li>
                The service account queries a project and associated samples through the API and receives an Exception message that the samples did not pass validation.
            </li>
        </ul>
  </tr>
</tbody>
</table>