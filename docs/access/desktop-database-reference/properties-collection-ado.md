---
title: Properties 集合 (ADO)
TOCTitle: Properties collection (ADO)
ms:assetid: 4d662790-1252-c930-e6f9-edf6a38636af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249245(v=office.15)
ms:contentKeyID: 48544729
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231104
f1_categories:
- Office.Version=v15
ms.openlocfilehash: a4e683781fc2c508b34717447fcac6f02f54d6ff
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997845"
---
# <a name="properties-collection-ado"></a><span data-ttu-id="cd287-102">Properties 集合 (ADO)</span><span class="sxs-lookup"><span data-stu-id="cd287-102">Properties collection (ADO)</span></span>

<span data-ttu-id="cd287-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cd287-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cd287-104">包含特定对象实例的所有 [Property](property-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="cd287-104">Contains all the [Property](property-object-ado.md) objects for a specific instance of an object.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd287-105">说明</span><span class="sxs-lookup"><span data-stu-id="cd287-105">Remarks</span></span>

<span data-ttu-id="cd287-p101">某些 ADO 对象具有由 **Property** 对象组成的 **Properties** 集合。每个 **Property** 对象对应于特定于提供程序的 ADO 对象的一个特性。</span><span class="sxs-lookup"><span data-stu-id="cd287-p101">Some ADO objects have a **Properties** collection made up of **Property** objects. Each **Property** object corresponds to a characteristic of the ADO object specific to the provider.</span></span>

> [!NOTE]
> <span data-ttu-id="cd287-108">[!注释] 有关如何使用 [Property](property-object-ado.md) 对象的更详细说明，请参阅 **Property** 对象主题。</span><span class="sxs-lookup"><span data-stu-id="cd287-108">See the [Property](property-object-ado.md) object topic for a more detailed explanation of how to use **Property** objects.</span></span>

<span data-ttu-id="cd287-109">关闭 **Recordset** 时， **Recordset** 对象的 **动态属性** 将超出范围（不可用）。</span><span class="sxs-lookup"><span data-stu-id="cd287-109">The **Dynamic Properties** of the **Recordset** object go out of scope (become unavailable) when the **Recordset** is closed.</span></span>

