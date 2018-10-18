---
title: Parent 属性 (ADO MD)
TOCTitle: Parent Property (ADO MD)
ms:assetid: 62649da7-d35f-f11f-674c-28ce95abaf20
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249370(v=office.15)
ms:contentKeyID: 48545238
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 10c183c997a3c0b49c74e08f7ef29fbe8c274516
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603334"
---
# <a name="parent-property-ado-md"></a><span data-ttu-id="ee151-102">Parent 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="ee151-102">Parent Property (ADO MD)</span></span>


<span data-ttu-id="ee151-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ee151-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="ee151-104">指示层次结构中作为当前成员的父级的成员。</span><span class="sxs-lookup"><span data-stu-id="ee151-104">Indicates the member that is the parent of the current member in a hierarchy.</span></span>

<span data-ttu-id="ee151-105"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="ee151-105"><<<<<<< HEAD</span></span>
## <a name="return-values"></a><span data-ttu-id="ee151-106">返回值</span><span class="sxs-lookup"><span data-stu-id="ee151-106">Return Values</span></span>
=======
## <a name="return-values"></a><span data-ttu-id="ee151-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ee151-107">Return values</span></span>
>>>>>>> <span data-ttu-id="ee151-108">master</span><span class="sxs-lookup"><span data-stu-id="ee151-108">master</span></span>

<span data-ttu-id="ee151-109">返回一个 [Member](member-object-ado-md.md) 对象，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="ee151-109">Returns a [Member](member-object-ado-md.md) object and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee151-110">说明</span><span class="sxs-lookup"><span data-stu-id="ee151-110">Remarks</span></span>

<span data-ttu-id="ee151-p101">位于层次结构顶级（根）的成员没有父级。此属性仅在 **Level** 对象所属的 [Member](level-object-ado-md.md) 对象上受支持。通过属于 **Position** 对象的 [Member](position-object-ado-md.md) 对象引用此属性时，会发生错误。</span><span class="sxs-lookup"><span data-stu-id="ee151-p101">A member that is at the top level of a hierarchy (the root) has no parent. This property is supported only on **Member** objects belonging to a [Level](level-object-ado-md.md) object. An error occurs when this property is referenced from **Member** objects belonging to a [Position](position-object-ado-md.md) object.</span></span>

