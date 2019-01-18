---
title: DriverPromptEnum 枚举 (DAO)
TOCTitle: DriverPromptEnum Enumeration
ms:assetid: 8dda5e9f-a58f-a62d-eb49-5966d4a1e086
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197361(v=office.15)
ms:contentKeyID: 48546266
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9612c0713a86ed6ad34a5eff61e45efcddf6cf24
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726104"
---
# <a name="driverpromptenum-enumeration-dao"></a>DriverPromptEnum 枚举 (DAO)


**适用于**： Access 2013、 Office 2013

指定是否以及何时提示用户建立连接。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dbDriverComplete</p></td>
<td><p>0</p></td>
<td><p>如果所提供的连接字符串包括 DSN 关键字，驱动程序管理器将使用所提供的字符串建立连接，否则，它将按照指定了 <strong>dbDriverPrompt</strong> 时的方式工作。</p></td>
</tr>
<tr class="even">
<td><p>dbDriverCompleteRequired</p></td>
<td><p>3</p></td>
<td><p>（默认值）其行为类似于 <strong>dbDriverComplete</strong>，不同之处在于，驱动程序将禁用完成连接所不需要的任何信息对应的控件。</p></td>
</tr>
<tr class="odd">
<td><p>dbDriverNoPrompt</p></td>
<td><p>1</p></td>
<td><p>驱动程序管理器使用所提供的连接字符串建立连接。如果提供的信息不足，则返回一个可捕获的错误。</p></td>
</tr>
<tr class="even">
<td><p>dbDriverPrompt</p></td>
<td><p>2</p></td>
<td><p>驱动程序管理器显示<strong>“ODBC 数据源”</strong>对话框。用来建立连接的连接字符串是由用户通过对话框选择和填写的数据源名称 (DSN) 构造的。</p></td>
</tr>
</tbody>
</table>

