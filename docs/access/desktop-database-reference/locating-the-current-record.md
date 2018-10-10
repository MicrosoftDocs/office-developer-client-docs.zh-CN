---
title: 定位当前记录
TOCTitle: Locating the Current Record
ms:assetid: b47fa9d6-0381-3d95-fb85-6bf1dd1071c9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249865(v=office.15)
ms:contentKeyID: 48547228
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 624c83e6b90b4e4ea7f9a4aad7c5f4784b104453
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466639"
---
# <a name="locating-the-current-record"></a><span data-ttu-id="698c1-102">定位当前记录</span><span class="sxs-lookup"><span data-stu-id="698c1-102">Locating the Current Record</span></span>


<span data-ttu-id="698c1-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="698c1-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="698c1-p101">游标在 **Recordset** 中的当前位置决定了当前记录位置。假如发出的命令返回了结果，则在调用 **Recordset** **Open** 方法时游标将自动位于第一个记录。因此，对于示例 **Recordset** ，游标将位于第一个记录"Uncle Bob's Organic Dried Pears"。</span><span class="sxs-lookup"><span data-stu-id="698c1-p101">The current position of the cursor in the **Recordset** delineates the current record position. Assuming that the command issued returns results, the cursor is automatically placed at the first record when the **Recordset** **Open** method is called. So, with the sample **Recordset**, the cursor would be on the first record, "Uncle Bob's Organic Dried Pears."</span></span>

