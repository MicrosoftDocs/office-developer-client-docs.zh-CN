---
title: ActiveCommand 属性 (ADO)
TOCTitle: ActiveCommand property (ADO)
ms:assetid: 41c19008-cbf7-ade9-b4ab-e908a16784ac
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249190(v=office.15)
ms:contentKeyID: 48544459
ms.date: 10/17/2018
mtps_version: v=office.15
ms.openlocfilehash: 473a0b99310d2eb5e050ed50f1e331cb65174ae8
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869559"
---
# <a name="activecommand-property-ado"></a><span data-ttu-id="97d10-102">ActiveCommand 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="97d10-102">ActiveCommand property (ADO)</span></span>

<span data-ttu-id="97d10-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="97d10-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="97d10-104">指示创建关联的 [Recordset](command-object-ado.md) 对象的 [Command](recordset-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="97d10-104">Indicates the [Command](command-object-ado.md) object that created the associated [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="97d10-105">返回值</span><span class="sxs-lookup"><span data-stu-id="97d10-105">Return value</span></span>

<span data-ttu-id="97d10-p101">返回一个包含 **Command** 对象的 **Variant** 。默认值为一个空对象引用。</span><span class="sxs-lookup"><span data-stu-id="97d10-p101">Returns a **Variant** that contains a **Command** object. Default is a null object reference.</span></span>

## <a name="remarks"></a><span data-ttu-id="97d10-108">备注</span><span class="sxs-lookup"><span data-stu-id="97d10-108">Remarks</span></span>

<span data-ttu-id="97d10-109">**ActiveCommand** 为只读属性。</span><span class="sxs-lookup"><span data-stu-id="97d10-109">The **ActiveCommand** property is read-only.</span></span>

<span data-ttu-id="97d10-110">如果不使用**Command**对象创建当前的**记录集**，则返回一个**Null**对象引用。</span><span class="sxs-lookup"><span data-stu-id="97d10-110">If a **Command** object was not used to create the current **Recordset**, a **Null** object reference is returned.</span></span>

<span data-ttu-id="97d10-111">当仅给定了生成的 **Recordset** 对象时，可以使用此属性来查找关联的 **Command** 对象。</span><span class="sxs-lookup"><span data-stu-id="97d10-111">Use this property to find the associated **Command** object when you are given only the resulting **Recordset** object.</span></span>

