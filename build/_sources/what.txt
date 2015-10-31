===================
What is IronPdf ?
===================


IronPDF is a commercial Grade PDF Generation library for the .Net platform, written in C#.

The key concept is to avoid time-consuming PDF generation APIs by rendering PDFs from HTML, CSS, Images and JavaScript.

IronPDF's core features are:

* Generating PDF documents from HTML as a string
* Generating PDF documents from Urls
* Rendering ASPX webforms as PDF documents on-the-fly

The base requirements are .Net framework 4.0 on the windows platform.

It works equally well in Forms Applications, Server Applications and Services, Web Applications, Secure Intranets, Console Apps, WPF Apps and MVC patterned websites.

Read more at http://ironpdf.com


Hello World
------------------------

 **NuGet Installer**

 
.. code-block:: bash

     PM> Install-Package IronPdf

  **1 Line Hello World**
 

.. code-block:: c#

     new IronPdf.HtmlToPdf().RenderHtmlAsPdf(@“<p>hello world</p>“).SaveAs(“test.pdf”);



Features
------------------------

  IronPDF doesn't try to render HTML.  It actually print up an instance of a real standard compliant web browser behind the scenes (without any additional software needing to be installed).  

The HTML gets rendered with complete accuracy - and in a vector format suitable for the highest standards of commercial printing.

* No more convoluted PDF APIs.  
* Just make it look right in HTML - and then use IronPDF output your PDF as a file, stream or byte array.
* Full IntelliSense documentation which even includes embedded code examples.
* No External Dependancies.  Just 1 Dll.
* Deploy almost anywhere on a windows environment without special permissions. No EXE files, Msi or Native Dlls to install.  *No COM objects or Interop hell.*
* No special security permissions required.
* CSS3, HTML5 and Javascript compliance.
* Real, standards compliant HTML rendering and pixel perfect PDF conversion with vector and font support.
* Javascript and AJAX content can also be rendered into your PDFs.
* High Performance - PDF from HTML rendering takes about 125ms.  Remote HTTP requests will obviously take longer.  *First usage take extra overhead as the browser virtual instance is initiated. Thereafter it is available almost instantly throughout your application process.*  
* Low memory footprint about under 10MB memory. Our smart Garbage Collection This allows for instance like performance from static methods.  Dynamically makes smart choices to minimize impact on CPU and Free Ram.  
* PDF rendering can be achieved in parallel using threads or Parallel.ForEach. This makes  batch conversions even faster.
* HTML forms fields can automagically become editable areas in your PDFs 
* Working code Examples on GitHub
* Customizable WebClient functionally allows Printing of HTML Documents even behind logins or on secure intranets.
* We cant to get better every day. If this documentation or software lacks in any way, please post a GitHub issue and we will respond.