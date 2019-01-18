---
title: CommandText 属性 (ADO)
TOCTitle: CommandText property (ADO)
ms:assetid: 0debec1c-068f-0aea-fce8-e61aa39c5907
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248859(v=office.15)
ms:contentKeyID: 48543234
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231123
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 66797accb24cead7d7ba5732f0a9c58ee31049e5
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28725978"
---
# <a name="commandtext-property-ado"></a>CommandText 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示要对提供程序发出的命令的文本。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个包含提供程序命令的 **String** 值，如 SQL 语句、表名称、相对 URL 或存储过程调用。默认值为 ""（零长度字符串）。

## <a name="remarks"></a>备注

使用 **CommandText** 属性可以设置或返回 [Command](command-object-ado.md) 对象所表示的命令的文本。通常，这将是 SQL 语句，但也可以是提供程序能识别的任何其他类型的命令语句，如存储过程调用。SQL 语句必须是提供程序的查询处理器支持的特定语句或版本。

在设置 [CommandText](prepared-property-ado.md) 属性时，如果 **Command** 对象的 **Prepared** 属性设置为 **True** ，且 **Command** 对象绑定到打开的连接，则在调用 [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 或 **Open** 方法时，ADO 会准备查询（即提供程序所存储的查询的已编译格式）。

根据 [CommandType](commandtype-property-ado.md) 属性设置的不同，ADO 可能会更改 **CommandText** 属性。可以随时读取 **CommandText** 属性，以查看 ADO 将在执行期间使用的实际命令文本。

使用 **CommandText** 属性可以设置或返回指定资源（如文件或目录）的相对 URL。该资源的相对位置由绝对 URL 显式指定，或由打开的 [Connection](connection-object-ado.md) 对象隐式指定。


> [!NOTE]
> [!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。


