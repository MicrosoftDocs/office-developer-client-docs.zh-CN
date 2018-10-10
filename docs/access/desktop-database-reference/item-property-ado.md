---
title: Item 属性 (ADO)
TOCTitle: Item Property (ADO)
ms:assetid: 793c305f-0e5b-a529-e21f-b7ab0843ed49
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249499(v=office.15)
ms:contentKeyID: 48545767
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 29453ac2801f606640fd6d9506a8ee1ee8625396
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465800"
---
# <a name="item-property-ado"></a><span data-ttu-id="aa45d-102">Item 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="aa45d-102">Item Property (ADO)</span></span>

<span data-ttu-id="aa45d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="aa45d-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="aa45d-104">按名称或序号指示集合的特定成员。</span><span class="sxs-lookup"><span data-stu-id="aa45d-104">Indicates a specific member of a collection, by name or ordinal number.</span></span>

## <a name="syntax"></a><span data-ttu-id="aa45d-105">语法</span><span class="sxs-lookup"><span data-stu-id="aa45d-105">Syntax</span></span>

<span data-ttu-id="aa45d-106">将*对象*设置 = *集合*。Item (Index)</span><span class="sxs-lookup"><span data-stu-id="aa45d-106">Set*object* = *collection*.Item ( Index )</span></span>

## <a name="return-value"></a><span data-ttu-id="aa45d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="aa45d-107">Return Value</span></span>

<span data-ttu-id="aa45d-108">返回对象引用。</span><span class="sxs-lookup"><span data-stu-id="aa45d-108">Returns an object reference.</span></span>

## <a name="parameters"></a><span data-ttu-id="aa45d-109">参数</span><span class="sxs-lookup"><span data-stu-id="aa45d-109">Parameters</span></span>

- <span data-ttu-id="aa45d-110">*Index*</span><span class="sxs-lookup"><span data-stu-id="aa45d-110">*Index*</span></span>

- <span data-ttu-id="aa45d-111">一个 **Variant** 表达式，其值为集合中对象的名称或序号。</span><span class="sxs-lookup"><span data-stu-id="aa45d-111">A **Variant** expression that evaluates either to the name or to the ordinal number of an object in a collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa45d-112">备注</span><span class="sxs-lookup"><span data-stu-id="aa45d-112">Remarks</span></span>

<span data-ttu-id="aa45d-113">使用 **Item** 属性可返回集合中的特定对象。</span><span class="sxs-lookup"><span data-stu-id="aa45d-113">Use the **Item** property to return a specific object in a collection.</span></span> <span data-ttu-id="aa45d-114">如果**项目**找不到对象对应于*Index*参数集合中，将导致出错。</span><span class="sxs-lookup"><span data-stu-id="aa45d-114">If **Item** cannot find an object in the collection corresponding to the *Index* argument, an error occurs.</span></span> <span data-ttu-id="aa45d-115">此外，有些集合不支持命名对象；对于这些集合，必须使用序号引用。</span><span class="sxs-lookup"><span data-stu-id="aa45d-115">Also, some collections don't support named objects; for these collections, you must use ordinal number references.</span></span>

<span data-ttu-id="aa45d-116">**Item** 属性是所有集合的默认属性；因此，以下语法格式可互换：</span><span class="sxs-lookup"><span data-stu-id="aa45d-116">The **Item** property is the default property for all collections; therefore, the following syntax forms are interchangeable:</span></span>

```vb
    collection.Item (Index)
    collection (Index)
```
