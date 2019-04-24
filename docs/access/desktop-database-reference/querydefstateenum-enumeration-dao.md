---
title: QueryDefStateEnum 枚举 (DAO)
TOCTitle: QueryDefStateEnum Enumeration
ms:assetid: edfa3085-f8b4-b813-0828-2ba2a9dc0b9d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836359(v=office.15)
ms:contentKeyID: 48548549
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0ca9923b1604b17c1d7f64d2d968378fec4a8c24
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303316"
---
# <a name="querydefstateenum-enumeration-dao"></a><span data-ttu-id="9ee81-102">QueryDefStateEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="9ee81-102">QueryDefStateEnum enumeration (DAO)</span></span>


<span data-ttu-id="9ee81-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="9ee81-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9ee81-104">与 **Prepare** 属性一起用来指定在指定查询准备方式时所使用的方法。</span><span class="sxs-lookup"><span data-stu-id="9ee81-104">Used with the **Prepare** property to specify the method used to specify how a query should be prepared.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ee81-105">名称</span><span class="sxs-lookup"><span data-stu-id="9ee81-105">Name</span></span></p></th>
<th><p><span data-ttu-id="9ee81-106">值</span><span class="sxs-lookup"><span data-stu-id="9ee81-106">Value</span></span></p></th>
<th><p><span data-ttu-id="9ee81-107">说明</span><span class="sxs-lookup"><span data-stu-id="9ee81-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ee81-108">dbQPrepare</span><span class="sxs-lookup"><span data-stu-id="9ee81-108">dbQPrepare</span></span></p></td>
<td><p><span data-ttu-id="9ee81-109">1</span><span class="sxs-lookup"><span data-stu-id="9ee81-109">1</span></span></p></td>
<td><p><span data-ttu-id="9ee81-110">（默认值）准备语句（即，调用 ODBC SQLPrepare API）。</span><span class="sxs-lookup"><span data-stu-id="9ee81-110">(Default) The statement is prepared (that is, the ODBC SQLPrepare API is called).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee81-111">dbQUnprepare</span><span class="sxs-lookup"><span data-stu-id="9ee81-111">dbQUnprepare</span></span></p></td>
<td><p><span data-ttu-id="9ee81-112">双面</span><span class="sxs-lookup"><span data-stu-id="9ee81-112">2</span></span></p></td>
<td><p><span data-ttu-id="9ee81-113">不准备语句（即，调用 ODBC SQLExecDirect API）。</span><span class="sxs-lookup"><span data-stu-id="9ee81-113">The statement is not prepared (that is, the ODBC SQLExecDirect API is called).</span></span></p></td>
</tr>
</tbody>
</table>

