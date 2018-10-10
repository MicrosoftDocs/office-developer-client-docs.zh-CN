---
title: Workspace.Type Property (DAO)
TOCTitle: Type Property
ms:assetid: 89e59280-d2cd-b6a2-16c5-9f14f42fdd99
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197086(v=office.15)
ms:contentKeyID: 48546177
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d062adbde4e9d7053e61342b7433939d4fbffcb8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466178"
---
# <a name="workspacetype-property-dao"></a>Workspace.Type Property (DAO)


**适用于**： Access 2013 |Office 2013

设置或返回一个值，该值指示对象的操作类型或数据类型。只读 **Integer**。

## <a name="syntax"></a>语法

*表达式*。类型

*表达式*一个代表**Workspace**对象的变量。

## <a name="remarks"></a>注解

对于 **Workspace** 对象，可能的设置和返回值如下。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>Workspace 类型</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>dbUseJet</strong></p></td>
<td><p><strong>Workspace</strong> 连接到 Microsoft Access 数据库引擎。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbUseODBC</strong></p></td>
<td><p><strong>Workspace</strong> 连接到 ODBC 数据源。</p></td>
</tr>
</tbody>
</table>

