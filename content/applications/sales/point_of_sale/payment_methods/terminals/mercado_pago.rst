============
Mercado Pago
============

Connecting a payment terminal allows you to offer a fluid payment flow to your customers and ease
the work of your cashiers.

.. important::
   - Odoo only supports the **Point Smart** payment terminal that can be purchased on `Mercado
     Pago's website <https://www.mercadopago.com.mx/herramientas-para-vender/lectores-point>`_.
   - Point Smart can only be used in :abbr:`LATAM (Latin America)` countries. The following countries are
     supported:

     - Argentina
     - Brasil
     - Chile
     - Colombia
     - México
     - Perú
     - Uruguay

.. raw:: html

    <embed>

        <p style="color:#CD5C5C;"> <b> --> ASK MOOL: liste exhaustive? </b> </p>

        <p> <a href="http://lanic.utexas.edu/subject/countries/"> Car Google dit: The United Nations
        recognizes 33 Latin American countries. They are: Mexico,
        Guatemala, Honduras, Nicaragua, El Salvador, Costa Rica, Panama, Belize, Haiti, Cuba, Dominican
        Republic, Jamaica, Trinidad & Tobago, Bahams, Barbados, St. Lucia, Grenada, St. Vincent &
        Grenadines, Antigua & Barbuda, Dominica, St </a>
        </p>

    </embed>

.. seealso::
   - `Mercado Pago online payment <https://www.mercadopago.com.mx/herramientas-para-vender/check-out#benefits-checkout>`_

Configuration
=============

Start by creating your `Mercado Pago account <https://www.mercadopago.com.mx/>`_ and associate your
terminal with a :guilabel:`store` and a :guilabel:`cash drawer` by following the Mercado pago's documentation.

Then, ensure your Point Smart terminal is set to :guilabel:`Point of Sale` by going to [ASK MOOL]

.. raw:: html

    <embed>

        <p style="color:#CD5C5C;"> <b> --> ASK MOOL </b></p>

    </embed>

.. warning::
   Point Smart terminal has two modes of operation: "Standalone" and "Point of Sale". Be sure your
   terminal is configured on the "Point of Sale" mode, Odoo does not support the "Standalone" mode.

.. note::
   - All the purchased terminals are automatically available on your Mercado dashboard.
   - Odoo doesn't use the Mercado Pago *store* and *cash drawer* associated with your terminal,
     these functionalities are provided by Mercado Pago for their system management

.. seealso::
   `Mercado Pago's documentation page <https://www.mercadopago.com.mx/developers/en/docs>`_

.. _mercado_pago/credentials:

Generate your credentials
-------------------------

To configure your Point Smart terminal with the Odoo system you'll need three credentials:

- An :ref:`access token <mercado_pago/token>` used by Odoo to call Mercado Pago.
- A :ref:`webhook secret key <mercado_pago/webhook>` used by Odoo to authenticate notifications
  sent by Mercado Pago.
- The **terminal serial number** used to identify the terminal. You can find it at the back of
  your terminal.

To retrieve the first two fields, go to the `Mercado Pago developers website
<https://www.mercadopago.com.mx/developers/en>`_, and click :guilabel:`Your integrations` in the
navigation menu/footer. Then, select the integration you've created beforehand or create one.

.. _mercado_pago/token:

The access token
~~~~~~~~~~~~~~~~

From your integration, click :guilabel:`Production credentials` on the left navigation menu, then
click the eye icon to reveal the access token. Copy and save the key to paste it into the Odoo
:guilabel:`Production user token` field at :ref:`the payment method creation <mercado_pago/method>`.

.. raw:: html

    <embed>

        <p style="color:#CD5C5C;"> <b> NEEDS SCREENSHOT </b></p>

    </embed>

.. _mercado_pago/webhook:

The webhook secret key
~~~~~~~~~~~~~~~~~~~~~~

From your integration, click :guilabel:`Webhook` on the left navigation menu. Then, go to the
:guilabel:`production mode` tab and click the eye icon to reveal the webhook secret key. Copy and
save the key to paste it into the Odoo :guilabel:`Production secret key` field at :ref:`the payment
method creation <mercado_pago/method>`.

On the same page, set up the production URL field by filling it in using your domain name followed
by `/pos_mercado_pago/notification` (e.g., `https://www.myshop.com/pos_mercado_pago/notification`).

.. raw:: html

    <embed>

        <p style="color:#CD5C5C;"> <b> NEEDS SCREENSHOT </b></p>

    </embed>

.. _mercado_pago/method:

Configure the payment method
----------------------------

Enable the payment terminal :ref:`in the application settings <configuration/settings>` and
:doc:`create the related payment method <../../payment_methods>`. Set the journal type as
:guilabel:`Bank` and select :guilabel:`Mercado Pago` in the :guilabel:`Use a Payment Terminal` field.

Finally, fill in the mandatory fields with the :ref:`previously generated credentials
<mercado_pago/credentials>`:

- Fill in the :guilabel:`Production user token` field using the :ref:`access token
  <mercado_pago/token>`.
- Fill in the :guilabel:`Production secret key` field using the :ref:`webhook secret key
  <mercado_pago/webhook>`
- Fill in the :guilabel:`Terminal S/N` field using the terminal serial number. You can find it at
  the back of your terminal.

.. image:: mercado_pago/payment-method.png

Once the payment method is created, you can select it in your POS settings. To do so, go to the
:ref:`POS' settings <configuration/settings>`, click :guilabel:`Edit`, and add the payment method
under the :guilabel:`Payments` section.

Pay with a payment terminal
===========================

When processing a payment, select your Mercado Pago payment method, check the amount and
click on :guilabel:`Send`. Once the payment is successful, the status changes to :guilabel:`Payment
Successful`.

.. note::
   - | In case of connection issues between Odoo and the payment terminal, force the payment by
       clicking on :guilabel:`Force Done`, which allows you to validate the order.
     | This option is only available after receiving an error message informing you that the
       connection failed.
   - To cancel the payment request, click on :guilabel:`cancel`.

.. important::
   Any action made on the terminal should trigger a notification on the POS interface. If you do not
   receive any notification, ensure the :ref:`webhook secret key <mercado_pago/webhook>` is
   correctly configured.

.. raw:: html

    <embed>

        <p style="color:#CD5C5C;"> <b> --> ASK MOOL </b></p>

    </embed>
