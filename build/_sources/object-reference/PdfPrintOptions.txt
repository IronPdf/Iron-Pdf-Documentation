=======================
IronPdf.PdfPrintOptions
=======================

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
 

*******************************************
Full Object Reference for IronPdf.AspxToPdf
*******************************************

 .. doxygenclass:: IronPdf::PdfPrintOptions
   :members: