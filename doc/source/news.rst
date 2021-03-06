:orphan:

.. highlightlang:: none

News
====

.. _release-7-06:

Release 7.06 - 2017-08-29
-------------------------

Improvements
^^^^^^^^^^^^

* [:doc:`/reference/udf/mroonga_highlight_html`] Added usage about
  ``mroonga_highlight_html``.

* Supported generated column. It is useful to full-text search for
  partially extracted content from JSON column. [GitHub#159,#160,#163]
  [Patch by Naoya Murakami]

* Added :ref:`server-variable-mroonga-enable-operations-recording`. variable.
  [GitHub#158] [Patch by Naoya Murakami]

* Supported virtual column for MariaDB 10.2 and MySQL 5.7. It supports
  ``VIRTUAL`` type.  [GitHub#161,#162] [Patch by Naoya Murakami]

* Supported MariaDB 10.1.26.

* [rpm][centos] Supported Percona Server 5.6.36 rel82.1 and 5.7.18-16.
  [Gitter/ja:59894500bc46472974622cbd] [Reported by
  @tigersun2000_twitter]

* [rpm][centos] Supported MySQL 5.6.37 and 5.7.19 on CentOS 7.
  [groonga-dev,04441] [Reported by Kagami Hiroshi]

Thanks
^^^^^^

* Naoya Murakami
* @tigersun2000_twitter
* Kagami Hiroshi

.. _release-7-05:

Release 7.05 - 2017-07-29
-------------------------

Improvements
^^^^^^^^^^^^

* Supported Groonga query log. Use ``mroonga_query_log_file`` variable
  to use this feature. [GitHub#148]

* Supported MariaDB 10.2.7. [groonga-dev,04397] [Reported by Tomohiro
  'Tomo-p' KATO]

* [:doc:`/reference/udf/mroonga_command`] Supported database name that
  has special name such as ``db-1`` for example. It contains special
  character ``-``.

* [:doc:`/reference/udf/mroonga_command`] Supported auto command
  syntax escape feature. It makes easy to use Groonga functionality
  from Mroonga.

* Supported MariaDB 5.5.57.

* [rpm][centos] Supported MySQL 5.6.37-2 and MySQL 5.7.19-1 on
  CentOS 6. [groonga-dev,04403] [Reported by Kagami Hiroshi]

* [ubuntu] Dropped Ubuntu 16.10 (Yekkety Yak) support.
  It has reached EOL at July 20, 2017.

* [:doc:`/reference/udf/mroonga_highlight_html`] Supported a function
  to highlight target column or text.

Fixes
^^^^^

* Fixed a crash bug when there is no active index internally.
  [Gitter:groonga/ja:596714a5c101bc4e3a7db4e5] [Reported by K
  Torimoto]

Thanks
^^^^^^

* K Torimoto
* Tomohiro 'Tomo-p' KATO
* Kagami Hiroshi

.. _release-7-04:

Release 7.04 - 2017-06-29
-------------------------

Improvements
^^^^^^^^^^^^

* Supported to show error message when failed to create a table for
  matched records. This kind of error occurs when indexes are
  broken. This error message helps to identify problem.

* [:doc:`/install/debian`] Supported Debian 9 (stretch).

Fixes
^^^^^

* Fixed a crash bug that missing ``NULL`` check before calling
  ``grn_table_setoperation`` causes. Such a crash bug occurs when
  indexes are broken.

.. _release-7-03:

Release 7.03 - 2017-05-29
-------------------------

Improvements
^^^^^^^^^^^^

* [:doc:`/reference/limitations`] Updated limitations about NULL in
  column. [Gitter/ja] [Reported by @bignum_twitter]

* Supported ``INDEX_MEDIUM`` and ``INDEX_SMALL`` flags. [GitHub#141]
  [Patch by Naoya Murakami]

* [:doc:`/install/centos`] Supported recent Percona Server 5.6.36 and
  5.7.18. [Reported by @pinpikokun]

Thanks
^^^^^^

* @bignum_twitter
* @pinpikokun
* Naoya Murakami

.. _release-7-02:

Release 7.02 - 2017-04-29
-------------------------

Improvements
^^^^^^^^^^^^

* [:doc:`/install/centos`] Dropped Ubuntu 12.04 (Precise Pangolin)
  support because of EOL.

* [:doc:`/install/ubuntu`] Added Zesty Zapus (Ubuntu 17.04) support.

Fixes
^^^^^

* [:doc:`/install/centos`] Fixed build error with MySQL 5.6.36 and
  MySQL 5.7.18.

* [cmake] Fixed missing link to ``libgroonga`` when mroonga is bundled
  and ``libgroonga`` isn't bundled. [GitHub#137] [Patch by Naoya
  Murakami]

Thanks
^^^^^^

* Naoya Murakami

.. _release-7-01:

Release 7.01 - 2017-03-29
-------------------------

Improvements
^^^^^^^^^^^^

* [:doc:`/install/centos`] Dropped CentOS 5 support because of EOL.

* [:doc:`/tutorial/storage`] Supported ``ALTER TABLE ADD/DROP FOREIGN
  KEY``.

* [:doc:`/tutorial/storage`] Supported fast ``ORDER LIMIT`` with
  ``ENUM``.  [groonga-dev,04277] [Reported by murata satoshi]

* Supported ``COMPRESS_ZSTD`` column compression flag. [GitHub#133]
  [Patch by Naoya Murakami]

* [:doc:`/reference/server_variables`] Added documentation about
  ``mroonga_libgroonga_support_zstd`` variable. [GitHub#133]
  [Patch by Naoya Murakaimi]

* [:doc:`/install`] Changed to recommend ``https://packages.groonga.org``
  for downloading resources.

Fixes
^^^^^

* [:doc:`/tutorial/storage`] Fixed update error for log-bin and
  ``UPDATE`` with collated ``PRIMARY KEY``. [GitHub#132] [Reported by
  kitora]

* Fixed a bug that ``FOREIGN KEY`` is dumped unexpectedly even though
  you didn't set it. [groonga-dev,04276] [Reported by murata satoshi]

Thanks
^^^^^^

* kitora
* murata satoshi
* Naoya Murakami

.. _release-7-00:

Release 7.00 - 2017-02-09
-------------------------

Improvements
^^^^^^^^^^^^

* [:doc:`/install/centos`] Changed to ensure enabling EPEL to install
  package.

* Supported ``FOREIGN KEY`` constrain on ``UPDATE`` and ``DELETE``
  parent row. In the previous versions, only ``FOREIGN KEY`` constrain
  on ``INSERT`` is supported.

* [:doc:`/tutorial/storage`] Supported updating row even though its
  table has primary key with ROW binlog format. In the previous
  version, it causes update statement error. [GitHub#130] [Reported by
  kitora]

Thanks
^^^^^^

* kitora

Past releases
-------------

.. toctree::
   :maxdepth: 2

   news/6.x
   news/5.x
   news/4.x
   news/3.x
   news/2.x
   news/1.x
   news/0.x
