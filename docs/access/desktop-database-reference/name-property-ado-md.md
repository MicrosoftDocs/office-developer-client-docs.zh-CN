---
title: Name 属性 (ADO MD)
TOCTitle: Name property (ADO MD)
ms:assetid: 31ea6dad-c464-3af7-4b7a-086900656c2c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249093(v=office.15)
ms:contentKeyID: 48544065
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e4e27870a0c1dbb38b7c0be31c439a95f6aae671
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288656"
---
# <a name="name-property-ado-md"></a><span data-ttu-id="44b77-102">Name 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="44b77-102">Name property (ADO MD)</span></span>


<span data-ttu-id="44b77-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="44b77-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="44b77-104">指示对象的名称。</span><span class="sxs-lookup"><span data-stu-id="44b77-104">Indicates the name of an object.</span></span>

## <a name="return-values"></a><span data-ttu-id="44b77-105">返回值</span><span class="sxs-lookup"><span data-stu-id="44b77-105">Return values</span></span>

<span data-ttu-id="44b77-106">返回一个 **String** 值，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="44b77-106">Returns a **String** and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="44b77-107">注解</span><span class="sxs-lookup"><span data-stu-id="44b77-107">Remarks</span></span>

<span data-ttu-id="44b77-p101">可按序号引用来检索对象的 **Name** 属性，此后就可按名称直接引用该对象。例如，如果 cdf.CubeDefs(0).Name 得到“Bobs Video Store”，则可按 cdf.CubeDefs("Bobs Video Store") 形式引用此 [CubeDef](cubedef-object-ado-md.md)。</span><span class="sxs-lookup"><span data-stu-id="44b77-p101">You can retrieve the **Name** property of an object by an ordinal reference, after which you can refer to the object directly by name. For example, if cdf.CubeDefs(0).Name yields "Bobs Video Store", you can refer to this [CubeDef](cubedef-object-ado-md.md) as cdf.CubeDefs("Bobs Video Store").</span></span>

