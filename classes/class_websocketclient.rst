.. Generated automatically by doc/tools/makerst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the WebSocketClient.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_WebSocketClient:

WebSocketClient
===============

**Inherits:** :ref:`WebSocketMultiplayerPeer<class_websocketmultiplayerpeer>` **<** :ref:`NetworkedMultiplayerPeer<class_networkedmultiplayerpeer>` **<** :ref:`PacketPeer<class_packetpeer>` **<** :ref:`Reference<class_reference>` **<** :ref:`Object<class_object>`

**Category:** Core

Brief Description
-----------------

A WebSocket client implementation

Member Functions
----------------

+----------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@globalscope_error>`  | :ref:`connect_to_url<class_WebSocketClient_connect_to_url>` **(** :ref:`String<class_string>` url, :ref:`PoolStringArray<class_poolstringarray>` protocols=PoolStringArray(  ), :ref:`bool<class_bool>` gd_mp_api=false **)** |
+----------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                   | :ref:`disconnect_from_host<class_WebSocketClient_disconnect_from_host>` **(** **)**                                                                                                                                           |
+----------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Signals
-------

.. _class_WebSocketClient_connection_closed:

- **connection_closed** **(** **)**

Emitted when the connection to the server is closed.

.. _class_WebSocketClient_connection_error:

- **connection_error** **(** **)**

Emitted when the connection to the server fails.

.. _class_WebSocketClient_connection_established:

- **connection_established** **(** :ref:`String<class_string>` protocol **)**

Emitted when a connection with the server is established, ``protocol`` will contain the sub-protocol agreed with the server.

.. _class_WebSocketClient_data_received:

- **data_received** **(** **)**

Emitted when a WebSocket message is received. Note: This signal is NOT emitted when used as high level multiplayer peer.


Member Variables
----------------

  .. _class_WebSocketClient_verify_ssl:

- :ref:`bool<class_bool>` **verify_ssl** - Enable or disable SSL certificate verification. Note: You must specify the certificates to be used in the project settings for it to work when exported.


Description
-----------

This class implements a WebSocket client compatible with any RFC 6455 complaint WebSocket server.

This client can be optionally used as a network peer for the :ref:`MultiplayerAPI<class_multiplayerapi>`.

After starting the client (:ref:`connect_to_url<class_WebSocketClient_connect_to_url>`), you will need to :ref:`NetworkedMultiplayerPeer.poll<class_NetworkedMultiplayerPeer_poll>` it at regular intervals (e.g. inside :ref:`Node._process<class_Node__process>`).

You will received appropriate signals when connecting, disconnecting, or when new data is available.

Member Function Description
---------------------------

.. _class_WebSocketClient_connect_to_url:

- :ref:`Error<enum_@globalscope_error>` **connect_to_url** **(** :ref:`String<class_string>` url, :ref:`PoolStringArray<class_poolstringarray>` protocols=PoolStringArray(  ), :ref:`bool<class_bool>` gd_mp_api=false **)**

Connect to the given URL requesting one of the given ``protocols`` as sub-protocol.

If ``true`` is passed as ``gd_mp_api``, the client will behave like a network peer for the :ref:`MultiplayerAPI<class_multiplayerapi>`. Note: connnections to non Godot servers will not work, and :ref:`data_received<class_WebSocketClient_data_received>` will not be emitted when this option is true.

.. _class_WebSocketClient_disconnect_from_host:

- void **disconnect_from_host** **(** **)**

Disconnect from the server if currently connected.


