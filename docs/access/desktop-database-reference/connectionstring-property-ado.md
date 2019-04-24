---
title: ConnectionString 属性 (ADO)
TOCTitle: ConnectionString property (ADO)
ms:assetid: c67a7daf-258f-d99d-6475-a4aa98d1e99d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249968(v=office.15)
ms:contentKeyID: 48547627
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3612652f3473c0794dbfe9be60f84ea2e3fee252
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295707"
---
# <a name="connectionstring-property-ado"></a>ConnectionString 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示用于建立数据源连接的信息。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **String** 值。

## <a name="remarks"></a>注解

使用**ConnectionString**属性可通过传递包含一系列由分号分隔的*参数* *= value*语句的详细连接字符串来指定数据源。

ADO 支持 **ConnectionString** 属性的五个参数；任何其他参数都直接传递给提供程序，不需要 ADO 进行任何处理。ADO 支持的参数如下：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>提供程序 =</em></p></td>
<td><p>指定用于连接的提供程序的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>File Name=</em></p></td>
<td><p>指定包含预置连接信息的、特定于提供程序的文件（例如，持久化的数据源对象）的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>Remote Provider=</em></p></td>
<td><p>指定在打开客户端连接时要使用的提供程序的名称。 (仅限远程数据服务。)</p></td>
</tr>
<tr class="even">
<td><p><em>Remote Server=</em></p></td>
<td><p>指定打开客户端连接时使用的服务器的路径名称（仅限于远程数据服务）。</p></td>
</tr>
<tr class="odd">
<td><p><em>URL =</em></p></td>
<td><p>将连接字符串指定为标识资源的绝对 URL，例如，文件或目录。</p></td>
</tr>
</tbody>
</table>


设置 **ConnectionString** 属性并打开 [Connection](connection-object-ado.md) 对象后，提供程序可以更改该属性的内容，例如，通过将 ADO 定义的参数名称映射到其提供程序对等项。

**ConnectionString** 属性自动继承为 [Open](open-method-ado-connection.md) 方法的 *ConnectionString* 参数使用的值，因此可以在 **Open** 方法调用期间重写当前的 **ConnectionString** 属性。

由于 *File Name* 参数会导致 ADO 加载关联的提供程序，因此不能同时传递 *Provider* 和 *File Name* 参数。

当连接关闭时，**ConnectionString** 属性为可读写，而当其打开时，该属性为只读。

**ConnectionString** 属性中重复的参数将被忽略。将使用任何参数的最后一个实例。

**远程数据服务使用情况**在客户端**Connection**对象上使用时, **ConnectionString**属性只能包含*远程提供程序*和*远程服务器*参数。

