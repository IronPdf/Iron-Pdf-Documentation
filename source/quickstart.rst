==========
QuickStart
==========

********************************************************
Developer Notice: `The Dot Net PDF QuickStart Guide Has Moved <https://ironpdf.com/docs/>`_.   
********************************************************


Get IronPdf Installed
----------------------------------------------------

**Using Nuget Package manager in Visual Studio**

.. code-block:: bash

    PM> Install-Package IronPdf

**Or Download IronPdf as DLL**

* Get http://localhost/iron/packages/IronPdf.zip 
* Add IronPdf.dll  to your project as a reference or to the GAC.  
* *Lazy option - just copy the dll into your /Bin folder in .net web applications.*

Basic Usage
-------------

HTML String to Pdf
^^^^^^^^^^^^^^^^^^

.. code-block:: csharp

	using IronPdf;

	HtmlToPdf HtmlToPdf = new IronPdf.HtmlToPdf();
	HtmlToPdf.RenderHtmlAsPdf("<p>html</p>"").SaveAs(@"Path\File.Pdf");
	

Url to Pdf
^^^^^^^^^^^
.. code-block:: csharp

	using IronPdf;

	HtmlToPdf HtmlToPdf = new IronPdf.HtmlToPdf();
	HtmlToPdf.RenderUrlAsPdf(@“http://myurl.com").SaveAs(@"Path\File.Pdf");


Advanced usage - you can also pass a System.Net.WebClient to RenderUrlAsPdf. 

.. code-block:: csharp

         //...
         HtmlToPdf.RenderUrlAsPdf("http://ironpdf.com", myWebClient ).SaveAs("File.Pdf");

 This allows you to set login credentials, proxy settings, special headers, cookies - to log  in to protected / secure web pages.


Pdf Settings
^^^^^^^^^^^^

.. code-block:: csharp

		using IronPdf;

		HtmlToPdf HtmlToPdf = new IronPdf.HtmlToPdf();

		HtmlToPdf.PrintOptions.Dpi = 300;
		HtmlToPdf.PrintOptions.PDFPaperSize = System.Drawing.PaperKind.A4;
		HtmlToPdf.PrintOptions.EnableJavaScript = true;
		HtmlToPdf.PrintOptions.AllowScreenCss = false;
		HtmlToPdf.PrintOptions.SetHeaderText = "{page} of {total-pages}";
		HtmlToPdf.PrintOptions.GrayScale = true;

You can also create a reusable instance of IronPDF.PdfPrintOptions and use it in the IronPdf.HtmlToPdf constructor.  




AspxToPdf
^^^^^^^^^^^^

Changes any ASPX web page to automatically render as a Pdf document instead of html.   

.. code-block:: c#

                  using IronPdf;

		  private void Form1_Load(object sender, EventArgs e)
		  {
		   //..		
		  AspxToPdf.RenderThisPageAsPDF();      
		  }

**AspxToPdf with Advanced Settings**


.. code-block:: c#

      IronPdf.AspxToPdf.RenderThisPageAsPDF(AspxToPdf.FileBehaviour.Attachment, "MyPdfDownload.pdf", new PdfPrintOptions(){ Dpi = 300});


Pdf Outputs
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

HtmlToPdf.RenderUrlAsPdf and  HtmlToPdf.RenderHtmlAsPdf return an instance of the
IronPdf.PdfResource class.

In the above examples, we directly save each PDF as a file.

It is also possible to get the Pdf document as a System.IO.MemoryStream or a byte array (byte[])the *Stream* and *BinaryData* properties of PdfResource respectively.

.. code-block:: c#

	using IronPdf;
	HtmlToPdf HtmlToPdf = new IronPdf.HtmlToPdf();
	//..
	System.IO.MemoryStream stream = HtmlToPdf.RenderHtmlAsPdf("<p>html</p>).Stream;
	//or
	byte[] data = HtmlToPdf.RenderHtmlAsPdf("<p>html</p>"").BinaryData;