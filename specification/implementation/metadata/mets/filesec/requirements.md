| ID | Name & Location | Description & usage | Cardinality & Level |
| -- | --------------- | ------------------- | ------------------- |
| <a name="CSIP58"></a>**CSIP58** | **File section**<br/>`fileSec` | When the section is used only one file section (fileSec) element is present.<br/>It is possible to transfer just descriptive metadata and/or adminsitrative metadata without files placed in this section. | **0..1**<br/>SHOULD |
| <a name="CSIP59"></a>**CSIP59** | **File section identfier**<br/>`fileSec/@ID` | An identifier for the file section used for referencing inside the package. It must be unique within the package.<br/>The ID must follow the rules for xml:id described in the chapter of the textual description of CS IP named "General requirements for the use of metadata" | **1..1**<br/>MUST |
| <a name="CSIP60"></a>**CSIP60** | **File grouping**<br/>`fileSec/fileGrp` | There are one or more file group (fileGrp) elements present grouping the transfered files in the main catagorization of; Documentation, Schemas and Representations.<br/>In one or more file groups with the catagorization of "Documentation" all documetation pertaining to the transfered information is present.<br/>In one or more file groups with the catagorization of "Schemas" all XML-schemas pertaining to the transfered XML documents is present.<br/>In one or more file groups with the catagorization of "Representations" the data being transfered is present or in one file group the data for each representation is present.<br/>To make the catagorization easier the different files being transfered should be placed in folders with names folowing the catagorization | **1..n**<br/>MUST |
| <a name="CSIP61"></a>**CSIP61** | **Reference to administrative metadata**<br/>`fileSec/fileGrp/@ADMID` | If administrative metadata is has been provided on the file group (fileGrp) level this attribute points to the correct administrative metadata section. | **0..1**<br/>MAY |
| <a name="CSIP62"></a>**CSIP62** | **Specific content type**<br/>`mets/@csip:CONTENTINFORMATIONTYPE` | An added attribute which describes the specific content information type specification used for the transferred content. The attribute is mandatory to use when the file group catagorization is Representations. The vocabulary is going to evolve under the care of the DILCIS Board as additional content information type specifications are developed. | **1..1**<br/>SHOULD |
| <a name="CSIP63"></a>**CSIP63** | **Other specific content type**<br/>`mets/@csip:OTHERCONTENTINFORMATIONTYPE` | When the @csip:CONTENTINFORMATIONTYPE uses the value "OTHER" the @csip:OTHERCONTENTINFORMATIONTYPE must describe the content. | **0..1**<br/>MAY |
| <a name="CSIP64"></a>**CSIP64** | **Description of the use of the file group**<br/>`fileSec/fileGrp/@USE` | The value in the @USE is the name of the whole folder structure to the data, e.g "Documentation", "Schemas", "Representations/preingest" or "Representations/submission/data" | **1..1**<br/>MUST |
| <a name="CSIP65"></a>**CSIP65** | **File group identifier**<br/>`fileSec/fileGrp/@ID` | An identifier for the file group used for referencing inside the package. It must be unique within the package.<br/>The ID must follow the rules for xml:id described in the chapter of the textual description of CS IP named "General requirements for the use of metadata" | **1..1**<br/>MUST |
| <a name="CSIP66"></a>**CSIP66** | **File**<br/>`fileSec/fileGrp/file` | The lowest level file group (fileGrp) contains the file elements which describe the transferred file objects.<br/>When the file element is categorised as "Representations" each representation file group contains one file which is the reference to the METS document describing the representation | **1..1**<br/>MUST |
| <a name="CSIP67"></a>**CSIP67** | **File identifier**<br/>`fileSec/fileGrp/file/@ID` | A unique identifier for this file across the package.<br/>The ID must follow the rules for xml:id described in the chapter of the textual description of CS IP named "General requirements for the use of metadata" | **1..1**<br/>MUST |
| <a name="CSIP68"></a>**CSIP68** | **File mimetype**<br/>`fileSec/fileGrp/file/@MIMETYPE` | The IANA mime type for the linked file. | **1..1**<br/>MUST |
| <a name="CSIP69"></a>**CSIP69** | **File size**<br/>`fileSec/fileGrp/file/@SIZE` | Size of the linked file in bytes. | **1..1**<br/>MUST |
| <a name="CSIP70"></a>**CSIP70** | **File creation date**<br/>`fileSec/fileGrp/file/@CREATED` | Date the linked file was created. | **1..1**<br/>MUST |
| <a name="CSIP71"></a>**CSIP71** | **File checksum**<br/> | The checksum of the linked file. | **1..1**<br/>MUST |
| <a name="CSIP72"></a>**CSIP72** | **File checksum type**<br/>`fileSec/fileGrp/file/@CHECKSUMTYPE` | The type of checksum following the value list in the standard which used for the linked file. | **1..1**<br/>MUST |
| <a name="CSIP73"></a>**CSIP73** | **File original identfication**<br/>`fileSec/fileGrp/file/@OWNERID` | If an original ID for the file has been given by the owner it can be saved in this attribute. | **0..1**<br/>MAY |
| <a name="CSIP74"></a>**CSIP74** | **File reference to administrative metadata**<br/>`fileSec/fileGrp/file/@ADMID` | If administrative metadata has been described for the file this attribute points to the file's administrative metadata. | **0..1**<br/>MAY |
| <a name="CSIP75"></a>**CSIP75** | **File reference to descriptive metadata**<br/>`fileSec/fileGrp/file/@DMDID` | If descriptive metadata has been described per file this attribute points to the file's descriptive metadata. | **0..1**<br/>MAY |
| <a name="CSIP76"></a>**CSIP76** | **File locator reference**<br/>`fileSec/fileGrp/file/FLocat` | The location of each external file must be defined by the file location (FLocat) element using the same rules as for referencing metadata files. All references to files should be made using the XLink href attribute and the file protocol using the relative location of the file. | **1..1**<br/>MUST |
| <a name="CSIP77"></a>**CSIP77** | **Type of locator**<br/>`fileSec/fileGrp/file/FLocat/@LOCTYPE` | The locator type is always used with the value "URL" from the vocabulary in the attribute. | **1..1**<br/>MUST |
| <a name="CSIP78"></a>**CSIP78** | **Type of link**<br/>`fileSec/fileGrp/file/FLocat/@xlink:type` | Attribute used with the value “simple”. Value list is maintained by the xlink standard | **1..1**<br/>MUST |
| <a name="CSIP79"></a>**CSIP79** | **Resource location**<br/>`fileSec/fileGrp/file/FLocat/@xlink:href` | The actual location of the resource. We  recommend recording a URL type filepath within this attribute. | **1..1**<br/>MUST |