---
title: Item 属性 (ADO)
TOCTitle: Item property (ADO)
ms:assetid: 793c305f-0e5b-a529-e21f-b7ab0843ed49
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249499(v=office.15)
ms:contentKeyID: 48545767
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 73e6240b92a34a6ff1d215cd3211a844f10fe766
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868306"
---
# <a name="item-property-ado"></a><span data-ttu-id="fefa2-102">Item 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="fefa2-102">Item property (ADO)</span></span>

<span data-ttu-id="fefa2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fefa2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fefa2-104">按名称或序号指示集合的特定成员。</span><span class="sxs-lookup"><span data-stu-id="fefa2-104">Indicates a specific member of a collection, by name or ordinal number.</span></span>

## <a name="syntax"></a><span data-ttu-id="fefa2-105">语法</span><span class="sxs-lookup"><span data-stu-id="fefa2-105">Syntax</span></span>

<span data-ttu-id="fefa2-106">将*对象*设置 = *集合*。Item (Index)</span><span class="sxs-lookup"><span data-stu-id="fefa2-106">Set*object* = *collection*.Item ( Index )</span></span>

## <a name="return-value"></a><span data-ttu-id="fefa2-107">返回值</span><span class="sxs-lookup"><span data-stu-id="fefa2-107">Return value</span></span>

<span data-ttu-id="fefa2-108">返回对象引用。</span><span class="sxs-lookup"><span data-stu-id="fefa2-108">Returns an object reference.</span></span>

## <a name="parameters"></a><span data-ttu-id="fefa2-109">参数</span><span class="sxs-lookup"><span data-stu-id="fefa2-109">Parameters</span></span>

- <span data-ttu-id="fefa2-110">*Index*</span><span class="sxs-lookup"><span data-stu-id="fefa2-110">*Index*</span></span>

- <span data-ttu-id="fefa2-111">一个 **Variant** 表达式，其值为集合中对象的名称或序号。</span><span class="sxs-lookup"><span data-stu-id="fefa2-111">A **Variant** expression that evaluates either to the name or to the ordinal number of an object in a collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="fefa2-112">备注</span><span class="sxs-lookup"><span data-stu-id="fefa2-112">Remarks</span></span>

<span data-ttu-id="fefa2-113">使用 **Item** 属性可返回集合中的特定对象。</span><span class="sxs-lookup"><span data-stu-id="fefa2-113">Use the **Item** property to return a specific object in a collection.</span></span> <span data-ttu-id="fefa2-114">如果**项目**找不到对象对应于*Index*参数集合中，将导致出错。</span><span class="sxs-lookup"><span data-stu-id="fefa2-114">If **Item** cannot find an object in the collection corresponding to the *Index* argument, an error occurs.</span></span> <span data-ttu-id="fefa2-115">此外，有些集合不支持命名对象；对于这些集合，必须使用序号引用。</span><span class="sxs-lookup"><span data-stu-id="fefa2-115">Also, some collections don't support named objects; for these collections, you must use ordinal number references.</span></span>

<span data-ttu-id="fefa2-116">**Item** 属性是所有集合的默认属性；因此，以下语法格式可互换：</span><span class="sxs-lookup"><span data-stu-id="fefa2-116">The **Item** property is the default property for all collections; therefore, the following syntax forms are interchangeable:</span></span>

```vb
    collection.Item (Index)
    collection (Index)
```
