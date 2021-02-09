# BOM-List with clickable Pictures
Electronic Schematics list with "Bill of Materials", with (manually) inserted pictures, made clickable
per CSS and JS-Script.

To create a BOM-List, each CAD-Program has its own Output-format, mostly (text-)CSS-format, although
programs also may output item-lists per HTML-File. Advantages of this format: Readable in each Browser
and able to use images in base64-data-format, this inserted in ONE-html-file only (not as usually spreaded
over the internet, inserting only as a Link pointing to image's URL-Place).

For this I used the mentioned ability (known from E-Mails in eml-file-format (MIME) to insert pictures
in HTML Base64-format **inside** the given html-file. This format uses 64 characters of the ASCII-table,
so beeing "typeable and printable" (also on screen), so beeing able to put directly into any html-file.

To create a HTML-(BOM-)file for that purpose, I modified a Eagle .ulp-script to generate a html-file
*with a table-cell at the begin of each row*, here named
"Eagle-BOM-List-Export to txt- css- or html-file.ulp"

Other BOM-(item-)files generated from other programs may also be used, beeing in html-format and
surrounding the inserted picture-data with a blank &lt;div&gt; box. 

To transform a picture into a base64-format it's possible to insert it via simply "drag and drop",
loading the html-file into a HTML-Editor, f.ex. using my online HTML-Editor @ www.nlohrmann.de
(see help-file there clicking "?" or pressing keyboards F1-key).

ATTENTION please: Internet-published images commonly are subjected to Owners Copyright! So use
them for privat purposes or create your own ones to spread – as I do, using f.ex. the two symbols
for R's and C's provided here in the html-file (inside the script) as example - they are free to use.

Using th html-file example it's possible to insert a picture into the &lt;div&gt;-box in each row,
resulting in a small visible symbol (placed at begin of each row).

To hold the item-list in a overviewable format, each line has a proposed height of 20px, so also
each picture has to be as small as 20px (height), therefore mostly not beeing possible to
recognize it in detail at first view...
Thus the ability to enlarge them via mouse-click and reduced them again with a second click.

Addition: image-data saved once, for repeated use within the file:
---------
If there are repeated items to be listed, as Resistors or Capacitors (as in electronic circuits
often are used), their picture in form of base64-data may be inserted only once as variable in the
html-file's js-header, but used repeated times in the html-body, so saving a lot of total (BOM-)file-space.

Yet not implemented in this last feature is a total automated process: The two (free) provided symbols
(for repeated use of R's and C's) inserted in the header serve as usable examples, but any additional
(repeated) items have to be inserted manually (f.ex. via text-editor), replacing all " in the 
&lt;image-data&gt; with \\" – as f.ex. commonly used alt="" has to be coded as alt\\"\\"
Also each image has to be surounded with a blank &lt;div&gt;...&lt;/div&gt;
Hint: For more detailed description see //outcommented lines inside the provided html and js-file examples.

For simple "Click over to enlarge" each image in a html-file:
-------------------------------------------------------------
If you don't have repeated images or items in a html-file it's also possible to use the provided
"Image-Resize.js" script, adding it into the header or other place inside the html-file.
This script simply makes all images of a html-file clickable to it's original size and resizing
them with a second click to the images given size.
In this example no other insertion is necessary.

The Principle:
--------------
The provided BOM html-file's css-layout adds a blue border on white background for all image &lt;div&gt;-cells
inside each listed item in a row, (inside in a table or as simple raw text-line), indicating that
"linked icons" inside this cells may be clicked, setting also a unique (small) hight for all
images of 20px.

After loading the html-file into a browser, the js-script adds a unique ID to each listed Image,
which later is used to identify the clicked one, "stealing" (deleting) them it's given height.
After a second click the originally given height of this image (here 20px) is reinstalled.
Hint: more detailed //commented-out descriptions at each end of js-line...
