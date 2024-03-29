.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt


.. _data-types-reference:

====================
Data types reference
====================



.. _data-type-tag:

<tag>
=====

.. container:: table-row

   Data type
         <tag>

   Examples
         ::

            <body lang="de">

   Comment
         An HTML tag.



.. _data-type-align:

align
=====

.. container:: table-row

   Data type
         align

   Examples
         right

   Comment
         **right / left / center**

         Decides alignment, typically in HTML-tags

   Default
         left



.. _data-type-vhalign:

VHalign
=======

.. container:: table-row

   Data type
         VHalign

   Examples
         Horizontal alignment = right and Vertical alignment = center:

         r , c

   Comment
         Pair of values separated by a comma. The first value determines the
         horizontal alignment, the second one the vertical alignment.

         **Possible values:**

         **r/c/l , t/c/b**

         Horizontal values standing for: right, center, left

         Vertical values standing for: top, center, bottom

   Default
         l , t



.. _data-type-resource:

resource
========

.. container:: table-row

   Data type
         resource

   Examples
         *Reference to a file in the file system:* ::

            fileadmin/picture.gif

         *Reference to a file from the resource field of the TypoScript
         template:* ::

            toplogo*.gif

         Note that the resource field and the possibility to reference files from
         it have been removed in TYPO3 6.0.

   Comment
         #. If the value contains a "/", it is expected to be a reference
            (absolute or relative) to a file in the file system. There is no
            support for wildcard characters in the name of the reference.

         #. If the value does not contain a "/", it is expected to be a reference
            to a file from the resource field in the template. You can write the
            exact filename or you can include an asterisk (\*) as wildcard. It is
            recommended to include an "\*" before the file extension (see the
            example). This will ensure that the file is still referenced
            correctly even if the template is copied (so that the file will have
            its name prepended with a number)!

            **Note:** The resource field in TypoScript templates has been removed
            in TYPO3 6.0. If you used this feature, move the referenced files to
            the folder fileadmin/ or similar and change your TypoScript to refer
            to these resources providing their path in the file system.



.. _data-type-imgresource:

imgResource
===========

.. container:: table-row

   Data type
         imgResource

   Examples
         Here "file" is an imgResource::

            10 = IMAGE
            10.file = fileadmin/toplogo.gif
            10.file.width = 200

         GIFBUILDER::

            10 = IMAGE
            10.file = GIFBUILDER
            10.file {
               # GIFBUILDER properties here...
            }

   Comment
         #. A "resource" (see above) plus imgResource properties (see the example
            and the object reference for imgResource below).

            Filetypes can be anything among the allowed types defined in the
            configuration variable $TYPO3\_CONF\_VARS['GFX']['imagefile\_ext'].
            Standard is pdf, gif, jpg, jpeg, tif, bmp, ai, pcx, tga, png.

         #. A GIFBUILDER object. See the object reference for GIFBUILDER below.



.. _data-type-html-code:

HTML code
=========

.. container:: table-row

   Data type
         HTML code

   Examples
         ::

            <b>Some text in bold</b>

   Comment
         pure HTML code



.. _data-type-target:

target
======

.. container:: table-row

   Data type
         target

   Examples
         \_top

         \_blank

         content

   Comment
         Target in an <a>-tag.

         This is normally the same value as the name of the root-level object
         that defines the frame.



.. _data-type-imageextension:

imageExtension
==============

.. container:: table-row

   Data type
         imageExtension

   Examples
         jpg

         web *(gif or jpg ..)*

   Comment
         Image extensions can be anything among the allowed types defined in
         the global variable $TYPO3\_CONF\_VARS['GFX']['imagefile\_ext'].
         Standard is pdf, gif, jpg, jpeg, tif, bmp, ai, pcx, tga, png.

         The value **"web"** is special. This will just ensure that an image is
         converted to a web image format (gif or jpg) if it happens not to be
         already!



.. _data-type-degree:

degree
======

.. container:: table-row

   Data type
         degree

   Examples
         45

   Comment
         -90 to 90, integers



.. _data-type-positive-integer:
.. _data-type-posint:
.. _data-type-intplus:

positive integer
================

.. container:: table-row

   Data type
         positive integer / posint / int+

   Examples
         42, 8, 9

   Comment
         Positive integer



.. _data-type-int:
.. _data-type-integer:

integer
=======

.. container:: table-row

   Data type
         integer / int

   Examples
         42, -8, -9, 0

   Comment
         integer

         (sometimes used generally though another type would have been more
         appropriate, like "pixels")



.. _data-type-string:
.. _data-type-str:
.. _data-type-value:

string
======

.. container:: table-row

   Data type
         string / str / value

   Examples
         The quick brown fox jumps over the lazy dog.

   Comment
         string.

         (sometimes used generally though another type would have been more
         appropriate, like "align")



.. _data-type-bool:
.. _data-type-boolean:

boolean
=======

.. container:: table-row

   Data type
         boolean

   Examples
         1

   Comment
         Possible values for boolean variables are "1" and "0"
         (meaning "TRUE" and "FALSE").

         Everything else is `evaluated to one of these values by PHP`__:
         Non-empty strings (but not "0") are treated as "TRUE",
         empty strings are evaluated to FALSE.

         __ http://php.net/manual/en/language.types.boolean.php

         Examples::

            dummy.enable = 0            # false, preferred notation
            dummy.enable = 1            # true, preferred notation
            dummy.enable =              # false, because the value is empty


.. _data-type-rotation:

rotation
========

.. container:: table-row

   Data type
         rotation

   Examples
         180

   Comment
         integer, degrees from 0 - 360



.. _data-type-xywh:

x,y,w,h
=======

.. container:: table-row

   Data type
         x,y,w,h

   Examples
         10,10,5,5

   Comment
         x,y is the offset from the upper left corner.

         w,h is the width and height



.. _data-type-html-color:

HTML-color
==========

.. container:: table-row

   Data type
         HTML-color

   Examples
         red

         #ffeecc

   Comment
         HTML color codes:

         =============  ================
         Color name     Hexadecimal code
         =============  ================
         Black             #000000
         Silver            #C0C0C0
         Gray              #808080
         White             #FFFFFF
         Maroon            #800000
         Red               #FF0000
         Purple            #800080
         Fuchsia           #FF00FF
         Green             #008000
         Lime              #00FF00
         Olive             #808000
         Yellow            #FFFF00
         Navy              #000080
         Blue              #0000FF
         Teal              #008080
         Aqua              #00FFFF
         =============  ================



.. _data-type-graphiccolor:

GraphicColor
============

.. container:: table-row

   Data type
         GraphicColor

   Examples
         red *(HTML-color)*

         #ffeecc *(HTML-color)*

         255,0,255 *(RGB-integers)*

         *Extra:*

         red *: \*0.8 ("red" is darkened by factor 0.8)*

         #ffeecc *: +16 ("ffeecc" is going to #fffedc because 16 is added)*

   Comment
         The color can be given as HTML-color or as a comma-separated list of
         RGB-values (integers).

         You can add an extra parameter that will modify the color
         mathematically:

         Syntax:

         [colordef] : [modifier]

         where modifier can be an integer which is added/subtracted to the
         three RGB-channels or a floating point with an "\*" before, which will
         then multiply the values with that factor.



.. _data-type-page-id:

page\_id
========

.. container:: table-row

   Data type
         page\_id

   Examples
         this

         34

   Comment
         A page id (integer) or "this" (=current page id).



.. _data-type-pixels:

pixels
======

.. container:: table-row

   Data type
         pixels

   Examples
         345

   Comment
         pixel-distance



.. _data-type-list:

list
====

.. container:: table-row

   Data type
         list

   Examples
         item,item2,item3

   Comment
         list of values



.. _data-type-margins:

margins
=======

.. container:: table-row

   Data type
         margins

   Examples
         *This sets margin-left to 10 and margin-bottom to 5. Top and right are
         not set (zero)*

         10,0,0,5

   Comment
         l,t,r,b

         left, top, right, bottom



.. _data-type-wrap:

wrap
====

.. container:: table-row

   Data type
         wrap

   Examples
         *This will cause the value to be wrapped in a p-tag coloring the
         value red:* ::

            <p style="color: red;"> | </p>

   Comment
         <...> \| </...>

         Used to wrap something. The parts on the left and right of the vertical
         line are placed on the left and right side of the value.



.. _data-type-linkwrap:

linkWrap
========

.. container:: table-row

   Data type
         linkWrap

   Examples
         *This will make a link to the root-level of a website:* ::

            <a href="?id={0}"> | </a>

   Comment
         <.. {x}.> \| </...>

         {x}; x is an integer (0-9) and points to a key in the PHP array
         rootLine. The key is equal to the level the current page is on
         measured relatively to the root of the website.

         If the key exists the uid of the level that key pointed to is inserted
         instead of {x}.

         Thus we can insert page\_ids from previous levels.



.. _data-type-case:

case
====

.. container:: table-row

   Data type
         case

   Examples
         upper

   Comment
         Case-conversion.

         Possible keywords:

         **upper:** Convert all letters of the string to uppercase.

         **lower:** Convert all letters of the string to lowercase.

         **capitalize:** (Since TYPO3 4.6) Uppercase the first character of
         each word in the string.

         **ucfirst:** (Since TYPO3 4.6) Convert the first letter of the string
         to uppercase.

         **lcfirst:** (Since TYPO3 4.6) Convert the first letter of the string
         to lowercase.



.. _data-type-space:

space
=====

.. container:: table-row

   Data type
         space

   Examples
         5 \| 5

   Comment
         "before \| after"

         Used for content and sets space "before \| after".



.. _data-type-date-conf:

date-conf
=========

.. container:: table-row

   Data type
         date-conf

   Examples
         d-m-y *(dd-mm-yy format)*

   Comment
         See PHP function Date()!

         === ===========================================================
         Abb The abbreviation is expanded to:
         === ===========================================================
         a   "am" or "pm"
         A   "AM" or "PM"
         d   01 - 31, day of the month, numeric, 2 digits with leading zeros
         D   day of the week, textual, 3 letters like "Fri"
         F   month, textual, long, like "January"
         h   hour, numeric, 12 hour format
         H   hour, numeric, 24 hour format
         i   minutes, numeric
         j   1 - 31, day of the month, numeric, without leading zeros
         l   (lowercase 'L'), day of the week, textual, long, like "Friday"
         m   month, numeric
         M   month, textual, 3 letters, like "Jan"
         s   seconds, numeric
         S   English ordinal suffix, textual, 2 characters, like "th" or "nd"
         U   seconds since the epoch
         Y   year, numeric, 4 digits, like "2013"
         w   day of the week, numeric, 0 represents Sunday
         y   year, numeric, 2 digits, like "13"
         z   day of the year, numeric, like "299"
         === ===========================================================


.. _data-type-strftime-conf:

strftime-conf
=============

.. container:: table-row

   Data type
         strftime-conf

   Examples
         Date "DD-MM-YY" = ::

            %e:%m:%y

         Time "HH:MM:SS" = ::

            %H:%M:%S

         or just ::

            %T

   Comment
         ==== ==========================================================
         Abb  The abbreviation is expanded to:
         ==== ==========================================================
         %a   abbreviated weekday name according to the current locale
         %A   full weekday name according to the current locale
         %b   abbreviated month name according to the current locale
         %B   full month name according to the current locale
         %c   preferred date and time representation for the current locale
         %C   century number (the year divided by 100 and truncated to an integer, range 00 to 99)
         %d   day of the month as a decimal number (range 00 to 31)
         %D   same as %m/%d/%y
         %e   day of the month as a decimal number, a single digit is preceded by a space (range ' 1' to '31')
         %h   same as %b
         %H   hour as a decimal number using a 24-hour clock (range 00 to 23)
         %I   hour as a decimal number using a 12-hour clock (range 01 to 12)
         %j   day of the year as a decimal number (range 001 to 366)
         %m   month as a decimal number (range 01 to 12)
         %M   minute as a decimal number
         %n   newline character
         %p   either \`am' or \`pm' according to the given time value, or the corresponding strings for the current locale
         %r   time in a.m. and p.m. notation
         %R   time in 24 hour notation
         %S   second as a decimal number
         %t   tab character
         %T   current time, equal to %H:%M:%S
         %u   weekday as a decimal number [1,7], with 1 representing Monday
         %U   week number of the current year as a decimal number, starting with the first Sunday as the first day of the first week
         %V   The ISO 8601:1988 week number of the current year as a decimal number, range 01 to 53, where week 1 is the first week that has at least 4 days in the current year, and with Monday as the first day of the week.
         %W   week number of the current year as a decimal number, starting with the first Monday as the first day of the first week
         %w   day of the week as a decimal, Sunday being 0
         %x   preferred date representation for the current locale without the time
         %X   preferred time representation for the current locale without the date
         %y   year as a decimal number without a century (range 00 to 99)
         %Y   year as a decimal number including the century
         %Z   time zone or name or abbreviation
         %%   a literal \`%' character
         ==== ==========================================================



.. _data-type-unix-time:

UNIX-time
=========

.. container:: table-row

   Data type
         UNIX-time

   Examples
         *Seconds to May 09th 2016 12:34:*

         1462790096

   Comment
         Seconds since January 1st 1970.



.. _data-type-path:

path
====

.. container:: table-row

   Data type


   Examples
         *fileadmin/stuff/*

   Comment
         Path relative to the directory from which we operate.



.. _data-type-tag-data:

< tag >-data
============

.. container:: table-row

   Data type
         < *tag* >-data

   Examples
         *<frameset>-data: row*

         *could be '150,\*'*

   Comment



.. _data-type-tag-params:

< tag >-params
==============

.. container:: table-row

   Data type
         < *tag* >-params

   Examples
         *<frameset>-params*

         *could be 'border="0" framespacing="0"'*

   Comment
         Parameters for a tag.



.. _data-type-gettext:

getText
=======

.. container:: table-row

   Data type
         getText

   Examples
         .. For help about t3-field-list-table see
            http://mbless.de/4us/typo3-oo2rest/06-The-%5Bfield-list-table%5D-directive/1-demo.rst.html

         .. t3-field-list-table::
          :header-rows: 1

          - :dt:
                Example

            :dd:
                Comment

          - :dt:
            :dd:
                This returns a value from somewhere in a PHP array, as defined by the
                type. The syntax is "type : pointer". The type is case-insensitive.

          - :dt:
               **= field : header**

               *get content from the $cObj->data-array[header]*

            :dd:
                **field:** [field name from the current *$cObj* ->data-array in the
                cObject.]

                As default the *$cObj* ->data-array is $GLOBALS['TSFE']->page (record
                of the current page!)

                In TMENU: *$cObj* ->data is set to the page-record for each menu
                item.

                In CONTENT/RECORDS *$cObj* ->data is set to the actual record

                In GIFBUILDER *$cObj* ->data is set to the data GIFBUILDER is
                supplied with.

          - :dt:
                **= parameters : color**

                *get content from the $cObj->parameters-array[color]*

            :dd:
                **parameters:** [field name from the current *$cObj* ->parameters-
                array in the cObject.]

                See ->parseFunc!

          - :dt:
                **= register : color**

                *get content from the $GLOBALS['TSFE']->register[color]*

            :dd:
                **register:** [field name from the $GLOBALS['TSFE']->register]

                See cObject "LOAD\_REGISTER"!

          - :dt:
                **= leveltitle : 1**

                *get the title of the page on the first level of the rootline*

                **= leveltitle : -2 , slide**

                *get the title of the page on the level right below the current page
                AND if that is not present, walt to the bottom of the rootline until
                there's a title*

                **= leveluid : 0**

                *get the id of the root-page of the website (level zero)*

            :dd:
                **leveltitle, leveluid, levelmedia:** [levelTitle, uid or media in
                rootLine, 0- , negative = from behind, " , slide" parameter forces a
                walk to the bottom of the rootline until there's a "true" value to
                return. Useful with levelmedia.]

          - :dt:
                **= levelfield : -1 , user\_myExtField , slide**

                *get the value of the user defined field "user\_myExtField" in the
                root line (requires additional configuration in $TYPO3\_CONF\_VARS to
                include field!)*

            :dd:
                **levelfield:** Like "leveltitle" et al. but where the second
                parameter is the rootLine field you want to fetch. Syntax: [pointer,
                integer], [field name], ["slide"]

          - :dt:
                **= global : HTTP\_COOKIE\_VARS \| some\_cookie**

                *get the env variable $HTTP\_COOKIE\_VARS[some\_cookie]*

            :dd:
                **global:** [GLOBAL-var, split with \| if you want to get from an
                array! Deprecated, use GP, TSFE or getenv]

          - :dt:
                **= date : d-m-y**

                *get the current time formatted dd-mm-yy*

            :dd:
                **date:** [date-conf]

          - :dt:
                **= page : title**

                *get the current page-title*

            :dd:
                **page:** [current page record]

          - :dt:
                **= current : 1**

                *get the current value*

            :dd:
                **current: 1** (gets 'current' value)

          - :dt:
                **= level : 1**

                *get the rootline level of the current page*

            :dd:
                **level: 1** (gets the rootline level of the current page)

          - :dt:
                **= GP : stuff**

                *get input value from query string, (&stuff=)*

                **= GP : stuff \| key**

                *get input value from query string, (&stuff[key]=)*

            :dd:
                **GP:** Value from GET or POST method. Use this instead of global

                **GPvar: Usage of "GPvar" is deprecated. Use "GP" instead!**

          - :dt:
                **= getenv : HTTP\_REFERER**

                *get the env var HTTP\_REFERER*

            :dd:
                **getenv:** Value from environment variables

          - :dt:
                **= getIndpEnv : REMOTE\_ADDR**

                *get the client IP*

            :dd:
                **getIndpEnv:** Value from
                TYPO3\CMS\Core\Utility\GeneralUtility::getIndpEnv() (t3lib\_div::getIndpEnv())

          - :dt:
                **= DB : tt\_content:234:header**

                *get the value of the header of record with uid 234 from table
                tt\_content*

            :dd:
                **DB:** Value from database, syntax is [table name] : [uid] : [field].
                Any record from a table in TCA can be selected here. Only marked-
                deleted records does not return a value here.

          - :dt:
                **= file : 17 : size**

                *(Since TYPO3 6.0) get the file size of the file with the
                sys\_file UID 17.*

            :dd:
                **file:** syntax is [uid] : [property]. Retrieves a property from a
                file object (FAL) by identifying it through its sys\_file UID. Note
                that during execution of the FILES cObject, you can also reference the
                current file with "current" as UID like "file : current : size".

                |

                The following properties are available:

                name, size, sha1, extension, MIME type, contents, publicUrl, localPath

                |

                Furthermore when manipulating references (such as images in content
                elements or media in pages), additional properties are available (not
                all are available all the time, it depends on the setup of *references*
                of the FILES cObject):

                title, description, link, alternative

                |

                See the :ref:`FILES cObject for usage examples <cobj-files-examples>`.

          - :dt:
                **= fullRootLine : -1, title**

                *get the title of the page right before the start of the current
                website*

            :dd:
                **fullRootLine:** syntax is [pointer, integer], [field name],
                ["slide"]

                This property can be used to retrieve values from "above" the current
                page's root. Take the below page tree and assume that we are on the
                page "Here you are!". Using the "levelfield" propertydescribed above,
                it is possible to goup only to the page "Site root", because it is the
                root of a new (sub-)site. With "fullRootLine" it is possible to go all
                the way up to page tree root. The numbers between square brackets
                indicate to which page each value of *pointer* would point to::

                  - Page tree root [-2]
                    |- 1. page before [-1]
                      |- Site root (root template here!) [0]
                        |- Here you are! [1]

                A "slide" parameter can be added just as for the "levelfield" property
                above.

          - :dt:
                **= LLL:EXT:css\_styled\_content/pi1/locallang.xlf:login.logout**

                *get localized label for logout button*

            :dd:
                **LLL:** Reference to a locallang (xlf, xml or php) label. Reference
                consists of [fileref]:[labelkey]

          - :dt:
                **= path:EXT:ie7/js/ie7-standard.js**

                *get path to file relative to siteroot possibly placed in an
                extension*

            :dd:
                **path:** path to a file, possibly placed in an extension, returns
                empty if the file does not exist.

          - :dt:
                **= cObj : parentRecordNumber**

                *get the number of the current cObject record*

            :dd:
                **cObj:** [internal variable from list: "parentRecordNumber"]: For
                CONTENT and RECORDS cObjects that are returned

                by a select query, this returns the row number (1,2,3,...) of the
                current cObject record.

          - :dt:
                **= debug : rootLine**

                *output the current root-line visually in HTML*

            :dd:
                **debug:** Returns HTML formatted content of PHP variable defined by
                keyword. Available keys are "rootLine", "fullRootLine", "data"

          - :dd:
                **Getting array/object elements**

                You can fetch the value of an array/object by splitting it with a pipe
                "\|".Example::

                   = TSFE:fe_user|user|username

          - :dd:
                **Getting more values**

                By separating the value of getText with "//" (double slash) you let
                getText fetch the first value. If it appears empty ("" or zero) the
                next value is fetched and so on. Example::

                   = field:header // field:title // field:uid

                This gets "title" if "header" is empty. If "title" is also empty it
                gets field "uid"



.. _data-type-dir:

dir
===

.. container:: table-row

   Data type
         dir

   Examples
         *returns a list of all pdf, gif and jpg-files from
         fileadmin/files/ sorted by their name reversely and with the full
         path (with "fileadmin/files/" prepended).*

         **fileadmin/files/ \| pdf,gif,jpg \| name** \| r \| true

   Comment
         [path relative to the web root of the site] \| [list of valid
         extensions] \| [sorting: name, size, ext, date] \| [reverse: "r"] \|
         [return full path: boolean

         Files matching is returned in a comma-separated string.

         **Note:**

         The value of config-option "lockFilePath" must equal the first part of
         the path. Thereby the path is locked to that folder.



.. _data-type-function-name:

function name
=============

.. container:: table-row

   Data type
         function name

   Examples
         Function::

            user_reverseString

         Method in class::

            user_stringReversing
            ->reverseString

   Comment
         Indicates a function or method in a class to call. See more
         information at the USER cObject.

         Depending on implementation the class or function name (but not the
         method name) should probably be prefixed with "user\_". The prefix
         can be changed in the $TYPO3\_CONF\_VARS config though. The function /
         method is normally called with 2 parameters, $conf (TS configuration)
         and $content (some content to be processed and returned).

         Also if you call a method in a class, it is checked (when using the
         USER/USER\_INT objects) whether a class with the same name, but
         prefixed with "ux\_" is present and if so, *this* class is
         instantiated instead. See the document "Inside TYPO3" for more
         information on extending classes in TYPO3!


.. ###### END~OF~TABLE ######


[tsref:(datatypes)]


.. _data-types-object-types:

Data types: Object types
""""""""""""""""""""""""

These are some "data types" that might be mentioned and valid values
are shown here below:


.. _data-type-cobject:

cObject
=======

"cObjects" are also called "Content Objects". See the section "Content
Objects" later in this manual.

**Examples:** ::

    TEXT / IMAGE / MEDIA ....



.. _data-type-frameobj:

frameObj
========

FRAMESET / FRAME



.. _data-type-menuobj:

menuObj
=======

See the section "Menu Objects" later in this manual.

**Examples:** ::

    GMENU / TMENU / IMGMENU / JSMENU



.. _data-type-gifbuilderobj:

GifBuilder Object
=================

See section :ref:`GIFBUILDER` in this manual.

**Examples:** ::

    TEXT / SHADOW / OUTLINE / EMBOSS / BOX / IMAGE / EFFECT


