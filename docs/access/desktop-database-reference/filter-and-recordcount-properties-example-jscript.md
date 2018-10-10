---
title: Filter 和 RecordCount 属性示例 (JScript)
TOCTitle: Filter and RecordCount Properties Example (JScript)
ms:assetid: a33e3d13-4184-69f9-4ff2-111106e653cf
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249755(v=office.15)
ms:contentKeyID: 48546780
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0f6b33ce6824144626a9219fa2d218d90b38ed89
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467603"
---
# <a name="filter-and-recordcount-properties-example-jscript"></a><span data-ttu-id="c158b-102">Filter 和 RecordCount 属性示例 (JScript)</span><span class="sxs-lookup"><span data-stu-id="c158b-102">Filter and RecordCount Properties Example (JScript)</span></span>


<span data-ttu-id="c158b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c158b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c158b-104">本示例打开 Northwind 数据库 Companies（公司）表上的一个 **Recordset** ，然后使用 [Filter](filter-property-ado.md) 属性将可见的记录限制为 CompanyName（公司名称）字段以字母 D 开头的记录。请将以下代码剪切并粘贴到"记事本"或其他文本编辑器中，并将其另存为 **FilterJS.asp** 。</span><span class="sxs-lookup"><span data-stu-id="c158b-104">This example opens a **Recordset** on the Companies table of the Northwind database and then uses the [Filter](filter-property-ado.md) property to limit the records visible to those where the CompanyName field starts with the letter D. Cut and paste the following code to Notepad or another text editor, and save it as **FilterJS.asp**.</span></span>

