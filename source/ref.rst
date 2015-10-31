==================================
Object Reference
==================================



*******************************************
IronPdf.HtmlToPdf
*******************************************

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


Full Object Reference for IronPdf.HtmlToPdf
============================================


.. doxygenclass:: IronPdf::HtmlToPdf
   :members:


**********************************
IronPdf.AspxToPdf
**********************************
AspxToPdf is a static class used to turn any ASPX web form into a PDF.  The look and feel remain the same - but the output becomes a PDF.

This is simply achieved by adding AspxToPdf in your ASPX page code-behind.   *Normally this is a file named like Default.aspx.cs*.

Just call **IronPdf.AspxToPdf.RenderThisPageAsPdf()** in your of your ASPX Form onLoad event.  


Examples:
^^^^^^^^^ 

Basic Example
****************

.. code-block:: c#

     private void Form1_Load(object sender, EventArgs e)
          {
               //..		
               IronPdf.AspxToPdf.RenderThisPageAsPDF();      
           }


Advanced Example
*****************
     using IronPdf;

     private void Form1_Load(object sender, EventArgs e)
         {
         //..

         var PrintOptions = new PdfPrintOptions(){ Dpi=100 };
         PrintOptions.SetHeaderText("{page} of {total-pages}”);
         
         AspxToPdf.RenderThisPageAsPDF(AspxToPdf.FileBehaviour.Attachment, "FileName.pdf", PrintOptions);

         }


 
Full Object Reference for IronPdf.AspxToPdf
===================================================

.. doxygenclass:: IronPdf::AspxToPdf
   :members:



*************************
IronPdf.PdfPrintOptions
*************************

PdfPrintOptions is a class used to fine-tune the behavior of Pdf rendering by any the following methods:

* IronPdf.AspxToPdf.RenderThisPageAsPDF
* IronPdf.HtmlToPdf.RenderUrlAsPdf
* IronPdf.HtmlToPdf.RenderHtmlAsPdf 

PdfPrintOptions covers almost every pdf setting we can imagine, including editable PDF forms, javascript, custom headers and footers with *{mail-merge}* fields, paper sizes including custom sizes, margins …the whole kitchen sink. 

Using PdfPrintOptions with HtmlToPdf
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
To make coding easier - there are 2 ways you can do set the PdfPrintOptions:

1. Construct HtmlToPdf with a PdfPrintOptions parameter.  E.g.

.. code-block:: c#

     HtmlToPdf myPdfMaker = new  HtmlToPdf(PdfPrintOptions);

2. HtmlToPdf has a property called PrintOptions which is an instance of PdfPrintOptions. This allows for on the fly settings changes.  E.g.


.. code-block:: c#

     HtmlToPdf myPdfMaker = new IronPdf.HtmlToPdf();
     myPdfMaker.PrintOptions.GrayScale = true;
     myPdfMaker.RenderHtmlAsPdf("<p>hello world</p>").SaveAs("test.pdf");
     myPdfMaker.PrintOptions.Zoom = 200;  
     myPdfMaker.RenderHtmlAsPdf(@“<p>hello world</p>“).SaveAs(“test2.pdf”);

Using PdfPrintOptions with AspxToPdf
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
For AspxToPdf your PdfPrintOptions are added as a final additional argument in the RenderThisPageAsPDF function call.  


.. code-block:: c#

     IronPdf.PdfPrintOptions PrintOptions = new PrintOptions(){ Dpi = 300 };
     IronPdf.AspxToPdf.RenderThisPageAsPDF(AspxToPdf.FileBehaviour.Attachment, “FileName.pdf”, PrintOptions);
 

Full Object Reference for IronPdf.AspxToPdf
==============================================

 .. doxygenclass:: IronPdf::PdfPrintOptions
   :members:


***********************
IronPdf.PdfResource
***********************

 All of IronPdf.HtmlToPdf's rendering methods output an instance of a IronPDF.PdfResource.

  We decided to work this way to make you job as a coder easier.  

PdfResource can automatically save a file for you, but it can also return an ByteArray (byte[]) as raw binary data or a System.IO.MemoryStream.  

This is useful if you want to post-process you pdf, save to a database, or do something innovative we haven't even thought of yet!    

Using IronPdf.PdfResource
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: c#

	using IronPdf;

	HtmlToPdf myPdfMaker = new IronPdf.HtmlToPdf();
	PdfResource  myPdf = myPdfMaker.RenderHtmlAsPdf("<p>hello world</p>");
	
	//Now you have 3 ways to use the PDF data stored in myPdf:

	PdfResource.SaveAs(@"C:\path\mypdf.pdf");
	  // or 
	System.IO.MemoryStream stream = PdfResource.Stream;
	  //or 
	byte[] data = BinaryData;



Full Object Reference for IronPdf.PdfResource
==================================================

.. doxygenclass:: IronPdf::Pdfresource
   :members:   