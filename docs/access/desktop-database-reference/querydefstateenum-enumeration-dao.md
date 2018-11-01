---
title: QueryDefStateEnum Enumeration (DAO)
TOCTitle: QueryDefStateEnum Enumeration
ms:assetid: edfa3085-f8b4-b813-0828-2ba2a9dc0b9d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836359(v=office.15)
ms:contentKeyID: 48548549
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b368079aeb668c9ae72e3955f55159ab2c72a53e
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25882565"
---
# <a name="querydefstateenum-enumeration-dao"></a><span data-ttu-id="0f308-102">QueryDefStateEnum Enumeration (DAO)</span><span class="sxs-lookup"><span data-stu-id="0f308-102">QueryDefStateEnum Enumeration (DAO)</span></span>


<span data-ttu-id="0f308-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0f308-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0f308-104">与 **Prepare** 属性一起用来指定在指定查询准备方式时所使用的方法。</span><span class="sxs-lookup"><span data-stu-id="0f308-104">Used with the **Prepare** property to specify the method used to specify how a query should be prepared.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0f308-105">名称</span><span class="sxs-lookup"><span data-stu-id="0f308-105">Name</span></span></p></th>
<th><p><span data-ttu-id="0f308-106">值</span><span class="sxs-lookup"><span data-stu-id="0f308-106">Value</span></span></p></th>
<th><p><span data-ttu-id="0f308-107">说明</span><span class="sxs-lookup"><span data-stu-id="0f308-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f308-108">dbQPrepare</span><span class="sxs-lookup"><span data-stu-id="0f308-108">dbQPrepare</span></span></p></td>
<td><p><span data-ttu-id="0f308-109">1</span><span class="sxs-lookup"><span data-stu-id="0f308-109">1</span></span></p></td>
<td><p><span data-ttu-id="0f308-110">（默认值）准备语句（即，调用 ODBC SQLPrepare API）。</span><span class="sxs-lookup"><span data-stu-id="0f308-110">(Default) The statement is prepared (that is, the ODBC SQLPrepare API is called).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f308-111">dbQUnprepare</span><span class="sxs-lookup"><span data-stu-id="0f308-111">dbQUnprepare</span></span></p></td>
<td><p><span data-ttu-id="0f308-112">2</span><span class="sxs-lookup"><span data-stu-id="0f308-112">2</span></span></p></td>
<td><p><span data-ttu-id="0f308-113">不准备语句（即，调用 ODBC SQLExecDirect API）。</span><span class="sxs-lookup"><span data-stu-id="0f308-113">The statement is not prepared (that is, the ODBC SQLExecDirect API is called).</span></span></p></td>
</tr>
</tbody>
</table>

