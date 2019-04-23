---
title: Open 方法（ADO 连接）
TOCTitle: Open method (ADO Connection)
ms:assetid: 1adaa17d-dfe1-22e0-3415-720516d138f8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248951(v=office.15)
ms:contentKeyID: 48543525
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b3b83eb87b181320c86e1aea91ede70cd173a5ce
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288425"
---
# <a name="open-method-ado-connection"></a>Open 方法（ADO 连接）

**适用于**：Access 2013、Office 2013
 
用于打开与数据源的连接。

## <a name="syntax"></a>语法

*连接*。打开*ConnectionString*、 *UserID*、 *Password*和*Options*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*ConnectionString* |可选。 **字符串** 值，包含连接信息。有关有效设置的详细信息，请参阅 [ConnectionString](connectionstring-property-ado.md) 属性。|
|*UserID* |可选。 **字符串** 值，包含建立连接时所使用的用户名。|
|*Password* |可选。 **字符串** 值，包含建立连接时所使用的密码。|
|*Options* |可选。一个 [ConnectOptionEnum](connectoptionenum.md) 值，用于确定此方法应在建立连接之后（同步）还是之前（异步）返回。|

## <a name="remarks"></a>注解

如果对 [Connection](connection-object-ado.md) 对象使用 **Open** 方法，则将建立与数据源的物理连接。此方法成功完成之后，连接将激活，您可以针对它发布命令并处理结果。

使用可选的*ConnectionString*参数指定一个连接字符串, 该字符串包含一系列由分号分隔的*argument* *= value*语句, 或者指定使用 URL 标识的文件或目录资源。 **ConnectionString** 属性会自动继承用于 *ConnectionString* 参数的值。 因此，您可以先设置 **Connection** 对象的 **ConnectionString** 属性然后再打开它，或者使用 *ConnectionString* 参数在调用 **Open** 方法过程中设置或替代当前的连接参数。

如果同时在 *ConnectionString* 参数和可选的 *UserID* 与 *Password* 参数中传递用户和密码信息，则 *UserID* 和 *Password* 参数将替代在 *ConnectionString* 中指定的值。

结束对打开的 **Connection** 执行的操作之后，可使用 [Close](close-method-ado.md) 方法释放任何关联的系统资源。关闭对象不会将其从内存中删除，您可以更改其属性设置，稍后使用 **Open** 方法再次打开它。若要从内存中完全消除对象，请将对象变量设置为 *Nothing*。

**远程数据服务使用情况**在客户端**Connection**对象上使用时, **Open**方法在**连接**对象上打开[Recordset](recordset-object-ado.md)之前, 不会实际建立到服务器的连接。

> [!NOTE]
> [!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 有关详细信息, 请参阅[绝对和相对 url](absolute-and-relative-urls.md)。


