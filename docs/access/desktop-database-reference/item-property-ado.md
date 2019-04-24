---
title: Item 属性 (ADO)
TOCTitle: Item property (ADO)
ms:assetid: 793c305f-0e5b-a529-e21f-b7ab0843ed49
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249499(v=office.15)
ms:contentKeyID: 48545767
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9cc38101cb17c52bf2c8c08c08c14163c3772b2f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290791"
---
# <a name="item-property-ado"></a><span data-ttu-id="8a491-102">Item 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="8a491-102">Item property (ADO)</span></span>

<span data-ttu-id="8a491-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="8a491-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8a491-104">按名称或序号指示集合的特定成员。</span><span class="sxs-lookup"><span data-stu-id="8a491-104">Indicates a specific member of a collection, by name or ordinal number.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a491-105">语法</span><span class="sxs-lookup"><span data-stu-id="8a491-105">Syntax</span></span>

<span data-ttu-id="8a491-106">Set*对象* = *集合*。Item (Index)</span><span class="sxs-lookup"><span data-stu-id="8a491-106">Set*object* = *collection*.Item ( Index )</span></span>

## <a name="return-value"></a><span data-ttu-id="8a491-107">返回值</span><span class="sxs-lookup"><span data-stu-id="8a491-107">Return value</span></span>

<span data-ttu-id="8a491-108">返回对象引用。</span><span class="sxs-lookup"><span data-stu-id="8a491-108">Returns an object reference.</span></span>

## <a name="parameters"></a><span data-ttu-id="8a491-109">参数</span><span class="sxs-lookup"><span data-stu-id="8a491-109">Parameters</span></span>

|<span data-ttu-id="8a491-110">参数</span><span class="sxs-lookup"><span data-stu-id="8a491-110">Parameter</span></span>|<span data-ttu-id="8a491-111">描述</span><span class="sxs-lookup"><span data-stu-id="8a491-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="8a491-112">*Index*</span><span class="sxs-lookup"><span data-stu-id="8a491-112">*Index*</span></span> |<span data-ttu-id="8a491-113">一个 **Variant** 表达式，其值为集合中对象的名称或序号。</span><span class="sxs-lookup"><span data-stu-id="8a491-113">A **Variant** expression that evaluates either to the name or to the ordinal number of an object in a collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8a491-114">注解</span><span class="sxs-lookup"><span data-stu-id="8a491-114">Remarks</span></span>

<span data-ttu-id="8a491-p101">使用 **Item** 属性可返回集合中的特定对象。如果 **Item** 无法在集合中找到对应于 *Index* 参数的对象，则将发生错误。此外，有些集合不支持命名对象；对于这些集合，必须使用序号引用。</span><span class="sxs-lookup"><span data-stu-id="8a491-p101">Use the **Item** property to return a specific object in a collection. If **Item** cannot find an object in the collection corresponding to the *Index* argument, an error occurs. Also, some collections don't support named objects; for these collections, you must use ordinal number references.</span></span>

<span data-ttu-id="8a491-118">**Item** 属性是所有集合的默认属性；因此，以下语法格式可互换：</span><span class="sxs-lookup"><span data-stu-id="8a491-118">The **Item** property is the default property for all collections; therefore, the following syntax forms are interchangeable:</span></span>

```vb
    collection.Item (Index)
    collection (Index)
```
