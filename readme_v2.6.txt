================================================================================
===
=== GeoNetwork 2.6.4: List of changes
===
================================================================================
--------------------------------------------------------------------------------
--- Changes
--------------------------------------------------------------------------------

- #456 Catalan translation, thanks Montserrat Marco Sabaté.
- #462: Load wms in map viewer for service metadata
- #463: Update Web Map Viewer OpenLayers to 2.10
- CSW Server configuration: use textarea for abstract and increase field size
  (label) in CswServerCapabilitiesInfo table
- Set WMC panel layout
- Added verbose protocol list for online resources (metadata editor)
- Turkish translation, thanks to the Turkish Kadastro (TKGM)
- #491: Custom ElementSet in CSW 2.0.2
- INSPIRE schematron fixes integrated from trunk
- CSW INSPIRE capabilities document updated to 1.0 xsd (scenario 2). Default
  values in capabilities_inspire.xml for TemporalReference, MetadataDate,
  SpatialDataServiceType, etc require user customization for his catalog

--------------------------------------------------------------------------------
--- Bug fixes
--------------------------------------------------------------------------------

- #299: Catch all empty elements with gco:nilReason=missing attribute to avoid
  large blank spaces in metadata views.
- #395: Use proxy configuration for built in proxy in GeoNetwork. Thanks schaubr
  for patch
- Fix for ticket #435 - thanks to Craig Jones, IMOS/eMii and Andrew Walsh, AODN
- #467: Search by abstract in Dublin Core doesn't find results
- #473: Left-column disappearing. Disabled scroll effect
- #476: Improvements to GeoNetworkAnalyzer
- Restore ending wildcard. Related to #476.
- Fix #478. Thanks Justin Rowles
- Fix resumptionToken handling in OAI-PMH harvester: backporting #7189
- OAIPHM havester fix for Until date, the From date value was used instead
- #492 : CSW 2.0.2 ElementName processing broken
- #503 Security hole in metadata insert
- Metadata insert, fixes when validation option is selected:
  1) validate xsd and schematron, both in copy&paste and file upload options
  2) show schematron report with errors (if any)
- Fix for save template display order

================================================================================
===
=== GeoNetwork 2.6.3: List of changes
===
================================================================================
--------------------------------------------------------------------------------
--- Bug fixes
--------------------------------------------------------------------------------

- #422 : 26x numeric fields range query bug
- #376 : Configurable stopwords fixes
- Tokenize responsiblePartyRole field to allow case insensitive searches
- Unification of INSPIRE GEMET thesaurus path for schematron rules and indexing
  of INSPIRE themes
- xml.user.metadata service changed to use Lucene instead of SQL

================================================================================
===
=== GeoNetwork 2.6.2: List of changes
===
================================================================================
--------------------------------------------------------------------------------
--- Bug fixes
--------------------------------------------------------------------------------

- Be sure id is an integer when creating SQL query. Thanks Pierre Mauduit
- Fix download with special character
- Protect code in getMetadataFromIndex if createDate or changeDate are null (for
  example, if created/harvested invalid metadata without this fields)
- Removed Download link (doesn't work within release documentation unless
  generic)
- Use permanent redirect instead of temporal redirect to avoid some issues when
  running with Apache proxy
- XSL processor configuration
- Fix #387 : GN vulnerable to other application's TransformerFactory
- Fix #397 : Thesaurus name after adding keyword
- Fix #398 : INSPIRE keywords not multilingual
- Fix #399 : Map in editor does not work correctly
- Fix #400 : Security hole in GeoNetwork -- search for owner
- Fix #413 : Fix typo in SQL scripts
- Fix #415 : Simple numeric indexing

--------------------------------------------------------------------------------
--- Changes
--------------------------------------------------------------------------------
- 2.6.x documentation updates
- Added documentation for ArcSDE harvester
- ArcSDE harvester documentation update
- GN logo points to http://geonetwork-opensource.org
- Improved documentation
- Improved pdf search print layout
- Removed InterMap log removal
- Small GUI improvements in search form
- Update version number in installer
- Updated Russian language files (thanks Irina Romanova)
- Updated documentation license
- Updated navigation for documentation
- Updated sql files for 2.6.2
- #376 : Configurable stopwords
- #391 Metadata Notifications to Remote Targets
- #407 : Option to discard invalid harvested metadata
- #410 : My Metadata function
- #411 : INSPIRE - support for CSW LANGUAGE parameter
- #412 : Add isPublishedToAll to geonet:info

================================================================================
===
=== GeoNetwork 2.6.1: List of changes
===
================================================================================
--------------------------------------------------------------------------------
--- Bug fixes
--------------------------------------------------------------------------------
- Exclude some substitutions which prevent the vertical extent element from
  being fully expanded
- Fix migration scripts from 2.4.3 to 2.6.0
- Fix search using INSPIRE annex
- Typo fix for German language
- Added support for sqlserver database. Thanks to Mikael Elmquist for provide
  sql files
- Add in xslt converters for DIF to ISO and Thredds
- Missing xslt to convert netcdf CDM coords to ISO keywords
- Fix harvesting a OAI set whose name contains a "-". Thanks Tim Proescholdt
- Fix #335: Max number of children displayed in relation panel. Added from and
  to parameters to allow paging in related records if needed
- Fix #339: Wildcard search broken
- Fix #337: Metadata indexing uses old INSPIRE setting
- Fix #343: CSW / iso19110 / exception when requesting ISO19139 output
- Fix #344: bad schema error when using XSL on import. Thanks murrayking
- Fix #345: Changed postgres driver version to be compatible with Java 1.5
- Fix #346: Javascript error when setting "singleTile: true" for a WMS layers in
  Map viewer
- Fix #347: Fix thesaurus directory removed by maven
- Fix #348: ArcSDE Harvester. Javascript error accessing config panel
- Fix #354: XSL error message in WMC to Iso19139 transformation
- Fix #357: Use geometry parameter in GUI search for bounding boxes, instead of
  lucene bbox fields. Fixed also Disjoint spatial filter
- Fix #364: CSW queryables, added support for INSPIRE ResponsiblePartyRole and
  fix for ResourceIdentifier
- Fix #365: Allow to configure LDAP uid attribute name
- Fix #366: Add contextual label translation allowing to use full xpath for
  elements in metadata editor
- Fix #367: Not possible to search on Subject queryable for a value that
  includes spaces
- Fix #371: Tooltips in System Configuration have disappeared

--------------------------------------------------------------------------------
--- Changes
--------------------------------------------------------------------------------
- Added support for OpenLayers Map config options in map viewer
- Service to retrieve the metadata owned by a user
- Use redirect for login and logout services to show in browser address bar the
  url of main page, after login/logout

================================================================================
===
=== GeoNetwork 2.6.0: List of changes
===
================================================================================
--------------------------------------------------------------------------------
--- Bug fixes
--------------------------------------------------------------------------------
- Fix for windows installer
- Included developer docs in installer and fixed links in index files
- Updated images and content in user manual (getting started section)
- Fix #311: For FGDC metadata the lat/lon values for the CSW response are
  concatenated instead of separated by a space (Thanks Marten Hogeweg)
- Fix #309: Open the CSV in a new page 
  Could not reproduce the dissapear of left menu. But seem better open CSV in a
  new window instead of repacing application window
- Fix #308: No result for "export as TXT" for templates
- Fix #303 : Invalid character when connecting to external database (Thanks to
  zoerb).
- Add missing data file for PostGIS.
- Fix to use proxy config in GetRecordsByIdRequest
- Fix #293: Fix for queries with AS clause in MySql. Thanks Justin Rowles for
  patch
- Fix #307: Use default OL cursors to avoid ServiceNotFoundEx exceptions in GN
  when using IE (IE doesn't resolve correctly cursor image url)
- Fix #319: Calendar buttons dont show the calendar in metadata editor after
  click on Check or Save button
- OGC harvester / Improve distribution info section for WMS service metadata.
- Included disclaimer window for WMS services in map viewer
- Fix to solve about some responses are cut when returned to the client
- Fix #320 typo
- Fix #304 WFS harvesting improvement.
- Fix #306 opener ref not used in trunk.
- xalan is not longer supported
- Fix #275: Image not showing
  The logo image for the GeoNetwork site was only created the first time when
  the database was initialized. 
  If the application was updated with a new version (images/logos folder only
  contains dummy.gif logo then) and preserving the database, the logo was not
  created again.
  Changed to check always in startup if logo for GeoNetwork site exists, if not
  then creates it
- Fix #320: parse and use mapSearch layers setting
  1) Map search uses custom layers if defined in config-gui.xml
  (mapSearch/layers). If not defined this section, uses layers defined for map
  viewer (mapViewer/layers)
  2) Use mapOptions hash, when initializing search maps
- Fix #323: Scrollbar in IE8
  Also happened in other browsers
- Zoom to region in search map, when selecting a region in combo list
- Protect resetInspireOptions method if inspire search panel is not enabled
- Fixes for thredds harvester - include validator precond, missing gif and
  recognition for thredds harvester Include baseUrl in geonet:info for scripts
  that don't have /root/gui info
  Include opendap-2.1 jar needed for thredds harvester
- Fix #328 LDAP DN Problem. Thanks to JoshVote for the fix.
- Fix remove uploaded file bug
- Fix #330 Improve validation report layout. Thanks Justin Rowles. 
- Fix #334 Web Map Viewer boudingbox taken from /root/gui/config/mapViewer
  subtree (Thanks Landry Breuil)

fixes in 2.6.0-1

- Fix migration scripts from 2.4.3 to 2.6.0
- Exclude some substitutions which prevent the vertical extent element from
  being fully expanded

================================================================================
===
=== GeoNetwork 2.6.0RC2: List of changes
===
================================================================================
--------------------------------------------------------------------------------
--- Bug fixes
--------------------------------------------------------------------------------

- Fix #223: manage parameter names from capabilities document in
  case-insensitive manner
- Fix #246: Simplify metadata view. Restored old layout to show metadata.
- Fix #257: Release the screen overlay in metadata editor when an error happen
  saving the metadata
- Fix #265: Fix for mis-aligned options in opera and IE
- Fix #271: CSW parent identifier field. Thanks Jürgen Weichand.
- Fix #272. Removing last element in simple mode.
- Fix #273: Update rss panel after delete metadata records
- Fix #276: Export as CSV issues
- Fix #278: Check online source already exist. Copy full distribution section
  content before update. Thanks Sylvain for testing.
- Fix #279: All maps are using same background layers. Harmonize size of all
  bbox inputs in edit and view mode.
- Fix #280: Alignment, highlighted, etc issues in metadata edit
- Fix #286: After click Metadata button in search results, editing a metadata
  show advanced edit instead of previously selected.
- Fix #288: Show number of records to delete in massive delete confirm message
- Fix #290: Improvements in export selection to pdf
- Fix #291: Menu "Actions on selection" issues
- Fix #292: Don't show the download button if the download link is empty
- Fix #294: Security hole in GeoNetwork search
- Fix #295: Calendar << and < buttons are not visible (blue on blue). Thanks
  Justin Rowles for patch
- Fix #296: Data rating window position
- Fix #301: Update saxon to fix JIT bug (also introduce 9.1.0.8b) 
- Fix #302: Include jdbm jar for JZKit3/Z3950 server
- OGC WMS Harvester / fix malformed URL. Add serviceType lucene field.
- Fix INSPIRE theme thesaurus name according to RDF file available in SVN
  utility folder.
- User manual updates
- Do not display translation tools icon if no other language declared.
- Fix selected group in advanced search

================================================================================
===
=== GeoNetwork 2.6.0RC1: List of changes
===
================================================================================
--------------------------------------------------------------------------------
--- Bug fixes
--------------------------------------------------------------------------------
- Fix for #263: Screen refresh not working
- Fix #266: Show alert if click on "Add templates" button and no selected
  templates. Remove from admin interface iso19115 templates.
- Fix for #267: Page coming up blank afer delete
- Fix for #268: Mis-aligned result in search
- Fix for #259: Fix for templates menu in administration
- #255: Fixed help links
- Fix for #265: Scroll-bar appearing when probably shouldn't
- #244: Update popup position always to work correctly when the window is
  resized
  Fixes for IE. Thanks to Jürgen Seib for reporting
- Fix GAST, "back to normal" since maven migration. Thanks to Jesse Eichar for
  his contribution.
- Map viewer: save map state in cookies (layers config and extent)
- Removed xlink:href attribute to link service and dataset in OGC WxS harvester
  which interact with XLink resolver. 
  Only uuidref attribute is used to navigate between records.
- Return all bboxes in brief formatting.
- Fix #250: Removing old thumbnail for OGC harvester.
- Fix #251. Xml search service does not use default param and does not keep any
  search results in session. Make it behave more like the main search service.
- Fix PDF print #252. Missing class due to wrong dependency version. Fix pdf
  selection and present print action.
- #244: Fix position of Other actions panel
- #253: User interface aligment issues in Opera and IE
- Replaced TRUNCATE with DELETE commands for Oracle data script.
- Removed optimization of updatePopularity in thread code.
- Update popularity also for harvested metadata.
- Fix CSV search broken by XSL output declaration in main.xsl.
- Fixes in LuceneQueryBuilder class
- Fix #249. Only one call to topDocs could be made on a TopFieldCollector.
- Speed up YUI compression excluding unnecessary JS files.
- Administration option to load metadata samples

================================================================================
===
=== GeoNetwork 2.6.0RC0: List of changes
===
================================================================================
--------------------------------------------------------------------------------
--- Bug fixes
--------------------------------------------------------------------------------
- Fix #146: Illegal character handling not robust
- Fix #170: Store more than one record in user session. Thanks Simon.
- Fix #202 to get "Not" and "PropertyIsNotEqualTo" filters work correctly
- Fix #218: Check privileges before exporting private data in MEF1 and MEF2
  export.
- Fix #219: Sample lacks download button
- Fix #224. For each outputFormat provided by WFS server add an OnlineSource?
  link to allow download of features.
- Fix #225: Add OpenSearch suggestion support.
- Fix #228: Add search criteria for revision, publication, creation date. 
- Fix #237: Replace Intermap with OpenLayers
- Fix #241: support for IPv6
- Fix #247: org.apache.lucene.store.AlreadyClosedException occurs for concurrent
  CSW getRecords requests
- Fix #248: CSW: Provide configurable limit on records examined for
  getcapabilities keywords and getdomain propertyname
- Fix #249: CSW / GetRecords / results_with_summary : empty results
- CSW: Implement reprojection of geometries in ogc:Filter to WGS84, add missing
  Equals filter and 
  Within filter does within, make sure filter-to-lucene.xsl doesn't try to handle
  ogc:Not over spatial expressions
- CSW and Search: Change IndexReader handling in LuceneSearcher and
  CatalogSearcher
- Z3950: Don't add collections from GeoNetwork Z server if it isn't enabled
- Include mime type in Lucene index.

--------------------------------------------------------------------------------
--- Changes
--------------------------------------------------------------------------------
- GAST changes to use sql data files instead of ddf files
- Maven migration
- English documentation ported into reStructuredText format.

