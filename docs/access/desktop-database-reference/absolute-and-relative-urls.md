---
title: 绝对 URL 和相对 URL
TOCTitle: Absolute and relative URLs
ms:assetid: 79a1f793-7154-1c13-7dfe-a1b8cd64e1ea
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249501(v=office.15)
ms:contentKeyID: 48545774
ms.date: 10/17/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a488617dc7ba0d7d1f7e38391f8382fa1e7ed247
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282099"
---
# <a name="absolute-and-relative-urls"></a>绝对 URL 和相对 URL

**适用于**：Access 2013、Office 2013    

URL 指定在本地或网络计算机上存储的目标（如文件、目录、HTML 页、图像、程序等）的位置。 在本讨论中，*绝对 URL* 的形式为：

*scheme://server/path/resource*

其中：

|名称 |说明|
|:----|:----------|
|*scheme*|指定如何访问 *resource*。|
|*server*|指定 *resource* 所在的计算机的名称。|
|*path*|指定在目标前面的目录序列。 如果省略 *resource*，则目标是 *path* 中最后一个目录。|
|*resource*|如果包含它，则 *resource* 是目标，并且通常是文件的名称。 它可以是一个包含单个二进制字节流的*简单文件*, 也可以是包含一个或多个存储和二进制字节流的*结构化文档*。|

*绝对 URL* 包含定位资源所需的所有信息。

*相对 URL* 使用绝对 URL 作为起点来定位资源。实际上，目标的“完整 URL”是通过将绝对和相对 URL 连接在一起指定的。相对 URL 通常只由 *path* 和可选的 *resource* 组成，但没有 *scheme* 或 *server*。

## <a name="url-scheme-registration"></a>URL 方案注册

如果提供程序支持 URL，它将注册一个或多个 URL 架构。 这意味着使用此架构的任何 URL 都将自动调用所注册的提供程序。 例如，*http* 架构注册到 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 ADO 假定所有以 "http" 为前缀的 url 代表要用于 Internet 发布提供程序的 web 文件夹或文件。 有关由提供程序注册的架构的信息，请参阅提供程序文档。

## <a name="defining-context-with-a-url"></a>使用 URL 定义上下文

打开的连接（由 [Connection](connection-object-ado.md) 对象表示）的一个功能是将随后的操作限制到由该连接表示的数据源。就是说，连接定义了后续操作的上下文。

使用 ADO 2.5，绝对 URL 也可能定义上下文。例如，使用绝对 URL 打开 [Record](record-object-ado.md) 对象时，将隐式创建 **Connection** 对象以表示该 URL 所指定的资源。

可以在 **Record** 对象的 [Open](open-method-ado-record.md) 方法的 *ActiveConnection* 参数中指定用于定义上下文的绝对 URL。 绝对 URL 还可以指定为**Connection**对象[open](open-method-ado-connection.md)方法*ConnectionString*参数中`URL=` new 关键字的值, 而[Recordset](recordset-object-ado.md)对象的[open](open-method-ado-recordset.md)方法*ActiveConnection*参数.

还可以用表示目录的已打开 **Record** 或 **Recordset** 对象来定义上下文，因为这些对象已经具有用于指定上下文的隐式或显式声明的 **Connection** 对象。

## <a name="scoped-operations"></a>作用域操作

上下文同时定义*作用域*, 即目录及其子目录, 在后续操作中可能会参与。 **Record** 对象具有多个对目录及其所有子目录操作的已确定范围的方法，包括 [CopyRecord](copyrecord-method-ado.md)、[MoveRecord](moverecord-method-ado.md) 和 [DeleteRecord](deleterecord-method-ado.md)。

## <a name="relative-urls-as-command-text"></a>命令文本形式的相对 url

可以在 **Connection** 对象的 **Execute** 方法的 *CommandText* 参数中以及在 **Recordset** 对象的 **Open** 方法的 *Source* 参数中，指定用于确定要对数据源执行的命令的字符串。

可以在 *CommandText* 或 *Source* 参数中指定相对 URL。相对 URL 实际上不指定命令（如 SQL 命令）；命令是在那些参数中指定的。此外，活动连接的上下文必须是绝对 URL，并且 *Option* 参数必须设置为 **adCmdTableDirect**。

例如，可以对 Winnt/system32 目录的 Readme25.txt 文件打开 **Recordset** ，如下所示：

```vb
recordset.Open "system32/Readme25.txt", "URL=https://YourServer/Winnt/",,,adCmdTableDirect 
```

连接字符串中的绝对 URL 指定服务器 (YourServer) 和路径 (Winnt)。 此 URL 还定义了上下文。

命令文本中的相对 url 使用绝对 url 作为起点, 并指定路径的其余部分 (system32) 和要打开的文件 (readme25.txt)。

"选项" 字段指示命令类型是相对 URL。

作为另一个示例，以下代码将在目录的内容中打开一个 **Recordset** ：

```vb
recordset.Open "", "URL=https://YourServer/Winnt/",,,adCmdTableDirect 
```

## <a name="ole-db-provider-supplied-url-schemes"></a>OLE DB 提供程序提供的 URL 方案

示例

ADO supports OLE DB providers that recognize their own URL schemes. 例如, [Microsoft OLE DB Provider for Internet 发布](microsoft-ole-db-provider-for-internet-publishing.md), 它访问 "已发布的 Windows 2000" 文件可识别现有的 HTTP 方案。

