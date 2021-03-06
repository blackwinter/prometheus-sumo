
# prometheus – The Distributed Digital Image Archive for Research and Studies

## Introduction

prometheus ({http://www.prometheus-bildarchiv.de www.prometheus-bildarchiv.de})
is a digital image archive for Art and Cultural Sciences. prometheus enables the
convenient search for images on a common user interface within different image 
archives, variable databases from institutes, research facilities and museums.

## The image archive

prometheus is a digital image archive for Art and Cultural Sciences. prometheus enables the convenient search for images on a common user interface within different image archives, variable databases from institutes, research facilities and museums.

<dl>
  <dt>Searching – Search in multiple image databases within one surface</dt>
  <dd>Currently you are able to search in 64 art historian, design, architectural, theological, historian and archaeological image databases with 875,594 images in total. The prometheus archive offers you a simple search that searches in all fields for your query terms or an advanced search that allows you to combine your search criteria in different ways or to pick certain databases for a more selective search.</dd>

  <dt>Collecting – Assemble your topical images in one place</dt>
  <dd>You can store your images which you need to prepare your courses, presentations or research into an image collection. The image collection can be expanded at all times with new images and your access is independent from your location. Additional information to characterize your image collection (description, keywords) or information concerning research literature or relevant web links can be added. Above all you have the possibility to share your collection with all users or only with single users so that they are able to have a closer look at your collection or even to collaborate with you.</dd>

  <dt>Presenting – Present your assembled images location-independently</dt>
  <dd>You can integrate the images which you found or assembled in an image collection in a presentation. The layout of the slides is flexible, the presentation can be started easily in any browser. You are also allowed to download the images to integrate them in your local presentation program.</dd>

  <dt>Publishing – Inform yourself about copyrights and publish images</dt>
  <dd>Next to any image you will find a link which leads you to the copyright information of the particular image. There you can research what is necessary to obtain the consent of the copyright-holder. In some cases there will be the opportunity to obtain the permission for publication directly through prometheus. In order to use the images for research and education, prometheus cooperates with the VG Bild-Kunst which allows both access to the images of the different databases through prometheus and the utilization of the images for research and education.</dd>

  <dt>Researching – Search, collect, annotate, connect images and mark motives</dt>
  <dd>In every area you will find tools that will help to alleviate your work and research: e.g. selective search with the aid of choosing certain databases and combined search fields, the structured and annotated image collection or the research work which you approved for collaboration. In the near future, prometheus will also integrate a tool that will allow the direct research on images through connections and image annotations within a research group.</dd>
</dl>

## History

{http://www.prometheus-bildarchiv.de prometheus – The Distributed Digital Image
Archive for Research and Studies} started on April 1, 2001 as a cooperative
project in Germany. Within the frame work of New Media in Education, prometheus
was supported by the {http://www.bmbf.de Federal Ministry for Education and
Research} (bmb+f) with a total amount of 1.8 Mio. €. The project’s executing
organization “New Media in Education” was associated with the
{http://www.dlr.de German Institute for Aerospace industry} (DLR).

During the 3 years of the project’s development and implementation, the project team consisted of 9 project managers, and a total of 50 staff members and assistants from 4 universities and 8 institutes. From the very beginning of the project, the established objective was to encourage close interdisciplinary interaction to enable all staff members to gain an understanding of varied subject areas, and to participate in decision making. 

The major components of the project work was distributed between the universities and institutes as follows:

* {http://www.hs-anhalt.de University of Anhalt} (FH)
  * {http://www.inf.hs-anhalt.de Computer Sciences} (Köthen): Programming of the research modules (TimeLine) and the off-line work folder
  * {http://www.design.hs-anhalt.de Design} (Dessau): Layout and conception of the image archive (research, work folders, navigation) and the home page; development of the educational program

* {http://www.hu-berlin.de Humboldt University Berlin}
  * Fine Arts: Database imago_diathek, database of the virtual art, development of the educational program

* {http://www.uni-giessen.de Justus-Liebig University Giessen}
  * Professorship for Archeology: Database EikonLine, development of the educational program
  * Professorships for Art history: Database digital Diathek, database DigiDiathek, coordination of the associated partners

* {http://www.uni-koeln.de University of Cologne}
  * Institute of Art History: Project management and project coordination, database DaDa Web
  * Institute for Data Processing of Cultural Studies: Technology of the central server, technical realization of the design and organization of the image archive
  * Pedagogical Department: Development of the educational program, evaluation.

## Software Stack

<dl>

  <dt>pandora</dt>
    <dd>{http://prometheus.uni-koeln.de/pandora/en/about pandora} (The prometheus digital image archive software) is the successor to kleio as the driving force behind the prometheus image archive. It's being developed since late fall of 2006, on top of the {http://rubyonrails.org Ruby on Rails} framework. pandora is Free Software, released under the terms of the {http://www.gnu.org/licenses/#AGPL GNU Affero General Public License}. </dd>

  <dt>Meta-Image</dt>
    <dd>{http://www2.leuphana.de/meta-image Meta-Image} fügt bestehende Komponenten zu einer virtuellen Arbeits- und Forschungsumgebung für den Bilddiskurs in der Kunstgeschichte zusammen. Meta-Image verbindet dazu die digitalen Bildbestände des Verbundes kunsthistorischer Bilddatenbanken prometheus und ein auf die Verlinkung und Anreicherung von Bildcorpora spezialisiertes Bild-Beschreibungs-Tool mit dem Ziel einer integrativen Cyberinfrastructure für die kunsthistorische Forschungsarbeit direkt am Bild. Meta-Image reichert die formellen dokumentarisch-archivarischen Informationen und Sacherschließungen des Repositorys um die Ergebnisse der informellen Forschungstätigkeiten der Fachcommunity an, wobei Ursprung und Kontext der Meta-Informationen stets transparent bleiben.</dd>

  <dt>HyperImage</dt>
    <dd>Mit {http://www.uni-lueneburg.de/hyperimage/hyperimage HyperImage} können beliebig viele Details innerhalb eines Bildes präzise markiert und beschrieben sowie Annotationen des Corpus untereinander verlinkt und über Indizes erschlossen werden. Zwischenergebnisse wie endgültige Fassungen lassen sich jederzeit als hypermediale online- oder offline-Publikation erstellen. Verschiedene einzeln eingeführte und erprobte Verfahren und Datenrepositorien sind in HyperImage zu einer einzeln oder gemeinschaftlich nutzbaren Forschungs- und Publikationsumgebung zusammengeführt.</dd>
</dl>

Besides the above mentioned front-end applications, there also exists a larger
collection of support tools (applications, libraries, modules, etc.) working in
background:

<dl>
  <dt>JekyllCommander</dt>
    <dd>{https://github.com/prometheus-ev/JekyllCommander JekyllCommander} is a Sinatra based web application, to give non-technical users the ability to maintain a complex {http://jekyllrb.com Jekyll} website, including git version control, without any scary terminal experiences.</dd>

  <dt>apache_secure_download</dt>
    <dd>Apache module providing secure downloading functionality, just like Mongrel Secure Download does for mongrel.</dd>

  <dt>wadl</dt>
    <dd>A Ruby client for the Web Application Description Language. It hides the details of HTTP communication between a web service client and a REST or HTTP+POX web service.</dd>
</dl>

