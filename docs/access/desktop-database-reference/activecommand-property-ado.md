---
title: ActiveCommand 属性 (ADO)
TOCTitle: ActiveCommand property (ADO)
ms:assetid: 41c19008-cbf7-ade9-b4ab-e908a16784ac
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249190(v=office.15)
ms:contentKeyID: 48544459
ms.date: 10/17/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 18fa38176f7174f27b46604c6182dfbdaa422f06
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705293"
---
# <a name="activecommand-property-ado"></a><span data-ttu-id="3b90d-102">ActiveCommand 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="3b90d-102">ActiveCommand property (ADO)</span></span>

<span data-ttu-id="3b90d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3b90d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3b90d-104">指示创建关联的 [Recordset](command-object-ado.md) 对象的 [Command](recordset-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="3b90d-104">Indicates the [Command](command-object-ado.md) object that created the associated [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="3b90d-105">返回值</span><span class="sxs-lookup"><span data-stu-id="3b90d-105">Return value</span></span>

<span data-ttu-id="3b90d-p101">返回一个包含 **Command** 对象的 **Variant** 。默认值为一个空对象引用。</span><span class="sxs-lookup"><span data-stu-id="3b90d-p101">Returns a **Variant** that contains a **Command** object. Default is a null object reference.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b90d-108">备注</span><span class="sxs-lookup"><span data-stu-id="3b90d-108">Remarks</span></span>

<span data-ttu-id="3b90d-109">**ActiveCommand** 为只读属性。</span><span class="sxs-lookup"><span data-stu-id="3b90d-109">The **ActiveCommand** property is read-only.</span></span>

<span data-ttu-id="3b90d-110">如果不使用**Command**对象创建当前的**记录集**，则返回一个**Null**对象引用。</span><span class="sxs-lookup"><span data-stu-id="3b90d-110">If a **Command** object was not used to create the current **Recordset**, a **Null** object reference is returned.</span></span>

<span data-ttu-id="3b90d-111">当仅给定了生成的 **Recordset** 对象时，可以使用此属性来查找关联的 **Command** 对象。</span><span class="sxs-lookup"><span data-stu-id="3b90d-111">Use this property to find the associated **Command** object when you are given only the resulting **Recordset** object.</span></span>

