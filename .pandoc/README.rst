estatjp
=======

`E-Stat <https://www.e-stat.go.jp/en>`__ is a widely used portal site
for accessing Japanese governmental statistical data. Began operation in
2008. e-Stat currently hosts `744 surveys (1,688,550 datasets) in
Japanese <https://www.e-stat.go.jp/stat-search?page=1 target='_blank'>`__
from about 30 governmental agencies with `56 surveys (292,856 datasets)
available in
English <https://www.e-stat.go.jp/en/stat-search?page=1>`__. These
collections contain 'databases' and files (mainly Excel files). The
'databases' can be accessed via an API. API urls can cover entire
databases or subsets that can be tailored to users' individual needs.

The objective of the estatjp Python package is to provide access to the
e-Stat portal and return datasets in pandas.DataFrame format.

For example, the e-Stat API returns CSV streams that contain headers
with metadata. These headers interfere with pandas.get_csv. The first
release of estatjp returns a dictionary that contains the header and
main table as separate dataframes.

Requirement
-----------

The e-Stat API requires an application ID that can be obtained from the
`E-Stat API <https://www.e-stat.go.jp/api/en>`__ page. Install this ID
into your project by setting your terminal to your project root and
running the following commands:

.. code:: 

   pip install python-dotenv
   dotenv set ESTAT_APP_ID your-app-id

Install this package
--------------------

.. code:: 

   pip install estatjp

Example
-------

This example downloads an English dataset, the `Labour Force Survey
Basic Tabulation Whole Japan Monthly table Population of 15 years old
and over by labour force
status <https://www.e-stat.go.jp/en/dbview?sid=0003005798>`__. The API
url for that table is assigned to enurl below.

.. code:: python

   import pandas
   from dotenv import load_dotenv
   from estatjp import api
   enurl = 'http://api.e-stat.go.jp/rest/3.0/app/getSimpleStatsData?appId=&lang=E&statsDataId=0003005798&metaGetFlg=Y&cntGetFlg=N&explanationGetFlg=Y&annotationGetFlg=Y&sectionHeaderFlg=1&replaceSpChars=0'
   dfs = api.get_csv_data(enurl)
   print(dfs.get('Header'))
   print(dfs.get('Main'))
   print(dfs.get('Description'))

References
==========

.. container:: references csl-bib-body hanging-indent
   :name: refs

   .. container:: csl-entry
      :name: ref-ashizawa2022estat.en

      Ashikawa, Souta, Matsuda, Junichi, & Osone, Tadashi. (2022).
      Method for improving the recall in e-stat data search.
      *Proceedings of Annual Conference of the Information Systems
      Society in Japan ISSJ2022*, S1–C1.
      https://doi.org/10.19014/proceedingsissj.18.0_S1-C1

   .. container:: csl-entry
      :name: ref-ashizawa2023estat.en

      Ashikawa, Souta, Matsuda, Junichi, & Osone, Tadashi. (2023).
      Development of front-end search system improving recall in e-stat.
      *Proceedings of Annual Conference of the Information Systems
      Society in Japan ISSJ2023*, 1–6.
      https://doi.org/10.19014/proceedingsissj.19.0_P001

   .. container:: csl-entry
      :name: ref-cocosan2023python.en

      cocosan. (2023). *Python apuri: Seifu tokei e-stat wo shigoto ni
      ikase!* https://www.youtube.com/watch?v=hiaK-jTXpCI.

   .. container:: csl-entry
      :name: ref-higashi2024incidence

      Higashi, Takahiro, & Kurokawa, Yukinori. (2024). Incidence,
      mortality, survival, and treatment statistics of cancers in
      digestive organs—japanese cancer statistics 2024. *Annals of
      Gastroenterological Surgery*, *8*\ (6), 958–965.
      https://doi.org/10.1002/ags3.12835

   .. container:: csl-entry
      :name: ref-inoue2023self

      Inoue, Takao. (2023). A self-made tutorial for GitHub flavored
      markdown (GFM), and its source codes. *ResearchGate*.
      https://www.researchgate.net/publication/370937551_A_self-made_tutorial_for_GitHub_Flavored_Markdown_GFM_and_its_source_codes

   .. container:: csl-entry
      :name: ref-kato2021residential

      Kato, Haruka, & Takizawa, Atsushi. (2021). Which residential
      clusters of walkability affect future population from the
      perspective of real estate prices in the osaka metropolitan area?
      *Sustainability*, *13*\ (23), 13413.
      https://doi.org/10.3390/su132313413

   .. container:: csl-entry
      :name: ref-masui2021r.en

      Masui, Toshikatsu. (2021). *R to python de manabu tokeigaku
      nyumon*. Ohmsha.

   .. container:: csl-entry
      :name: ref-estat2016adaptor

      National Statistics Center, Japan. (2016). *Chukan apuri*.
      https://github.com/e-stat-api/adaptor.

   .. container:: csl-entry
      :name: ref-nishimura2017linked.en

      Nishimura, Shoki. (2017). Providing statistical data by linked
      open data (LOD): Innovative official statistical data (e-stat)
      dissemination. *Joho Kanri*, *59*\ (12), 812–821.
      https://doi.org/10.1241/johokanri.59.812

   .. container:: csl-entry
      :name: ref-seki2023social

      Seki, Katsunori. (2023). Social identification and redistribution
      preference: A survey experiment in japan. *Social Science Japan
      Journal*, *26*\ (1), 47–60. https://doi.org/10.1093/ssjj/jyac029

   .. container:: csl-entry
      :name: ref-takahashi2022estat.en

      Takahashi, Shūichiro. (2022). *E-stat to nakayokusuru hon: Python
      to ōpun deta de nihon wo bunseki suru! API keiyu de seifu tōkei wo
      shutoku! katsuyo!* Impress R&D.

   .. container:: csl-entry
      :name: ref-wakabayashi2015public.en

      Wakabayashi, Chihiro, Shinmura, Hiromi, Ando, Miri, Shimada,
      Masako, & Yanagawa, Hiroshi. (2015). Kōeisei topikksu dai 13 kai
      seifutōkei no sōgōmadoguchi e-stat: Chiiki shindan he no katsuyō -
      jissen herusu puromōshon. *Gekkan Chiiki Igaku*, *29*\ (2), 52.
      https://doi.org/10.60261/chiikiigaku.29.2_52
