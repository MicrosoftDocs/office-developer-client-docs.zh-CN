---
title: Delete 方法 （ADO Parameters 集合）
TOCTitle: Delete method (ADO Parameters Collection)
ms:assetid: 03ffc24d-fea2-30fa-c8e9-43eb524fd51f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248804(v=office.15)
ms:contentKeyID: 48542998
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e075e176f1c007a258f6277147442223ae108b47
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704572"
---
# <a name="delete-method-ado-parameters-collection"></a><span data-ttu-id="39bae-102">Delete 方法 （ADO Parameters 集合）</span><span class="sxs-lookup"><span data-stu-id="39bae-102">Delete method (ADO Parameters Collection)</span></span>

<span data-ttu-id="39bae-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="39bae-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="39bae-104">用于从 [Parameters](parameters-collection-ado.md) 集合中删除对象。</span><span class="sxs-lookup"><span data-stu-id="39bae-104">Deletes an object from the [Parameters](parameters-collection-ado.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="39bae-105">语法</span><span class="sxs-lookup"><span data-stu-id="39bae-105">Syntax</span></span>

<span data-ttu-id="39bae-106">*参数*。删除*索引*</span><span class="sxs-lookup"><span data-stu-id="39bae-106">*Parameters*.Delete *Index*</span></span>

## <a name="parameters"></a><span data-ttu-id="39bae-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="39bae-107">Parameters</span></span>

|<span data-ttu-id="39bae-108">参数</span><span class="sxs-lookup"><span data-stu-id="39bae-108">Parameter</span></span>|<span data-ttu-id="39bae-109">说明</span><span class="sxs-lookup"><span data-stu-id="39bae-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="39bae-110">*Index*</span><span class="sxs-lookup"><span data-stu-id="39bae-110">*Index*</span></span> |<span data-ttu-id="39bae-111">**字符串** 值，包含要删除的对象的名称，或对象在集合中的序号位置（索引）。</span><span class="sxs-lookup"><span data-stu-id="39bae-111">A **String** value that contains the name of the object you want to delete, or the objects ordinal position (index) in the collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="39bae-112">说明</span><span class="sxs-lookup"><span data-stu-id="39bae-112">Remarks</span></span>

<span data-ttu-id="39bae-p101">通过对集合使用 **Delete** 方法，可以删除集合中的对象之一。此方法仅适用于 **Command** 对象的 [Parameters](command-object-ado.md) 集合。在调用 [Delete](parameter-object-ado.md) 方法时，必须使用 [Parameter](name-property-ado.md) 对象的 **Name** 属性或其集合索引，对象变量不是有效的参数。</span><span class="sxs-lookup"><span data-stu-id="39bae-p101">Using the **Delete** method on a collection lets you remove one of the objects in the collection. This method is available only on the **Parameters** collection of a [Command](command-object-ado.md) object. You must use the [Parameter](parameter-object-ado.md) object's [Name](name-property-ado.md) property or its collection index when calling the **Delete** method — an object variable is not a valid argument.</span></span>

