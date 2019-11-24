# The Library Metadata Visualizations Project


#### Introduction

In 1968, at the Library of Congress, Henriette Avram created Machine Readable Cataloging, a mathematical code that translated bibliographic records stored in physical card catalogs to a computational format that could be stored in a digital database.  Libraries around the world adopted the MARC format, including the University of Edinburgh Library (the Library).   Since then, when the Library acquires new items, cataloguers record the items in a database using MARC (specifically MARC 21, the latest generation of MARC1).  MARC enables the Library’s patrons to browse books online.  When searching on the Library’s discovery service, DiscoverEd, the service compares the search query to MARC data fields in the Library catalog to determine which results to display.

The value of MARC extends beyond search queries, though.  MARC records as a whole give insight on University cataloguers’ interpretation of books and on the Library’s overall understanding of its patrons’ interests.  The Library exists to support the reading and research of its patrons, so the University community shapes the Library’s acquisitions and thus the contents of its catalog.  Taken individually, in addition to data about the title, author, and publication of books, a MARC record contains terms with which cataloguers expect patrons to search.  Libraries around the world follow similar cataloguing practices, building catalogs with MARC data that give insight on the communities they serve. ,   However, existing research on MARC data focuses on the cataloging practices, investigating how the quality of MARC data could be improved.4 The Library Metadata Visualizations Project, by contrast, investigates what insights MARC data could provide for libraries beyond cataloging.

We ask, if a library downloads all its collections data from OCLC, how can one analyze and visualize the data?  Although the University of Edinburgh alone provided the Project’s data, thousands of libraries store their catalogs in the same format.  We hope the Project inspires collaboration between data visualization designers and library staff worldwide, prompting libraries to treat their catalog’s metadata as data, exploring the insights MARC data can provide on a library, such as the historical growth of its collection, or the extent to which the collection reflects the library’s stated acquisition strategy.


#### Approach

This project consisted of four steps: data translation, data cleaning, data analysis and data visualization.  

(1)	Data Translation: The University Library’s MARC data was downloaded from OCLC for its print books (the “physical collection”).  To visualize the data, the file needed to be translated from MARC format to CSV format.  While MarcEdit (an open-source software)  could separate the downloaded file into several files and translate one to CSV, the software returned an error when batch translating all the files.  Consequently, Python scripts were written to read the downloaded file and translate the MARC data to CSV (comma-separated values) format.

(2)	Data Cleaning: Python and Pandas  provided the means to clean the Library’s data.  After translating the data to CSV format, we wrote Python functions to standardize the format of publication years, publication places, and subject classifications.

(3)	Data Analysis: To analyze the clean, CSV-formatted data, we considered temporal, geographic and classification dimensions.  We counted the number of books published per year and per century; we counted the number of books published per city, per country and per continent; and we counted the number of books catalogued in the main classes of the Library of Congress Classification  and Dewey Decimal Classification  schemes.

(4)	Data Visualization: To support further analysis and disseminate the project findings, we created a data visualization booklet.  The booklet includes one infographic and five data visualizations summarizing the results of our data analysis.  We created the final visualizations with Python, Microsoft Excel and Adobe InDesign.


#### Results

Analysis of the Library’s MARC data shows that the bibliographic records of library books have data entries suitable for visualization.  Lack of standardization in data entries renders visualization difficult without extensive data cleaning.  During this project, books’ publications dates were standardized to four-digit years (dates were entered in various formats including “20th century,” “1920-30”, and “1830-5”).  Subject classification data entries did not require standardization.  Efforts were made to standardize publication places, matching cities, countries and regions in the MARC data to countries in Natural Earth9 data.  Due to the lack of standardization in naming places, 71.9% (19,207 out of 26,711) of publication places in the MARC data have no known country.  Applying a translator to the MARC data could reduce this percentage; the MARC data includes publication places written in languages other than English which means those places cannot be found in the Natural Earth dataset.


#### Next Steps

Future work could build on this project through further data cleaning, visualization development, and replication with new datasets.  Due to the time constraints of this project, the data visualizations exist in static form only.  This project’s visualizations could be made interactive with a D3.js.  Additionally MARC data beyond the publication dates and subject classifications could be used for new visualizations.  For example, MARC data on publication places could be combined with geographic data from Natural Earth  and MapShaper  to create a map of where books were published.  The University of Edinburgh’s Library could look to data visualization designers work with Library of Congress data for additional ideas (for example, Birthy-Deathy  and Southern Mosaic ).
