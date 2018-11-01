---
title: Filter 和 RecordCount 属性示例 (JScript)
TOCTitle: Filter and RecordCount properties example (JScript)
ms:assetid: a33e3d13-4184-69f9-4ff2-111106e653cf
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249755(v=office.15)
ms:contentKeyID: 48546780
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6d5994a072e34d07256cbce7b45ffe3fd5179f99
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877602"
---
# <a name="filter-and-recordcount-properties-example-jscript"></a>Filter 和 RecordCount 属性示例 (JScript)


**适用于**： Access 2013、 Office 2013

本示例打开 Northwind 数据库 Companies（公司）表上的一个 **Recordset** ，然后使用 [Filter](filter-property-ado.md) 属性将可见的记录限制为 CompanyName（公司名称）字段以字母 D 开头的记录。请将以下代码剪切并粘贴到"记事本"或其他文本编辑器中，并将其另存为 **FilterJS.asp** 。

