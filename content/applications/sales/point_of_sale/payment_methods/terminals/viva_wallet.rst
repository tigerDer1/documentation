===========
Viva Wallet
===========

Connecting a **Viva Wallet payment terminal**  allows you to offer a fluid payment flow to your
customers and ease the work of your cashiers.

.. note::
   Viva Wallet lets you turn your phone into a mobile card reader: `Tap On Phone
   <https://www.vivawallet.com/gb_en/blog-tap-on-phone-gb>`_.

Configuration
=============

Start by creating your Viva Wallet account on `Viva Wallet's website <https://www.vivawallet.com>`_.

Locate your Viva Wallet credentials
-----------------------------------

When configuring Viva Wallet in Point of Sale, you need to use specific credentials that are
available in your Viva Wallet account. These credentials include your :ref:`Merchant ID
<viva_wallet/id-key>`, :ref:`API key <viva_wallet/id-key>`, :ref:`POS APIs credentials
<viva_wallet/pos-apis>`, and :ref:`Terminal ID <viva_wallet/identifier>` number.

.. _viva_wallet/id-key:

Merchant ID and API key
~~~~~~~~~~~~~~~~~~~~~~~

To find your Merchant ID and API key:

#. Go to your Viva Wallet account and select the relevant account;
#. Go to :menuselection:`Settings --> API access` in the navigation menu.

Your Merchant ID and API Key are located in the :guilabel:`Access credentials` section at the top of
the page. Save the keys and paste them into the Odoo :guilabel:`Merchant ID` and :guilabel:`API Key`
fields :ref:`when creating a payment method <viva_wallet/method-creation>`.

.. image:: viva_wallet/access-cred.png
   :alt: merchant ID and API key fields

.. note::
   These credentials are used for APIs that authenticate with Basic Auth.

.. seealso::
   `Find your Merchant ID and API Key
   <https://developer.vivawallet.com/getting-started/find-your-account-credentials/merchant-id-and-api-key/>`_.

.. _viva_wallet/pos-apis:

POS APIs credentials
~~~~~~~~~~~~~~~~~~~~

To find your POS APIs credentials:

#. Go to your Viva Wallet account and select the relevant account.
#. Go to :menuselection:`Settings --> API access` in the navigation menu.

Your POS APIs credentials are located in the :guilabel:`POS APIs Credential` section. Click
:guilabel:`Generate a pair of credentials` to generate them. Save the keys and paste them into the
Odoo :guilabel:`Client secret` and :guilabel:`Client ID` fields :ref:`when creating a payment method
<viva_wallet/method-creation>`.

.. image:: viva_wallet/api-cred.png
   :alt: Client secret and client ID fields

.. warning::
   These credentials are only displayed once. Ensure you keep a copy to secure them.

.. note::
   These credentials are used for Android and iOS POS Activation requests, as well as the Cloud
   Terminal API.

.. seealso::
   `Find your POS APIs Credentials
   <https://developer.vivawallet.com/getting-started/find-your-account-credentials/pos-apis-credentials/>`_.

.. _viva_wallet/identifier:

Terminal ID
~~~~~~~~~~~

To find your terminal ID number:

#. Go to your Viva Wallet account and select the relevant account.
#. Go to :menuselection:`Sales --> Physical payments --> Card terminals` in the navigation menu.

The terminal ID number is located under the :guilabel:`Terminal ID (TID)` column.

.. image:: viva_wallet/terminal-id.png
   :alt: Viva terminal ID

.. _viva_wallet/method-creation:

Configure the payment method
----------------------------

Enable the payment terminal :ref:`in the application settings <configuration/settings>` and
:doc:`create the related payment method <../../payment_methods>`. Set the journal type as
:guilabel:`Bank` and select :guilabel:`Viva Wallet` in the :guilabel:`Use a Payment Terminal` field.

Finally, fill in the mandatory fields with your

- :ref:`Merchant ID and API key <viva_wallet/ID-key>`
- :ref:`Client ID and Client secret <viva_wallet/pos-apis>`
- :ref:`Terminal ID <viva_wallet/identifier>`

.. image:: viva_wallet/create-method-viva-wallet.png
   :alt: payment method creation form
   :scale: 75%

Then, save the form and copy the generated webhook URL of the :guilabel:`Viva Wallet Webhook
Endpoint` field.

Configure the Webhook
---------------------

Webhooks allow you to receive real-time notifications whenever a transaction occurs within your Viva
Wallet account. To set them up:

#. Go to :menuselection:`Settings --> API Access --> Webhooks` in your Viva Wallet account.
#. Click :guilabel:`Create Webhook`.

   .. image:: viva_wallet/register-webhook.png
      :alt: webhook creation page

#. Enter the previously generated Webhook URL in the :guilabel:`URL` field. Click :guilabel:`Verify`
   to confirm its validity.
#. From the :guilabel:`Event Type` dropdown menu, select :guilabel:`Transaction Payment Created`.
#. Enable notifications by checking the :guilabel:`Active` checkbox.
#. Click :guilabel:`Save` to complete the configuration.

   .. image:: viva_wallet/webhook-form.png
      :alt: webhook creation popup window

.. seealso::
   - `Setting up webhooks <https://developer.viva.com/webhooks-for-payments/#setting-up-webhooks>`_
   - `Webhooks for payment transactions <https://developer.vivawallet.com/webhooks-for-payments/transaction-payment-created/>`_

Link the payment method to a POS
--------------------------------

You can select the payment method in your POS settings once the payment method is created. To do so,
go to the :ref:`POS' settings <configuration/settings>`, click :guilabel:`Edit`, and add the payment
method under the :guilabel:`Payment methods` field of the :guilabel:`Payments` section.

Pay with a payment terminal
===========================

When processing a payment, select the related payment method. Check the amount and
click on :guilabel:`Send`. Once the payment is successful, the status changes to :guilabel:`Payment
Successful`.

.. note::
   - | In case of connection issues between Odoo and the payment terminal, force the payment by
       clicking on :guilabel:`Force Done`, which allows you to validate the order.
     | This option is only available after receiving an error message informing you that the
       connection failed.
   - To cancel the payment request, click :guilabel:`cancel`.
