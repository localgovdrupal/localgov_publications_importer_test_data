# Publications Importer Test Data.

This is a collection of PDF files that are used to test 
localgovdrupal/localgov_publications_importer.

These files are placed in a separate project so the publications importer can be
installed without including the test data.

Files are stored under data, and then a directory named for the council that
provided the PDF.

Each file must be added to the manifest.json file in data, which provides file
metadata that's used for testing.

For example, each object in the JSON represents one file:
```JSON
{
  "filename": "southwark/HMO licensing conditions_1.pdf",
  "title": "Private Rented Sector Property Licensing",
  "page_count": 10,
  "links": {
    "2": [
      "<a href=\"https://www.gov.uk/guidance/domestic-private-rented-property-minimum-energy-efficiency-standard-landlord-guidance\">Energy \nPerformance Certificate (EPC) Rating of less than ‘E’</a>"
    ]
  }
}
```

* filename is the path to the file.
* title is the title stored in the file.
* page_count is how many pages the file has.
* links is optional. This stores an object mapping of page number to an array of links. The tests will ensure that each link in the array can be found in the content of the given page.
