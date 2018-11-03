---
title: CursorDriverEnum 枚举 (DAO)
TOCTitle: CursorDriverEnum enumeration
ms:assetid: d0312ece-c30a-7d61-d5f3-75edf0d0afc8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834707(v=office.15)
ms:contentKeyID: 48547832
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d8fac1dbf3da20e3af476ec4bcaac6046d834881
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944100"
---
# <a name="cursordriverenum-enumeration-dao"></a><span data-ttu-id="db424-102">CursorDriverEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="db424-102">CursorDriverEnum enumeration (DAO)</span></span>

<span data-ttu-id="db424-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="db424-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="db424-104">指定游标驱动程序的类型。</span><span class="sxs-lookup"><span data-stu-id="db424-104">Specifies the type of cursor driver.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="db424-105">名称</span><span class="sxs-lookup"><span data-stu-id="db424-105">Name</span></span></p></th>
<th><p><span data-ttu-id="db424-106">值</span><span class="sxs-lookup"><span data-stu-id="db424-106">Value</span></span></p></th>
<th><p><span data-ttu-id="db424-107">说明</span><span class="sxs-lookup"><span data-stu-id="db424-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db424-108">dbUseClientBatchCursor</span><span class="sxs-lookup"><span data-stu-id="db424-108">dbUseClientBatchCursor</span></span></p></td>
<td><p><span data-ttu-id="db424-109">3</span><span class="sxs-lookup"><span data-stu-id="db424-109">3</span></span></p></td>
<td><p><span data-ttu-id="db424-p101">总是使用 FoxPro 游标库。执行批更新需要此选项。</span><span class="sxs-lookup"><span data-stu-id="db424-p101">Always uses the FoxPro Cursor Library. This option is required for performing batch updates.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db424-112">dbUseDefaultCursor</span><span class="sxs-lookup"><span data-stu-id="db424-112">dbUseDefaultCursor</span></span></p></td>
<td><p><span data-ttu-id="db424-113">-1</span><span class="sxs-lookup"><span data-stu-id="db424-113">-1</span></span></p></td>
<td><p><span data-ttu-id="db424-114">（默认值）如果服务器支持，则使用服务器端游标；否则使用 ODBC 游标库。</span><span class="sxs-lookup"><span data-stu-id="db424-114">(Default) Uses server-side cursors if the server supports them; otherwise uses the ODBC Cursor Library.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db424-115">dbUseNoCursor</span><span class="sxs-lookup"><span data-stu-id="db424-115">dbUseNoCursor</span></span></p></td>
<td><p><span data-ttu-id="db424-116">4</span><span class="sxs-lookup"><span data-stu-id="db424-116">4</span></span></p></td>
<td><p><span data-ttu-id="db424-117">打开所有游标 （即， <strong>Recordset</strong>对象） 作为仅向前类型，只读的行集大小为 1。</span><span class="sxs-lookup"><span data-stu-id="db424-117">Opens all cursors (that is, <strong>Recordset</strong> objects) as forward-only type, read-only, with a rowset size of 1.</span></span> <span data-ttu-id="db424-118">也称为&quot;是无游标查询。&quot;</span><span class="sxs-lookup"><span data-stu-id="db424-118">Also known as &quot;cursorless queries.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db424-119">dbUseODBCCursor</span><span class="sxs-lookup"><span data-stu-id="db424-119">dbUseODBCCursor</span></span></p></td>
<td><p><span data-ttu-id="db424-120">1</span><span class="sxs-lookup"><span data-stu-id="db424-120">1</span></span></p></td>
<td><p><span data-ttu-id="db424-p103">总是使用 ODBC 游标库。对于小型结果集，此选项可提供更好的性能，但对于较大的结果集，性能会快速下降。</span><span class="sxs-lookup"><span data-stu-id="db424-p103">Always uses the ODBC Cursor Library. This option provides better performance for small result sets, but degrades quickly for larger result sets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db424-123">dbUseServerCursor</span><span class="sxs-lookup"><span data-stu-id="db424-123">dbUseServerCursor</span></span></p></td>
<td><p><span data-ttu-id="db424-124">2</span><span class="sxs-lookup"><span data-stu-id="db424-124">2</span></span></p></td>
<td><p><span data-ttu-id="db424-p104">总是使用服务器端游标。对于大多数大型操作，此选项可提供更好的性能，但可能造成网络拥塞。</span><span class="sxs-lookup"><span data-stu-id="db424-p104">Always uses server-side cursors. For most large operations this option provides better performance, but might cause more network traffic.</span></span></p></td>
</tr>
</tbody>
</table>

