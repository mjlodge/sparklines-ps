A sparkline is a small line graph designed to be used in-line within
text to illustrate a time series; the concept was developed by data
presentation guru [Edward Tufte][]. Here’s an example:

**University of California 403(b) pension fund cumulative return Jan
1990-April 2004** ([original data][])

  ---------- -------- ------
  Equities   ![][]    267%
  Bonds      ![][1]   154%
  ---------- -------- ------

The idea is to show, using minimal space, how a value varies over time.
One advantage of sparklines’ compactness is that several can be used
together to allow at-a-glance comparison between a set of time series.
At Tufte’s web site there is a [longer description of sparklines][],
with further examples, from a sample chapter of Tufte’s book, *Beautiful
Evidence*. Sparklines are tangentially related to photography – they are
used alongside images as a graphical design element in qualitative and
quantitative analysis.<span id="more-18"></span>

Sparklines can be hard to produce. Most graphing packages are designed
to produce large graphs or charts, and it can be very hard to generate
the wide-but-thin lines for incorporation in documents. This was the
motivation for writing a Photoshop script that would automate the
production of sparklines. It works by reading a data series from a text
file and plotting a sparkline image as a Photoshop path, and then
stroking it with the pencil tool. This produces a bitmap image which can
then be cut-and-pasted into the target document. The user retains
control of the color and line style of the sparkline by setting the
Photoshop foreground color and pencil tool settings before running the
script.

Mac support and PS CS2 testing
------------------------------

Some Mac users had reported problems with the Sparkline script not being
able to open text data files. Thanks to the help of two kindly Mac
contributors, I found and fixed the problem. In addition, the script has
been tested on Photoshop CS2. All the changes are incorporated in
Version 2 of the script below.

Installing the sparkline script
-------------------------------

The code of the sparkline script for Adobe Photoshop CS/CS2/CS3 is
included below. While it will run on Mac or PC Photoshop, it does not
work on any earlier versions. You can also right click (Mac: Option
click) [here to download the script][]. Select “Save as…” from the menu
that pops up, and save it somewhere where you can find it on your
computer.

The script works on textual data files, where the first line is the name
of the quantity being charted, and the remainder of the lines are the
data values. To start you off, here’s a [sample data file for wind
speed][]. Using Microsoft Excel, it’s easy to create data files in this
format: put the legend in cell A1, then the data values in cells A2, A3
and so on, and then do File-\>Save As… and select “Text file” for the
output format.

To install the script, first locate Adobe Photoshop’s main directory on
your computer. On my (Windows) computer, it’s in C:Program
FilesAdobePhotoshop CS

On the PC, save the script as Sparklinev2.js in the directory
\<Photoshop dir\>PresetsScripts

On the Mac, save the script as Sparklinev2.js in the directory
\<Photoshop dir\>/Presets/Scripts

![][2]

Start Photoshop (or re-start it, if it was already running). You should
now see the Sparkline script on the File-\>Scripts menu:

![][3]

Using the script
================

First of all, select the foreground color and Pencil tool settings that
you want to use for the Sparkline. To select a foreground color, double
click on the foreground color swatch in the palette menu. To select the
pencil tool, right-click (Mac: option-click) on the palette menu as
shown:

![][4]

Then, set the pencil defaults to whatever you’d prefer using the tool
menu just below the Photoshop menu bar:

![][5]

  [Edward Tufte]: http://www.edwardtufte.com/
  [original data]: http://atyourservice.ucop.edu/employees/retirement/performance.html
  []: http://www.lodgephoto.com/images/Sparkline_uc_equity.gif
  [1]: http://www.lodgephoto.com/images/Sparkline_uc_bond.gif
  [longer description of sparklines]: http://www.edwardtufte.com/bboard/q-and-a-fetch-msg?msg_id=0001OR&topic_id=1&topic=
  [here to download the script]: http://www.lodgephoto.com/articles/sparklinesv2.js
  [sample data file for wind speed]: http://www.lodgephoto.com/articles/Example_data.txt
  [2]: http://www.lodgephoto.com/images/sparkline_script_location.gif
  [3]: http://www.lodgephoto.com/images/sparkline_file_menu.gif
  [4]: http://www.lodgephoto.com/images/sparkline_pencil_select.gif

