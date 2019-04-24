---
title: Filter 和 RecordCount 属性示例 (JScript)
TOCTitle: Filter and RecordCount properties example (JScript)
ms:assetid: a33e3d13-4184-69f9-4ff2-111106e653cf
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249755(v=office.15)
ms:contentKeyID: 48546780
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 993209478d18d013771de8239d8e8cd10efc5da2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292487"
---
# <a name="filter-and-recordcount-properties-example-jscript"></a><span data-ttu-id="4b09f-102">Filter 和 RecordCount 属性示例 (JScript)</span><span class="sxs-lookup"><span data-stu-id="4b09f-102">Filter and RecordCount properties example (JScript)</span></span>


<span data-ttu-id="4b09f-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="4b09f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4b09f-104">本示例打开 Northwind 数据库 Companies（公司）表上的一个 **Recordset** ，然后使用 [Filter](filter-property-ado.md) 属性将可见的记录限制为 CompanyName（公司名称）字段以字母 D 开头的记录。请将以下代码剪切并粘贴到"记事本"或其他文本编辑器中，并将其另存为 **FilterJS.asp** 。</span><span class="sxs-lookup"><span data-stu-id="4b09f-104">This example opens a **Recordset** on the Companies table of the Northwind database and then uses the [Filter](filter-property-ado.md) property to limit the records visible to those where the CompanyName field starts with the letter D. Cut and paste the following code to Notepad or another text editor, and save it as **FilterJS.asp**.</span></span>

