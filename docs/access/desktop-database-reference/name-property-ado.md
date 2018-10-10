---
title: Name 属性 (ADO)
TOCTitle: Name Property (ADO)
ms:assetid: 4b19bd08-ac3c-86f0-471d-06a37a0d4f89
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249234(v=office.15)
ms:contentKeyID: 48544683
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 132d00af1aecf7ec1ae8fbdb7855a10dd99c7f4f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468344"
---
# <a name="name-property-ado"></a><span data-ttu-id="9c625-102">Name 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="9c625-102">Name Property (ADO)</span></span>


<span data-ttu-id="9c625-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9c625-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9c625-104">指示对象的名称。</span><span class="sxs-lookup"><span data-stu-id="9c625-104">Indicates the name of an object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="9c625-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="9c625-105">Settings and Return Values</span></span>

<span data-ttu-id="9c625-106">设置或返回一个指示对象名称的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="9c625-106">Sets or returns a **String** value that indicates the name of an object.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c625-107">备注</span><span class="sxs-lookup"><span data-stu-id="9c625-107">Remarks</span></span>

<span data-ttu-id="9c625-108">使用 **Name** 属性可指定名称或检索 **Command** 、 **Property** 、 **Field** 或 **Parameter** 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="9c625-108">Use the **Name** property to assign a name to or retrieve the name of a **Command**, **Property**, **Field**, or **Parameter** object.</span></span>

<span data-ttu-id="9c625-109">该值在 **Command** 对象上为可读/写，在 **Property** 对象上为只读。</span><span class="sxs-lookup"><span data-stu-id="9c625-109">The value is read/write on a **Command** object and read-only on a **Property** object.</span></span>

<span data-ttu-id="9c625-p101">对于 **Field** 对象， **Name** 通常为只读。然而，对于已追加到 **Record** 的 [Fields](fields-collection-ado.md) 集合的新 [Field](record-object-ado.md) 对象，只有在已指定 **Field** 的 [Value](value-property-ado.md) 属性并且数据提供程序已通过调用 **Fields** 集合的 **Update** 方法成功添加新 [Field](update-method-ado.md) 之后， **Name** 才为可读/写。</span><span class="sxs-lookup"><span data-stu-id="9c625-p101">For a **Field** object, **Name** is normally read-only. However, for new **Field** objects that have been appended to the [Fields](fields-collection-ado.md) collection of a [Record](record-object-ado.md), **Name** is read/write only after the [Value](value-property-ado.md) property for the **Field** has been specified and the data provider has successfully added the new **Field** by calling the [Update](update-method-ado.md) method of the **Fields** collection.</span></span>

<span data-ttu-id="9c625-p102">对于尚未追加到 **Parameters** 集合的 [Parameter](parameters-collection-ado.md) ， **Name** 属性为可读/写属性。对于已追加的 **Parameter** 对象以及其他所有对象， **Name** 属性为只读属性。Names 在集合中不必唯一。</span><span class="sxs-lookup"><span data-stu-id="9c625-p102">For **Parameter** objects not yet appended to the [Parameters](parameters-collection-ado.md) collection, the **Name** property is read/write. For appended **Parameter** objects and all other objects, the **Name** property is read-only. Names do not have to be unique within a collection.</span></span>

<span data-ttu-id="9c625-115">可以通过序号引用来检索对象的 **Name** 属性，然后可以直接通过名称引用该对象。</span><span class="sxs-lookup"><span data-stu-id="9c625-115">You can retrieve the **Name** property of an object by an ordinal reference, after which you can refer to the object directly by name.</span></span> <span data-ttu-id="9c625-116">例如，如果 rstMain.Properties(20)。名称生成可更新性、 您随后可以参考此属性，如生成可更新性、 您随后可以参考 rstMain.Properties("Updatability") 作为此属性。</span><span class="sxs-lookup"><span data-stu-id="9c625-116">For example, if rstMain.Properties(20).Name yields Updatability , you can subsequently refer to this property as yields Updatability , you can subsequently refer to this property as rstMain.Properties("Updatability") .</span></span>

