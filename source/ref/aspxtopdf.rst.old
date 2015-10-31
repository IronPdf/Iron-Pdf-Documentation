=================
IronPdf.AspxToPdf
=================
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


*******************************************
Full Object Reference for IronPdf.AspxToPdf
*******************************************

.. doxygenclass:: IronPdf::AspxToPdf
   :members: