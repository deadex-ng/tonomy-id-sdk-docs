Using the SDK
=============

Login
--------------

To login to an application with the TonomyID using Single Sign-On `Single Sign-On <https://en.wikipedia.org/wiki/Single_sign-on>`_.

To use Lumache, first install it using pip:

.. code-block:: javascript

import { UserApps, setSettings } from '@tonomy/tonomy-id-sdk';

...

async function onButtonPress() {
    setSettings({ ssoWebsiteOrigin: "https://tonomy-id-staging.tonomy.foundation" });

    UserApps.onPressLogin({ callbackPath: '/callback' });
}

Creating recipes
----------------

To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']

