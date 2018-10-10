---
title: Open 方法 (ADO Connection)
TOCTitle: Open Method (ADO Connection)
ms:assetid: 1adaa17d-dfe1-22e0-3415-720516d138f8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248951(v=office.15)
ms:contentKeyID: 48543525
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 33d3abd4ebf188534dbaefd9e7668453635a7aaa
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468097"
---
# <a name="open-method-ado-connection"></a>Open 方法 (ADO Connection)


**适用于**： Access 2013 |Office 2013
 

用于打开与数据源的连接。

## <a name="syntax"></a>语法

*连接*。打开*ConnectionString*、*用户 Id*、*密码*和*选项*

## <a name="parameters"></a>参数

  - *ConnectionString*

  - 可选。 **字符串** 值，包含连接信息。有关有效设置的详细信息，请参阅 [ConnectionString](connectionstring-property-ado.md) 属性。

  - *用户 Id*

  - 可选。 **字符串** 值，包含建立连接时所使用的用户名。

  - *Password*

  - 可选。 **字符串** 值，包含建立连接时所使用的密码。

  - *Options*

  - 可选。一个 [ConnectOptionEnum](connectoptionenum.md) 值，用于确定此方法应在建立连接之后（同步）还是之前（异步）返回。

## <a name="remarks"></a>说明

如果对 **Connection** 对象使用 [Open](connection-object-ado.md) 方法，则将建立与数据源的物理连接。此方法成功完成之后，连接将激活，您可以针对它发布命令并处理结果。

使用可选的*ConnectionString*参数指定包含一系列并用分号或文件的*参数* *= value*语句或标识与 URL 目录资源的连接字符串。 **ConnectionString**属性自动继承的*ConnectionString*参数使用的值。 因此，您可以将**Connection**对象的**ConnectionString**属性设置然后再打开它，或使用的*ConnectionString*参数设置或**Open**方法调用期间重写当前的连接参数.

如果同时在 *ConnectionString* 参数和可选的 *UserID* 与 *Password* 参数中传递用户和密码信息，则 *UserID* 和 *Password* 参数将替代在 *ConnectionString* 中指定的值。

结束对打开的 **Connection** 执行的操作之后，可使用 [Close](close-method-ado.md) 方法释放任何关联的系统资源。关闭对象不会将其从内存中删除，您可以更改其属性设置，稍后使用 **Open** 方法再次打开它。若要从内存中完全消除对象，请将对象变量设置为 *Nothing*。

**远程数据服务用法**当客户端**Connection**对象上使用， **Open**方法实际上不会建立连接到服务器的直到在**Connection**对象上打开[Recordset](recordset-object-ado.md) 。


> [!NOTE]
> <P>[!注释] 使用 HTTP 架构的 URL 将自动调用 <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>。有关详细信息，请参阅<A href="absolute-and-relative-urls.md">绝对 URL 和相对 URL</A>。</P>


