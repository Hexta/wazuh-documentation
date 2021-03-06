.. Copyright (C) 2019 Wazuh, Inc.

.. _register_agents:

Registering agents
==================

.. meta::
  :description: Learn more about the different methods that can be used to register agents against the Wazuh manager.

In this section, the registration process is described, and more specifically the different methods that users can use to register agents in the Wazuh manager.

Prerequisites
-------------

The registration service requires an SSL certificate on the manager in order to work. This certificate will be automatically generated by the package during the installation if the ``openssl`` package is installed. This certificate is stored in ``/var/ossec/etc/sslmanager.cert``.

If you already have a certificate, you can use them just by copying them into the same path:

.. code-block:: console

  # cp <ssl_cert> /var/ossec/etc/sslmanager.cert
  # cp <ssl_key> /var/ossec/etc/sslmanager.key

Otherwise, you can create a self-signed certificate using the following command:

.. code-block:: console

  # openssl req -x509 -batch -nodes -days 365 -newkey rsa:4096 -out /var/ossec/etc/sslmanager.cert -keyout /var/ossec/etc/sslmanager.key

Available registration methods
------------------------------

You can use the method that better suits with your need. We recommend: :ref:`simple-registration-service`.

+----------------+---------------------------------------------------------------+
| Type           | Method                                                        |
+================+===============================================================+
| Manual method  | :ref:`using-command-line`                                     |
+----------------+---------------------------------------------------------------+
| Semi automatic | :ref:`restful-api-register`                                   |
+----------------+---------------------------------------------------------------+
|                | :ref:`simple-registration-service`                            |
|                +---------------------------------------------------------------+
| Automatic      | :ref:`password-authorization-registration-service`            |
|                +---------------------------------------------------------------+
|                | :ref:`manager-verification-registration`                      |
|                +---------------------------------------------------------------+
|                | :ref:`agent-verification-with-host-validation`                |
|                +---------------------------------------------------------------+
|                | :ref:`agent-verification-without-host-validation`             |
+----------------+---------------------------------------------------------------+

.. toctree::
    :maxdepth: 2
    :hidden:

    registration-process
    using-command-line
    simple-registration-method
    password-authorization-registration-service
    manager-verification/host-verification-registration
    restful-api-register
