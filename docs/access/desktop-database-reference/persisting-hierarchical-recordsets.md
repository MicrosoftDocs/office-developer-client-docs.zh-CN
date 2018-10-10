---
title: 持久化分层记录集
TOCTitle: Persisting Hierarchical Recordsets
ms:assetid: 28f48d4a-1c32-7b60-cd65-51fb87c5380e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249048(v=office.15)
ms:contentKeyID: 48543872
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 36c6c1d99b01918d848dfde06c26ad6851b1db43
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467329"
---
# <a name="persisting-hierarchical-recordsets"></a><span data-ttu-id="1813e-102">持久化分层记录集</span><span class="sxs-lookup"><span data-stu-id="1813e-102">Persisting Hierarchical Recordsets</span></span>


<span data-ttu-id="1813e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1813e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1813e-p101">通过调用 [Save](save-method-ado.md) 方法，可以将分层 **Recordset** 以 ADTG 或 XML 格式保存在文件中。不过，在以 XML 格式保存分层 **Recordset** 时，存在两个限制条件：一是如果分层 **Recordset** 中包含未决更新，则不能保存为 XML 格式；二是不能保存参数化分层 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="1813e-p101">You can save a hierarchical **Recordset** to a file in either ADTG or XML format by calling the [Save](save-method-ado.md) method. However, two limitations apply when saving hierarchical **Recordset**s in XML format: You cannot save in XML if the hierarchical **Recordset** contains pending updates, and you cannot save a parameterized hierarchical **Recordset**.</span></span>

<span data-ttu-id="1813e-106">有关数据定形提供程序的详细信息，请参阅 [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) (ADO) 和"Data Shaping Service for OLE DB(OLE DB)"。</span><span class="sxs-lookup"><span data-stu-id="1813e-106">For more information about the Data Shaping provider, see [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) (ADO) and The Data Shaping Service for OLE DB(OLE DB).</span></span>

