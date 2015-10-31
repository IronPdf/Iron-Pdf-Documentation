=================
IronPdf.HtmlToPdf
=================

HtmlToPdf is your go-to class for creating PDFs in .Net

It can work from HTMl string or fetch URL (with all of their supporting assets). 

A custom System.Net.WebCient can optionally be assign to manage requests to render webpages with special security provisions.

Examples:
^^^^^^^^^ 

This should help you get started.  IntelliSense should take it from there! 

.. code-block:: c#

	using IronPdf;

	//..

	HtmlToPdf HtmlToPdf = new IronPdf.HtmlToPdf();
	HtmlToPdf.PrintOptions.EnableJavaScript = true;
	// Many more PrintOptions available - check IntelliSense
	
	HtmlToPdf.RenderHtmlAsPdf("<p>html</p>").SaveAs("Path/FileName.Pdf");
	//or
 	HtmlToPdf.RenderUrlAsPdf("http://ironpdf.com").SaveAs("FileName.Pdf");
	//or


	HtmlToPdf.RenderUrlAsPdf(new Uri("http://ironpdf.com")).SaveAs("FileName.Pdf");


You can also save the result as a Stream or Byte array for advanced usage.  *See IronPdf.PdfResource*.

*******************************************
Full Object Reference for IronPdf.HtmlToPdf
*******************************************


.. doxygenclass:: IronPdf::HtmlToPdf
   :members: