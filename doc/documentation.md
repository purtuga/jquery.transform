jquery.transform
================

jquery.transform is a jQuery plugin which provides an easy way for users to perform cross-browser XML transformations with XSL templates. It lets you retrieve and transform your xml and xsl data through a number of formats including passing the data as a url, string, and xml or ajax object and has all the features of a normal ajax request including success, error, and complete callbacks.

Features
--------

-    Asynchronous or non-asynchronous calls
-    Multiple asynchronous transformations at once
-    Pass an object or html for a loading message while xml and xsl is retrieved
-    Automatically transform element by providing a custom transform attribute to the element
-    Supports passing ajax objects for xml and xsl retrieval
-    Request data from URL or pass as string
-    Works with xsl:import and xsl:include (even Safari and Chrome)
-    Pass custom parameter values to XSL and callback functions
-    Custom handlers for 'success', 'error', and 'complete'
-    Non-asynchronous calls return transformed HTML
-    Option to append XML and XSL as a data island
-    Works with selectors
-    No ActiveX objects
-    Tested in IE6/8, Firefox3, Opera 9, Safari 3, Chrome, Netscape 8, and Flock


Usage
-----

Simple call that retrieves a remote xml file and transforms it using cds.xsl template into a element on the page with id of 'result'   

    $("div#result").transform({
        xml:"xml/catalog.xml",
        xsl:"xsl/cds.xsl"
    });

Full list of input options:

    $.tranform({
        el: null,
        cache : false,
        async : true,
        xsl : null,
        xml : null,
        xslstr : null,
        xmlstr : null,
        xslobj : null,
        xmlobj : null,
        xslParams : null,
        error : null,
        success : null,
        complete : null,
        island : false,
        pass : null,
        msg : null,
        dataType : "html"
    })


Options
-------

All properties below can be passed in the transform config object.
    
-   **el**          :   *HTMLElement|jQuery. Optional. Default=null* <br />
                        The element which the transformation html is placed. Automatically set if using $("[selector]").transform()
-   **cache**       :   *Boolean. Optional. Default=false.* <br />
                        Used in the ajax request for xml and xsl. Does not cache result.
-   **async**       :   *Boolean. Optional. Deafult=true* <br />
                        Make ajax calls async or not. If false, transform function returns html.
-   **error**       :   *Function. Optional. Default=null* <br />
                        Function to call if transform fails. Passes html,xsl,xml,transform object,and exception as arguments. Not called if ajax request fails.
-   **success**     :   *Function. Optional. Default=null* <br />
                        Function to call if transform succeeds. Passes html,xsl,xml and transform object as arguments.
-   **complete**    :   *Function. Optional. Default=null* <br />
                        Function to call after transform. Fires after success and even if there is an error. Passes html,xsl,xml,and transform object as arguments.
-   **island**      :   *Boolean. Optional. Default=false.* <br />
                        Appends a hidden div with an xml node inside
-   **pass**        :   *Object|String. Optional. Default=null* <br />
                        Allows you to pass additional variables,etc which will be passed to the callback functions in the obj argument.
-   **msg**         :   *String|HTMLElement. Optional. Default=null* <br />
                        HTML to load to el element while performing transformation.
-   **xslParams**   :   Object. Optional. Default=null* <br />
                        Object with {name:value} pairs that will add the value to the xsl:param with the respective name.
-   **xmlstr**      :   *String. Optional|Required. Default=null* <br />
                        XML data as a string. Required if xml and xmlobj are not used.
-   **xslstr**      :   *String. Optional|Required. Default=null* <br />
                        XSL data as a string. Required if xsl and xslobj are not used.
-   **xmlobj**      :   *XMLDocument. Optional|Required. Default=null* <br />
                        XML document object used for the transform
-   **xslobj**      :   *XMLDocument. Optional|Required. Default=null* <br />
                        XSL as an XML document object used for the transformation 
-   **xml**         :   *String|AJAXObject. Optional|Required. Default=null* <br />
                        URL to xml file. Required if xmlstr and xmlobj not used. An AJAX Object can be used to set custom Ajax callbacks, post, etc. Required if xmlstr and xmlobj are not used.
-   **xsl**         :   *String. Optional|Required. Default=null* <br />
                        URL to xsl file. Required if xslstr and xslobj are not used. An Ajax object can be used to set custom Ajax callbacks, post, etc. Required if xslstr and xslobj are not used.
-   **dataType**    :   *String. Optional. Default="html"* <br />
                        Return type for transformation result. Default is to return html. Can be "json" or "xml"


Versions
--------

-   Client-side - The client-side version supports basic features in all current browsers. It does not support xsl:import and xsl:include when using Chrome, Safari, or Opera.

-   Server-side - A solution to the client-side issues. Using this will transform your data on the server instead of client and the xml and xsl are still requested in the browser to utilize any browser authentication. This version requires setting some values in the $.transform_config object.
You currently must set two values in the $.transform_config object:
sitetoserver - A relative path from the current page to your server-side asp/php file.
jstosite - A relative path from the javascript file to your site.


About the Author
----------------

This library was developed by Jason Iles of daersystems.com. The site no longer exists and I received permission from the author to create this github repository for it so that it may encourage the community to use it and maintain it.  I'm currently a heavy user of this library in my workings with Sharepoint webservices, thus the interest in continuing support for it.

The original pages for this plugin can still be seen on archive.org ([here](http://web.archive.org/web/20100815004711/http://daersystems.com/jquerytransform.asp)).


License
-------


*Copyright (c) 2009 DAER Systems (daersystems.com)*

Dual licensed under the [GPL](http://www.gnu.org/licenses/gpl.html) and [MIT](http://www.opensource.org/licenses/mit-license.php) licenses.

