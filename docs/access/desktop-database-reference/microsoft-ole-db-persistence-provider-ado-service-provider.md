---
title: Microsoft OLE DB Persistence Provider（ADO 服务提供程序）
TOCTitle: Microsoft OLE DB Persistence Provider (ADO Service Provider)
ms:assetid: 22e41769-36eb-5a88-05ed-870938657624
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249007(v=office.15)
ms:contentKeyID: 48543719
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4045445120d42f1ca88fce22ce566fc970fce28b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288951"
---
# <a name="microsoft-ole-db-persistence-provider-ado-service-provider"></a>Microsoft OLE DB 暂留提供程序（ADO 服务提供程序）


**适用于**：Access 2013、Office 2013 

Microsoft OLE DB Persistence Provider 使您可以将 [Recordset](recordset-object-ado.md) 对象保存到文件中，而且以后可以从该文件中还原 **Recordset** 对象。架构信息、数据和待定的更改将被保留。

可以采用专用的 Advanced Data Table Gram (ADTG) 格式或开放式可扩展标记语言 (XML) 格式来保存 **Recordset** 。

## <a name="provider-keyword"></a>提供程序关键字

若要调用此提供程序，请在连接字符串中指定以下关键字和值。

```vb 
 
"Provider=MSPersist" 
```

## <a name="errors"></a>Errors

在应用程序中，可能会检测到此提供程序发出的以下错误。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>E_BADSTREAM</p></td>
<td><p>打开的文件不具备有效格式（即，格式不为 ADTG 或 XML）。</p></td>
</tr>
<tr class="even">
<td><p>E_CANTPERSISTROWSET</p></td>
<td><p>已保存的 <strong>Recordset</strong> 对象具有防止其被存储的特征。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

Microsoft OLE DB Persistence Provider 没有公开任何动态属性。

当前只有参数化分级 **Recordset** 对象不能被保存。

有关持久存储 **Recordset** 对象的详细信息，请参阅[关于记录集持久化的详细信息](more-about-recordset-persistence.md)。

使用流打开 **Recordset** 时，除了 **Open** 方法的 *Source* 参数以外，不应指定任何其他参数。

