Sparklines-ps is a Photoshop script to draw Sparklines, written in JavaScript
for PC and Mac Photoshop CS and newer.

A sparkline is a small line graph designed to be used in-line within
text to illustrate a time series; the concept was developed by data
presentation guru [Edward Tufte](http://www.edwardtufte.com/). Here’s an
example:

**University of California 403(b) pension fund cumulative return Jan
1990-April 2004** ([original
data](http://atyourservice.ucop.edu/employees/retirement/performance.html))

  ---------- --------------------------------------------------------------- ------
  Equities   ![](http://www.lodgephoto.com/images/Sparkline_uc_equity.gif)   267%
  Bonds      ![](http://www.lodgephoto.com/images/Sparkline_uc_bond.gif)     154%
  ---------- --------------------------------------------------------------- ------

The idea is to show, using minimal space, how a value varies over time.
One advantage of sparklines’ compactness is that several can be used
together to allow at-a-glance comparison between a set of time series.
At Tufte’s web site there is a [longer description of
sparklines](http://www.edwardtufte.com/bboard/q-and-a-fetch-msg?msg_id=0001OR&topic_id=1&topic=),
with further examples, from a sample chapter of Tufte’s book, *Beautiful
Evidence*.

Sparklines were hard to produce when this script was first written, though
support has improved as Sparklines have become mainstream -- e.g. Excel
now has a Sparkline plotting capability.
Most graphing packages are designed
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

Licensing
---------
Sparkline-ps is open source and licensed under the GNU GPLv3. That means
it is free to use
without royalty or fee, and may not be incorporated into a commercial product,
and all derivative works are also covered by GPLv3. For more information on
GPLv3, see the Free Software Foundation website: (http://gplv3.fsf.org/)

The full licensng text is in COPYING.md


Mac support and PS CS6 testing
------------------------------

Some Mac users had reported problems with the Sparkline script not being
able to open text data files. Thanks to the help of two kindly Mac
contributors, I found and fixed the problem. In addition, the script has
been tested on Photoshop CS2-CS6. All the changes are incorporated in
Version 2 of the script.

Installing the sparkline script
-------------------------------

The code will run on Mac or PC Photoshop CS or later; it does not
work on any earlier versions.

The script works on textual data files, where the first line is the name
of the quantity being charted, and the remainder of the lines are the
data values. To start you off, here’s a [sample data file for wind
speed](http://www.lodgephoto.com/articles/Example_data.txt). Using
Microsoft Excel, it’s easy to create data files in this format: put the
legend in cell A1, then the data values in cells A2, A3 and so on, and
then do File-\>Save As… and select “Text file” for the output format.

To install the script, first locate Adobe Photoshop’s main directory on
your computer. On my (Windows) computer, it’s in C:\\Program
Files\\Adobe\\Photoshop CS6

On the PC, save the script as Sparklinev2.js in the directory
\<Photoshop dir\>Presets\\Scripts

On the Mac, save the script as Sparklinev2.js in the directory
\<Photoshop dir\>/Presets/Scripts

![](http://www.lodgephoto.com/images/sparkline_script_location.gif)

Start Photoshop (or re-start it, if it was already running). You should
now see the Sparkline script on the File-\>Scripts menu:

![](http://www.lodgephoto.com/images/sparkline_file_menu.gif)

Using the script
================

First of all, select the foreground color and Pencil tool settings that
you want to use for the Sparkline. To select a foreground color, double
click on the foreground color swatch in the palette menu. To select the
pencil tool, right-click (Mac: option-click) on the palette menu as
shown:

![](http://www.lodgephoto.com/images/sparkline_pencil_select.gif)

Then, set the pencil defaults to whatever you’d prefer using the tool
menu just below the Photoshop menu bar:

![](http://www.lodgephoto.com/images/sparkline_pencil_params.gif)

Click File-\>Scripts-\>Sparkline (as shown in the screen shot above) to
start the script. You will be promoted to locate the file containing the
sparkline data:

![](http://www.lodgephoto.com/images/sparkline_open_data.gif)

Click “Open”; the script will open the file and then prompt you for the
height of the sparkline, in pixels. The default height is 50 pixels,
which is 50 points (0.7″) high on a typical 72dpi computer screen, and
12 points high when printed on paper at 300dpi (you can change the
default height by editing the script).

The script will then ask if you want to automatically scale the
sparkline to the document height. If you select Yes, then the script
uses the minimum and maximum values present in the data file to scale
the Y axis such that the minimum value is plotted at the bottom of the
document, and the maximum value is plotted at the top, like this (a
border has been added to make it easier to see the effect):

![](http://www.lodgephoto.com/images/sparkline_auto.gif)

If you select No, then the script will prompt you for the Y intercept
(the data value that will be plotted at the bottom of the document) and
the maximum Y value (which will be plotted at the top of the document).
For example, using a Y intercept of 0 and a max Y value of 50, the same
data would be plotted as follows (again, border added for clarity):

![](http://www.lodgephoto.com/images/sparkline_0_50.gif)

Finally, the script asks for the X axis pixel spacing between points.
The default setting of 1 plots each point of the sparkline immediately
adjacent (one pixel away) from the previous point. To make the sparkline
shorter, use a value less than 1. To make it longer, use a value greater
than one. For example:

X axis pixel spacing of 0.3:
![](http://www.lodgephoto.com/images/sparkline_x_03.gif)

X axis pixel spacing of 0.5:
![](http://www.lodgephoto.com/images/sparkline_x_05.gif)

Advanced topics: Use of time travel
-----------------------------------

Because the script creates a regular Photoshop document complete with
history, you can use the Photoshop history palette to “go back in time”
and change the way that the path is stroked. For example, to use a Brush
stroke rather than a Pencil stroke, you’d go back in the document
history to the point where the path has been saved, but before it has
been stroked. Then stroke it with the Brush, rather than the Pencil.

First of all, open both the History and Paths palettes. Then, use the
History palette to go back to the document state before the stroke
occurred:

![](http://www.lodgephoto.com/images/sparkline_history.gif)

Then, right click (Mac: option-click) on the Sparkline path in the
channels palette. Select “Stroke path…” from the pop-up menu.

The following dialog will appear, and you can elect to stroke the path
using the Brush, or indeed any of the other Photoshop tools:

![](http://www.lodgephoto.com/images/sparkline_stroke.gif)
