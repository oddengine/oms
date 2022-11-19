# Live Streaming Administration Service

## Roadmap

- [x] Server status (cpu, memory, bandwidth*, connected*, etc.).  
- [x] Get Application, Instance, NetConnection, NetStream, Stream list.  
- [x] Get NetConnection status (uuid).  
- [x] Get NetStream status (uuid).  
- [x] Get Stream status (stream).  
- [x] Close NetConnection (uuid).  
- [x] Stop NetStream (uuid).  
- [x] Start a proxy to push/pull stream (method, application, instance, name, url, authorization).  
- [ ] Control media recorder.  

## API

| Method | Description |
| :--- | :--- |
| [closeNetConnection](#closenetconnection) | Closes the specified NetConnection. |
| [closeNetStream](#closenetstream) | Closes the specified NetStream. |
| [getApplications](#getapplications) | Returns an array of strings that contains the names of all the applications that are installed. |
| [getApplicationStats](#getapplicationstats) | Gets aggregate performance data for all instances of the specified application. |
| [getInstances](#getinstances) | Returns an array of strings that contains the names of all running application instances. |
| [getInstanceStats](#getinstancestats) | Gets aggregate performance data for a specified instance of an application. |
| [getNetConnections](#getnetconnections) | Returns an array of strings that represent the server-assigned UUIDs of all the network connections that are currently connected to the specified instance of the application. |
| [getNetConnectionStats](#getnetconnectionstats) | Gets detailed information for one or more network connections that are connecting to the specified instance of an application. |
| [getNetStreams](#getnetstreams) | Returns an array of strings that represent the server-assigned UUIDs of all the network streams that are currently connected to the specified instance of the application. |
| [getNetStreamStats](#getnetstreamstats) | Gets detailed information for one or more network streams that are connecting to the specified instance of an application. |
| [getRecorders](#getrecorders) | Returns an array of strings that contains the names of all the recorders that are currently running for the specified stream. |
| [getServerStats](#getserverstats) | Retrieves the server status and statistics about the operation of the server. |
| [getStreams](#getstreams) | Gets an array of strings that contains the names of all the live streams that are currently publishing to the specified instance of an application. |
| [getStreamStats](#getstreamstats) | Returns detailed information about a live stream. |
| [proxy](#proxy) | Starts a proxy to push/pull stream. |
| [recorder](#recorder) | Controls a media recorder by ID. |

### closeNetConnection

**HTTP**

<http://www.example.com/rtmp/admin/closeNetConnection?auser=&apass=&uuid>=

Closes the specified NetConnection.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |
| uuid | string | UUID of the NetConnection. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getNetConnections()](#getnetconnections), [getNetConnectionStats()](#getnetconnectionstats)

### closeNetStream

**HTTP**

<http://www.example.com/rtmp/admin/closeNetStream?auser=&apass=&uuid>=

Closes the specified NetStream.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |
| uuid | string | UUID of the NetStream. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getNetStreams()](#getnetstreams), [getNetStreamStats()](#getnetstreamstats)

### getApplications

**HTTP**

<http://www.example.com/rtmp/admin/getApplications?auser=&apass>=

Returns an array of strings that contains the names of all the applications that are installed.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
    <data>
        <total>1</total>
        <item>live</item>
    </data>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getApplicationStats()](#getapplicationstats), [getInstances()](#getinstances), [getInstanceStats()](#getinstancestats)

### getApplicationStats

**HTTP**

<http://www.example.com/rtmp/admin/getApplicationStats?auser=&apass=&application>=

Gets aggregate performance data for all instances of the specified application.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |
| application | string | Name of the Application. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
    <data>
        <Connections></Connections>
        <BwIn></BwIn>
        <BwOut></BwOut>
        <BytesIn></BytesIn>
        <BytesOut></BytesOut>
        <MsgDropped></MsgDropped>
        <MsgIn></MsgIn>
        <MsgOut></MsgOut>
    </data>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getApplications()](#getapplications), [getInstances()](#getinstances), [getInstanceStats()](#getinstancestats)

### getInstances

**HTTP**

<http://www.example.com/rtmp/admin/getInstances?auser=&apass>=

Returns an array of strings that contains the names of all running application instances.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
    <data>
        <total>1</total>
        <item>live/_definst_</item>
    </data>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getApplications()](#getapplications), [getInstanceStats()](#getinstancestats)

### getInstanceStats

**HTTP**

<http://www.example.com/rtmp/admin/getInstanceStats?auser=&apass=&instance>=

Gets aggregate performance data for a specified instance of an application.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |
| instance | string | Name of the Instance. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
    <data>
        <Connections></Connections>
        <BwIn></BwIn>
        <BwOut></BwOut>
        <BytesIn></BytesIn>
        <BytesOut></BytesOut>
        <MsgDropped></MsgDropped>
        <MsgIn></MsgIn>
        <MsgOut></MsgOut>
    </data>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getInstances()](#getinstances), [getApplicationStats()](#getapplicationstats)

### getNetConnections

**HTTP**

<http://www.example.com/rtmp/admin/getNetConnections?auser=&apass=&application=&instance>=

Returns an array of strings that represent the server-assigned UUIDs of all the network connections that are currently connected to the specified instance of the application.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |
| application | string | Name of the Application. |
| instance | string | Name of the Instance. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
    <data>
        <total>1</total>
        <item>
            <UUID></UUID>
            <Establisher></Establisher>
            <Address></Address>
            <Application></Application>
            <Instance></Instance>
            <Time></Time>
        </item>
    </data>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getApplications()](#getapplications), [getInstances()](#getinstances), [getNetConnectionStats()](#getnetconnectionstats)

### getNetConnectionStats

**HTTP**

<http://www.example.com/rtmp/admin/getNetConnectionStats?auser=&apass=&application=&instance=&uuid>=

Gets detailed information for one or more network connections that are connecting to the specified instance of an application.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |
| application | string | Name of the Application. |
| instance | string | Name of the Instance. |
| uuid | string | UUID of the NetConnection. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
    <data>
        <ConnectTime></ConnectTime>
        <BwIn></BwIn>
        <BwOut></BwOut>
        <BytesIn></BytesIn>
        <BytesOut></BytesOut>
        <MsgDropped></MsgDropped>
        <MsgIn></MsgIn>
        <MsgOut></MsgOut>
    </data>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getNetConnections()](#getnetconnections), [getNetStreamStats()](#getnetstreamstats)

### getNetStreams

**HTTP**

<http://www.example.com/rtmp/admin/getNetStreams?auser=&apass=&application=&instance>=

Returns an array of strings that represent the server-assigned UUIDs of all the network streams that are currently connected to the specified instance of the application.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |
| application | string | Name of the Application. |
| instance | string | Name of the Instance. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
    <data>
        <total>1</total>
        <item>
            <Client></Client>
            <Establisher></Establisher>
            <Address></Address>
            <UUID></UUID>
            <Application></Application>
            <Instance></Instance>
            <Name></Name>
            <Authorization></Authorization>
            <Type></Type>
            <Time></Time>
        </item>
    </data>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getApplications()](#getapplications), [getInstances()](#getinstances), [getNetStreamStats()](#getnetstreamstats)

### getNetStreamStats

**HTTP**

<http://www.example.com/rtmp/admin/getNetStreamStats?auser=&apass=&application=&instance=&uuid>=

Gets detailed information for one or more network streams that are connecting to the specified instance of an application.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |
| application | string | Name of the Application. |
| instance | string | Name of the Instance. |
| uuid | string | UUID of the NetConnection. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
    <data>
        <Type></Type>
        <Address></Address>
        <Client></Client>
        <UUID></UUID>
        <Application></Application>
        <Instance></Instance>
        <Name></Name>
        <Authorization></Authorization>
        <InboundBytes></InboundBytes>
        <InboundPackets></InboundPackets>
        <OutboundBytes></OutboundBytes>
        <OutboundPackets></OutboundPackets>
        <Time></Time>
    </data>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getNetStreams()](#getnetstreams), [getNetConnectionStats()](#getnetconnectionstats)

### getRecorders

**HTTP**

<http://www.example.com/rtmp/admin/getRecorders?auser=&apass=&application=&instance=&name>=

Returns an array of strings that contains the names of all the recorders that are currently running for the specified stream.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |
| application | string | Name of the Application. |
| instance | string | Name of the Instance. |
| name | string | Name of the Stream. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
    <data>
        <Item>
            <ID></ID>
            <Kind></Kind>
        </Item>
    </data>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getNetStreams()](#getnetstreams), [getStreams()](#getstreams)

### getServerStats

**HTTP**

<http://www.example.com/rtmp/admin/getServerStats?auser=&apass>=

Retrieves the server status and statistics about the operation of the server.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
    <data>
        <CPU></CPU>
        <Mem></Mem>
        <LaunchTime></LaunchTime>
        <BwIn></BwIn>
        <BwOut></BwOut>
        <BytesIn></BytesIn>
        <BytesOut></BytesOut>
        <MsgDropped></MsgDropped>
        <MsgIn></MsgIn>
        <MsgOut></MsgOut>
    </data>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getApplicationStats()](#getapplicationstats), [getInstanceStats()](#getinstancestats)

### getStreams

**HTTP**

<http://www.example.com/rtmp/admin/getStreams?auser=&apass=&application=&instance>=

Gets an array of strings that contains the names of all the live streams that are currently publishing to the specified instance of an application.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |
| application | string | Name of the Application. |
| instance | string | Name of the Instance. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
    <data>
        <total>1</total>
        <Item>abc</Item>
    </data>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getNetStreams()](#getnetstreams), [getStreamStats()](#getstreamstats)

### getStreamStats

**HTTP**

<http://www.example.com/rtmp/admin/getStreamStats?auser=&apass=&application=&instance=&name>=

Returns detailed information about a live stream.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |
| application | string | Name of the Application. |
| instance | string | Name of the Instance. |
| name | string | Name of the Stream. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
    <data>
        <Client></Client>
        <ID></ID>
        <Name></Name>
        <Type></Type>
        <Time></Time>
    </data>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getStreams()](#getstreams), [getNetStreamStats()](#getnetstreamstats)

### proxy

**HTTP**

<http://www.example.com/rtmp/admin/getStreamStats?auser=&apass=&method=&mode=&application=&instance=&name=&url=&authorization>=

Returns detailed information about a live stream.

**Availability**

Live Media Server 1.1.79.

**Parameters**

| Name | Type | Description |
| :--- | :--- | :--- |
| auser | string | Username of the administrator. |
| apswd | string | Password of the administrator. |
| method | string | "push", "pull" |
| mode | string | "normal", "strict", "unique" |
| application | string | Name of the Application. |
| instance | string | Name of the Instance. |
| name | string | Local stream name. |
| url | string | Remote stream url. |
| authorization | string | Authorization name. |

**Returns**

If the call succeeds, it returns XML with the following structure:

```xml
<result>
    <level>status</level>
    <code>NetConnection.Call.Success</code>
    <description></description>
</result>
```

***Note:*** *Some XML might also have a description element that contains a string describing the cause of the failure.*

**See also**

[getApplications()](#getapplications), [getInstances()](#getinstances), [getNetStreams()](#getnetstreams)
