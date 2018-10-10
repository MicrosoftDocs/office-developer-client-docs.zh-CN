---
title: ActiveCommand 属性 (ADO)
TOCTitle: ActiveCommand Property (ADO)
ms:assetid: 41c19008-cbf7-ade9-b4ab-e908a16784ac
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249190(v=office.15)
ms:contentKeyID: 48544459
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f01ae4c821d8beb6c8de84c7ed671a373d7372c9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468399"
---
# <a name="activecommand-property-ado"></a><span data-ttu-id="569d1-102">ActiveCommand 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="569d1-102">ActiveCommand Property (ADO)</span></span>


<span data-ttu-id="569d1-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="569d1-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="569d1-104">指示创建关联的 [Recordset](command-object-ado.md) 对象的 [Command](recordset-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="569d1-104">Indicates the [Command](command-object-ado.md) object that created the associated [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="569d1-105">返回值</span><span class="sxs-lookup"><span data-stu-id="569d1-105">Return Value</span></span>

<span data-ttu-id="569d1-p101">返回一个包含 **Command** 对象的 **Variant** 。默认值为一个空对象引用。</span><span class="sxs-lookup"><span data-stu-id="569d1-p101">Returns a **Variant** that contains a **Command** object. Default is a null object reference.</span></span>

## <a name="remarks"></a><span data-ttu-id="569d1-108">备注</span><span class="sxs-lookup"><span data-stu-id="569d1-108">Remarks</span></span>

<span data-ttu-id="569d1-109">**ActiveCommand** 为只读属性。</span><span class="sxs-lookup"><span data-stu-id="569d1-109">The **ActiveCommand** property is read-only.</span></span>

<span data-ttu-id="569d1-110">如果未使用 **Command** 对象创建当前的 **Recordset** ，则会返回一个 **Null** 对象引用。</span><span class="sxs-lookup"><span data-stu-id="569d1-110">If a **Command** object was not used to create the current **Recordset**, then a **Null** object reference is returned.</span></span>

<span data-ttu-id="569d1-111">当仅给定了生成的 **Recordset** 对象时，可以使用此属性来查找关联的 **Command** 对象。</span><span class="sxs-lookup"><span data-stu-id="569d1-111">Use this property to find the associated **Command** object when you are given only the resulting **Recordset** object.</span></span>

