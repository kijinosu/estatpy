=======
estatjp
=======

`E-Stat`_ is a widely used portal site for accessing Japanese governmental statistical data. Began operation in 2008. e-Stat currently hosts `744 surveys (1,688,550 datasets) in Japanese` from about 30 governmental agencies with `56 surveys (292,856 datasets) available in English`_. These collections contain 'databases' and files (mainly Excel files). The 'databases' can be accessed via an API. API urls can cover entire databases or subsets that can be tailored to users' individual needs.

.. _E-Stat: https://www.e-stat.go.jp/en
.. _E-Stat API: https://www.e-stat.go.jp/api/en
.. _56 surveys (292,856 datasets) available in English: https://www.e-stat.go.jp/en/stat-search?page=1
.. _744 surveys (1,688,550 datasets) in Japanese: https://www.e-stat.go.jp/stat-search?page=1

The objective of the `estatjp` Python package is to provide access to the e-Stat portal and return datasets in `pandas.DataFrame` format.

For example, the e-Stat API returns CSV streams that contain headers with metadata. These headers interfere with `pandas.get_csv`. The first release of estatjp returns a dictionary that contains the header and main table as separate dataframes.

-----------
Requirement
-----------

The e-Stat API requires an application ID that can be obtained from the `E-Stat API`_ page. Install this ID into your project by setting your terminal to your project root and running the following commands:

.. code::

    pip install python-dotenv
    dotenv set ESTAT_APP_ID your-app-id

--------------------
Install this package
--------------------

.. code::

    pip install estatjp

==========
References
==========

