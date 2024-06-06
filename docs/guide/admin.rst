************
Guide: Admin
************

This module provides an in depth knowledge of the Translations admin.

Make admin translatable
=======================

To make an admin translatable:

1. Make sure the admin model is :ref:`translatable <models.Translatable>`.
2. Inherit the admin from the :class:`~translations.admin.TranslatableAdmin`.

   .. literalinclude:: ../../sample/admin.py
      :lines: 2

   .. literalinclude:: ../../sample/admin.py
      :pyobject: ContinentAdmin
      :emphasize-lines: 1

3. Add :class:`~translations.admin.TranslationInline` as its inline.

   .. literalinclude:: ../../sample/admin.py
      :lines: 2

   .. literalinclude:: ../../sample/admin.py
      :pyobject: ContinentAdmin
      :emphasize-lines: 2

The ``TranslatableAdmin`` should represent the values for
the :term:`default language`, and
the ``TranslationInline`` should represent the values for
the :term:`translation language`\ s.

.. note::

   An admin may contain an inline which itself needs to be translatable. Since
   translations appear as inlines to the admins, then the inlines themselves
   should have translation inlines in order to be translatable, and since
   Django does not support nested inlines there may be a need to use an
   external library. In that case check out :doc:`../howto/custom_admins`.
