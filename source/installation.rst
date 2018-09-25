==================
Installing IronPdf 
==================


********************************************************
Developer Notice: `The Pdf Library Installation Guide Has Moved <https://ironpdf.com/docs/questions/installation/>`_.   
********************************************************


For Microsoft Visual Studio Users - the easiest way to install IronPdf is using the **NuGet** Package Manager.

.. code-block:: bash

     PM> Install-Package IronPdf

Using NuGet 
--------------------------------------------------------------------------------
* Right click on your project in Visual Studio 'Solution Explorer'
* Select "Manage Nuget Packages…"
* In the Search Box Type "IronPDF"
* Select The "IronPdf" package to your lower left.
* Click the "Install" button your right.

For more info you can also find us at: https://www.nuget.org/packages/IronPdf/


Manual Installation
------------------------------------------------------------------------------
* Download IronPdf as DLL from http://ironpdf.com/packages/IronPdf.zip
* Extract the DLL to a logical location inside your project *(or GAC for advanced users)*
* In Visual Studio 'Solution Explorer’”:
        * Right click on your project and choose Add > Reference....
        * Select 'Browse...' and then find IronPDF.dll and double click on it.