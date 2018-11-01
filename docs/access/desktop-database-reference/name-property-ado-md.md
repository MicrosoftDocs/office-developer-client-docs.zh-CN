---
title: Name 属性 (ADO MD)
TOCTitle: Name Property (ADO MD)
ms:assetid: 31ea6dad-c464-3af7-4b7a-086900656c2c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249093(v=office.15)
ms:contentKeyID: 48544065
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 63e098a8b97bb37fad2ef256affb2da142daf434
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25878645"
---
# <a name="name-property-ado-md"></a><span data-ttu-id="b133b-102">Name 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="b133b-102">Name Property (ADO MD)</span></span>


<span data-ttu-id="b133b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b133b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b133b-104">指示对象的名称。</span><span class="sxs-lookup"><span data-stu-id="b133b-104">Indicates the name of an object.</span></span>

## <a name="return-values"></a><span data-ttu-id="b133b-105">返回值</span><span class="sxs-lookup"><span data-stu-id="b133b-105">Return values</span></span>

<span data-ttu-id="b133b-106">返回一个 **String** 值，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="b133b-106">Returns a **String** and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="b133b-107">备注</span><span class="sxs-lookup"><span data-stu-id="b133b-107">Remarks</span></span>

<span data-ttu-id="b133b-p101">可按序号引用来检索对象的 **Name** 属性，此后就可按名称直接引用该对象。例如，如果 cdf.CubeDefs(0).Name 得到"Bobs Video Store"，则可按 cdf.CubeDefs("Bobs Video Store") 形式引用此 [CubeDef](cubedef-object-ado-md.md)。</span><span class="sxs-lookup"><span data-stu-id="b133b-p101">You can retrieve the **Name** property of an object by an ordinal reference, after which you can refer to the object directly by name. For example, if cdf.CubeDefs(0).Name yields "Bobs Video Store", you can refer to this [CubeDef](cubedef-object-ado-md.md) as cdf.CubeDefs("Bobs Video Store").</span></span>

