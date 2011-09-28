
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<title>CutyCapt - A Qt WebKit Web Page Rendering Capture Utility</title>
<link rel="stylesheet" href="http://www.w3.org/StyleSheets/Core/Swiss" type="text/css" />
</head>
<body>
<h1>CutyCapt</h1>
<p>CutyCapt is a small cross-platform command-line utility to capture WebKit's rendering of a web page into a variety of vector and bitmap formats, including SVG, PDF, PS, PNG, JPEG, TIFF, GIF, and BMP. See <a href='http://iecapt.sourceforge.net/'>IECapt</a> for a similar tool based on Internet Explorer.</p>
<h2>Samples</h2>
<p>Here are some samples of CutyCapt generated renderings:</p>
<ul>
<li><a href='digg.png'>PNG Snapshot</a> of <a href='http://digg.com'>http://digg.com</a></li>
<li><a href='css-co-ltd.png'>PNG Snapshot</a> of <a href='http://csszengarden.com/?cssfile=/209/209.css&amp;page=0'>http://csszengarden.com/?cssfile=/209/209.css&amp;page=0</a></li>
<li><a href='silverlight.net.svgz'>SVG Snapshot</a> of <a href='http://silverlight.net'>http://silverlight.net</a></li>
<li><a href='silverlight.net.pdf'>PDF Snapshot</a> of <a href='http://silverlight.net'>http://silverlight.net</a></li>
</ul>
<h2>Status</h2>
<p>CutyCapt has a number of known quirks, most of which are caused by problems with Qt and/or WebKit. For example, while plugin support can be enabled, and the plugins execute properly, their rendering cannot be captured on some platforms. Use of with caution.</p>
<h2>Requirements</h2>
<p>CutyCapt depends on <a href='http://www.qtsoftware.com/'>Qt 4.4.0+</a>.</p>
<h2>Download</h2>
<ul>
<li><a href='http://downloads.sourceforge.net/cutycapt/CutyCapt-Win32-2010-04-26.zip'>CutyCapt-Win32-2010-04-26.zip (7MB, .exe for Win32 systems)</a></li>
<li><small><a href='http://downloads.sourceforge.net/cutycapt/CutyCapt-Win32-2008-06-11.zip'>CutyCapt-Win32-2008-06-11.zip (6MB, .exe for Win32 systems)</a></small></li>
</ul>
<h2>Source code</h2>
<p>The <a href='http://cutycapt.svn.sourceforge.net/viewvc/cutycapt/CutyCapt/'>source code is available in the SVN repositorty</a> (<a href='http://cutycapt.svn.sourceforge.net/viewvc/cutycapt/CutyCapt.tar.gz?view=tar'>download tarball</a>).</p>
<h2>Usage</h2>
<p>Open a command prompt and ask for help:</p>
<pre>
 % CutyCapt --help
 -----------------------------------------------------------------------------
 Usage: CutyCapt --url=http://www.example.org/ --out=localfile.png
 -----------------------------------------------------------------------------
  --help                         Print this help page and exit
  --url=&lt;url&gt;                    The URL to capture (http:...|file:...|...)
  --out=&lt;path&gt;                   The target file (.png|pdf|ps|svg|jpeg|...)
  --out-format=&lt;f&gt;               Like extension in --out, overrides heuristic
  --min-width=&lt;int&gt;              Minimal width for the image (default: 800)
  --min-height=&lt;int&gt;             Minimal height for the image (default: 600)
  --max-wait=&lt;ms&gt;                Don't wait more than (default: 90000, inf: 0)
  --delay=&lt;ms&gt;                   After successful load, wait (default: 0)
  --user-styles=&lt;url&gt;            Location of user style sheet, if any
  --header=&lt;name&gt;:&lt;value&gt;        request header; repeatable; some can't be set
  --method=&lt;get|post|put&gt;        Specifies the request method (default: get)
  --body-string=&lt;string&gt;         Unencoded request body (default: none)
  --body-base64=&lt;base64&gt;         Base64-encoded request body (default: none)
  --app-name=&lt;name&gt;              appName used in User-Agent; default is none
  --app-version=&lt;version&gt;        appVers used in User-Agent; default is none
  --user-agent=&lt;string&gt;          Override the User-Agent header Qt would set
  --javascript=&lt;on|off&gt;          JavaScript execution (default: on)
  --java=&lt;on|off&gt;                Java execution (default: unknown)
  --plugins=&lt;on|off&gt;             Plugin execution (default: unknown)
  --private-browsing=&lt;on|off&gt;    Private browsing (default: unknown)
  --auto-load-images=&lt;on|off&gt;    Automatic image loading (default: on)
  --js-can-open-windows=&lt;on|off&gt; Script can open windows? (default: unknown)
  --js-can-access-clipboard=&lt;on|off&gt; Script clipboard privs (default: unknown)
  --print-backgrounds=&lt;on|off&gt;   Backgrounds in PDF/PS output (default: off)
 -----------------------------------------------------------------------------
  &lt;f&gt; is svg,ps,pdf,itext,html,rtree,png,jpeg,mng,tiff,gif,bmp,ppm,xbm,xpm
 -----------------------------------------------------------------------------
 <a href='/'>http://cutycapt.sf.net</a> - (c) 2003-2010 <a href='http://bjoern.hoehrmann.de'>Bjoern Hoehrmann</a> - <a href='mailto:bjoern@hoehrmann.de'>bjoern@hoehrmann.de</a>
</pre>
<h2>Build Instructions</h2>
<p>If your system is set up to compile Qt applications, building CutyCapt should be a simple matter of checking out the source code and running <code>qmake</code> and your version of <code>make</code>. As an example, if you are running Ubuntu Hardy Heron and have configured the system to use packages from <code>hardy-backports</code>, the following should do:</p>
<pre>
  % sudo apt-get install subversion libqt4-webkit libqt4-dev g++
  % svn co https://cutycapt.svn.sourceforge.net/svnroot/cutycapt
  % cd cutycapt/CutyCapt
  % qmake
  % make
  % ./CutyCapt --url=http://www.example.org --out=example.png
</pre>

<h2>Using CutyCapt without X server</h2>
<p>You cannot use CutyCapt without an X server, but you can use e.g. Xvfb as light-weight server if you are not running an interactive graphical desktop environment. For example, you could use:</p>
<pre>
  % xvfb-run --server-args="-screen 0, 1024x768x24" ./CutyCapt --url=... --out=...
</pre>

<h2>Author</h2>
<address>
<p><a href='http://bjoern.hoehrmann.de'>Bj&ouml;rn H&ouml;hrmann</a>&nbsp;<a href='mailto:bjoern@hoehrmann.de'>bjoern@hoehrmann.de</a> (<a href='http://sourceforge.net/donate/index.php?user_id=188003'>Donate via SourceForge</a>, <a href='https://www.paypal.com/cgi-bin/webscr?cmd=_xclick&amp;business=bjoern@hoehrmann.de&amp;item_name=Support+Bjoern+Hoehrmann'>PayPal</a>)</p>
</address>
<hr />
<p style='text-align:center'><a href='http://sourceforge.net/project/project_donations.php?group_id=230656'><img src='http://images.sourceforge.net/images/project-support.jpg' alt='Support this project' border="0" width="88" height='32' /></a> <a href="http://sourceforge.net"><img src="http://sourceforge.net/sflogo.php?group_id=230656&amp;type=1" width="88" height="31" border="0" alt="SourceForge.net Logo" /></a> <a href="http://validator.w3.org/check?uri=http://cutycapt.sourceforge.net"><img src="http://www.w3.org/Icons/valid-xhtml10" height="31" border="0" width="88" alt="" /></a></p>
</body>
</html>