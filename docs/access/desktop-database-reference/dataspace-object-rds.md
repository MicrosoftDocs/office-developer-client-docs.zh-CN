---
title: DataSpace 对象 (RDS)
TOCTitle: DataSpace object (RDS)
ms:assetid: 7db181d5-422b-49fe-b6af-a20f5da520ff
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249527(v=office.15)
ms:contentKeyID: 48545862
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 43a69e16f14df7304a2278456641f6ad44fbccb7
ms.sourcegitcommit: 48bfe5ab15b11105f4f52937b886c92bdc26525a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25910654"
---
# <a name="dataspace-object-rds"></a><span data-ttu-id="e0ee3-102">DataSpace 对象 (RDS)</span><span class="sxs-lookup"><span data-stu-id="e0ee3-102">DataSpace object (RDS)</span></span>

<span data-ttu-id="e0ee3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e0ee3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e0ee3-104">创建位于中间层的自定义业务对象的客户端代理。</span><span class="sxs-lookup"><span data-stu-id="e0ee3-104">Creates client-side proxies to custom business objects located on the middle tier.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0ee3-105">说明</span><span class="sxs-lookup"><span data-stu-id="e0ee3-105">Remarks</span></span>

<span data-ttu-id="e0ee3-p101">远程数据服务需要业务对象代理，以便客户端组件可以与位于中间层的业务对象通信。通过代理，可以方便地利用跨进程或计算机边界的应用程序的 [Recordset](recordset-object-ado.md) 数据的打包、解包和传输（封送处理）功能。</span><span class="sxs-lookup"><span data-stu-id="e0ee3-p101">Remote Data Service needs business object proxies so that client-side component can communicate with business objects located on the middle tier. Proxies facilitate the packaging, unpackaging, and transport (marshaling) of the application's [Recordset](recordset-object-ado.md) data across process or machine boundaries.</span></span>

<span data-ttu-id="e0ee3-p102">远程数据服务使用 **RDS.DataSpace** 对象的 [CreateObject](createobject-method-rds.md) 方法创建业务对象代理。每当创建业务对象的中间层业务对象对应方的实例时，就会动态创建业务对象代理。远程数据服务支持下列协议：HTTP、HTTPS（HTTP 安全套接字）、DCOM 以及进程中（客户端组件和驻留在同一计算机上的业务对象）。</span><span class="sxs-lookup"><span data-stu-id="e0ee3-p102">Remote Data Service uses the **RDS.DataSpace** object's [CreateObject](createobject-method-rds.md) method to create business object proxies. The business object proxy is dynamically created whenever an instance of its middle-tier business object counterpart is created. Remote Data Service supports the following protocols: HTTP, HTTPS (HTTP Secure Sockets), DCOM, and in-process (client components and the business object reside on the same computer).</span></span>

> [!NOTE]
> <span data-ttu-id="e0ee3-p103">[!注释] 当 **RDS.DataSpace** 对象使用 HTTP 或 HTTPS 协议时，RDS 的行为模式为"无状态"。即，服务器返回响应后，就会丢弃有关客户端请求的所有内部信息。</span><span class="sxs-lookup"><span data-stu-id="e0ee3-p103">RDS behaves in a "stateless" manner when the **RDS.DataSpace** object uses the HTTP or HTTPS protocols. That is, any internal information about a client request is discarded after the server returns a response.</span></span>

<span data-ttu-id="e0ee3-p104">尽管好像在业务对象代理的整个生命周期中都存在业务对象，而实际上仅在将响应发送给请求之前才存在业务对象。发送请求后（即，调用了业务对象的方法），代理会打开一个与服务器的新连接，服务器会创建该业务对象的新实例。业务对象响应请求后，服务器会破坏业务对象并关闭连接。</span><span class="sxs-lookup"><span data-stu-id="e0ee3-p104">Although the business object appears to exist for the lifetime of the business object proxy, the business object actually exists only until a response is sent to a request. When a request is issued (that is, a method is invoked on the business object), the proxy opens a new connection to the server and the server creates a new instance of the business object. After the business object responds to the request, the server destroys the business object and closes the connection.</span></span>

<span data-ttu-id="e0ee3-p105">这种行为意味着您不能使用业务对象属性或变量将数据从一个请求传递到另一个请求。必须使用某些其他机制（如文件或方法参数）来保留状态数据。</span><span class="sxs-lookup"><span data-stu-id="e0ee3-p105">This behavior means you cannot pass data from one request to another using a business object property or variable. You must employ some other mechanism, such as a file or a method argument, to persist state data.</span></span>

<span data-ttu-id="e0ee3-118">**RDS.DataSpace** 对象的类 ID 为 BD96C556-65A3-11D0-983A-00C04FC29E36。</span><span class="sxs-lookup"><span data-stu-id="e0ee3-118">The class ID for the **RDS.DataSpace** object is BD96C556-65A3-11D0-983A-00C04FC29E36.</span></span>

