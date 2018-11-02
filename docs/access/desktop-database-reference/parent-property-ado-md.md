---
title: Parent 属性 (ADO MD)
TOCTitle: Parent property (ADO MD)
ms:assetid: 62649da7-d35f-f11f-674c-28ce95abaf20
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249370(v=office.15)
ms:contentKeyID: 48545238
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c1da5b763d85fc9975a42e357860d87ce64cf618
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930586"
---
# <a name="parent-property-ado-md"></a><span data-ttu-id="8749a-102">Parent 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="8749a-102">Parent property (ADO MD)</span></span>


<span data-ttu-id="8749a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8749a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8749a-104">指示层次结构中作为当前成员的父级的成员。</span><span class="sxs-lookup"><span data-stu-id="8749a-104">Indicates the member that is the parent of the current member in a hierarchy.</span></span>

## <a name="return-values"></a><span data-ttu-id="8749a-105">返回值</span><span class="sxs-lookup"><span data-stu-id="8749a-105">Return values</span></span>

<span data-ttu-id="8749a-106">返回一个 [Member](member-object-ado-md.md) 对象，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="8749a-106">Returns a [Member](member-object-ado-md.md) object and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="8749a-107">说明</span><span class="sxs-lookup"><span data-stu-id="8749a-107">Remarks</span></span>

<span data-ttu-id="8749a-p101">位于层次结构顶级（根）的成员没有父级。此属性仅在 **Level** 对象所属的 [Member](level-object-ado-md.md) 对象上受支持。通过属于 **Position** 对象的 [Member](position-object-ado-md.md) 对象引用此属性时，会发生错误。</span><span class="sxs-lookup"><span data-stu-id="8749a-p101">A member that is at the top level of a hierarchy (the root) has no parent. This property is supported only on **Member** objects belonging to a [Level](level-object-ado-md.md) object. An error occurs when this property is referenced from **Member** objects belonging to a [Position](position-object-ado-md.md) object.</span></span>

