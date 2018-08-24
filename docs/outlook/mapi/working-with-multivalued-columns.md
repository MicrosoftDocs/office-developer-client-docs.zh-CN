---
title: 处理多值列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 911a41c3-c10f-4473-8853-fafb56b721ba
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 78f6083cf17bb21152df1a7ea09825f3be7f0e37
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572940"
---
# <a name="working-with-multivalued-columns"></a><span data-ttu-id="f27ec-103">处理多值列</span><span class="sxs-lookup"><span data-stu-id="f27ec-103">Working with Multivalued Columns</span></span>

  
  
<span data-ttu-id="f27ec-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f27ec-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f27ec-105">多值的列包含的数据的多值属性，这是该属性的值而不是单个值的基类型的数组。</span><span class="sxs-lookup"><span data-stu-id="f27ec-105">A multivalued column contains the data of a multivalued property, which is a property that has an array of values of the base type instead of a single value.</span></span> <span data-ttu-id="f27ec-106">无表在其默认列集合中包含多值的属性，因为多值的属性包含表格中的表的用户请求时，才。</span><span class="sxs-lookup"><span data-stu-id="f27ec-106">Because none of the tables include multivalued properties in their default column sets, multivalued properties are included in a table only if the user of the table requests it.</span></span> 
  
<span data-ttu-id="f27ec-107">可以在表中显示多值的列：</span><span class="sxs-lookup"><span data-stu-id="f27ec-107">Multivalued columns can be displayed in tables:</span></span>
  
- <span data-ttu-id="f27ec-108">在单独一行，与所有显示在单列实例的属性值。</span><span class="sxs-lookup"><span data-stu-id="f27ec-108">In a single row, with all of the property values appearing in the single column instance.</span></span> <span data-ttu-id="f27ec-109">这是默认按钮。</span><span class="sxs-lookup"><span data-stu-id="f27ec-109">This is the default.</span></span>
    
    - <span data-ttu-id="f27ec-110">或者-</span><span class="sxs-lookup"><span data-stu-id="f27ec-110">Or -</span></span>
    
- <span data-ttu-id="f27ec-111">在一系列的行，通过为每个属性值的一行。</span><span class="sxs-lookup"><span data-stu-id="f27ec-111">In a series of rows, with one row for each of the property values.</span></span> <span data-ttu-id="f27ec-112">每个唯一值出现在其自己与以下行中的列是因为存在多个行是多值属性中的值。</span><span class="sxs-lookup"><span data-stu-id="f27ec-112">Each unique value appears in the column in its own row with there being as many rows as there are values in the multivalued property.</span></span> <span data-ttu-id="f27ec-113">每个行具有的唯一值**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性，但其他列的相同值。</span><span class="sxs-lookup"><span data-stu-id="f27ec-113">Each row has a unique value for the **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property, but the same values for the other columns.</span></span> <span data-ttu-id="f27ec-114">如果某一行包含多个列与多个值，例如，两个列中的包含_M_ 、 _N_值分别，然后_M\*N_表中显示的行的实例。</span><span class="sxs-lookup"><span data-stu-id="f27ec-114">If a row contains more than one column with multiple values, for example, two columns with  _M_ and  _N_ values respectively, then  _M\*N_ instances of the row appear in the table.</span></span> 
    
<span data-ttu-id="f27ec-115">表用户请求中的多值列的属性类型设置 MVI_FLAG 标志与调用[IMAPITable::SetColumns](imapitable-setcolumns.md)方法来显示的非默认类型。</span><span class="sxs-lookup"><span data-stu-id="f27ec-115">A table user requests the nondefault type of display by calling the [IMAPITable::SetColumns](imapitable-setcolumns.md) method with the MVI_FLAG flag set in the property type of the multivalued column.</span></span> <span data-ttu-id="f27ec-116">MVI_FLAG 标志是定义为 MV_FLAG 和 MV_INSTANCE 标志组合与逻辑**OR**运算的结果的常量。</span><span class="sxs-lookup"><span data-stu-id="f27ec-116">The MVI_FLAG flag is a constant defined as the result of combining the MV_FLAG and MV_INSTANCE flags with a logical **OR** operation.</span></span> <span data-ttu-id="f27ec-117">除了中正使用的**SetColumns**，MVI_FLAG 还可传递给[IMAPITable::SortTable](imapitable-sorttable.md) _lpSortCriteria_参数和[IMAPITable::Restrict](imapitable-restrict.md)中_lpRestriction_的**ulPropTag**成员参数。</span><span class="sxs-lookup"><span data-stu-id="f27ec-117">In addition to being used in **SetColumns**, MVI_FLAG can also be passed to [IMAPITable::SortTable](imapitable-sorttable.md) in the  _lpSortCriteria_ parameter and [IMAPITable::Restrict](imapitable-restrict.md) in the **ulPropTag** member of the  _lpRestriction_ parameter.</span></span> <span data-ttu-id="f27ec-118">当传递 MVI_FLAG，则**SortTable**同样执行到**SetColumns**，在多值列中添加的每个值的一行和实例中的单个值排序。</span><span class="sxs-lookup"><span data-stu-id="f27ec-118">When passed the MVI_FLAG, **SortTable** performs similarly to **SetColumns**, adding one row for each value in the multivalued column and sorting on the single values in the instances.</span></span> <span data-ttu-id="f27ec-119">对于每个值添加了一个行。</span><span class="sxs-lookup"><span data-stu-id="f27ec-119">One row is added for each value.</span></span> 
  
 <span data-ttu-id="f27ec-120">**限制**，但是，不展开多值的列到其他计算行。</span><span class="sxs-lookup"><span data-stu-id="f27ec-120">**Restrict**, however, does not expand the multivalued column into additional computed rows.</span></span> <span data-ttu-id="f27ec-121">使用 MVI_FLAG 集的多值的列指示的服务提供程序，用于限制表中的列。</span><span class="sxs-lookup"><span data-stu-id="f27ec-121">A multivalued column with the MVI_FLAG set instructs the service provider to use that column in restricting the table.</span></span> <span data-ttu-id="f27ec-122">如果限制中没有属性值，它必须是相同的列[IMAPITable::QueryRows](imapitable-queryrows.md)将返回一个单值属性标记。</span><span class="sxs-lookup"><span data-stu-id="f27ec-122">If there is a property value in the restriction, it must be a single value property tag identical to the one that would be returned by [IMAPITable::QueryRows](imapitable-queryrows.md) for the column.</span></span> 
  
<span data-ttu-id="f27ec-123">表实施只需支持显示的默认类型和呼叫者请求其他替代项时，可以返回 MAPI_E_TOO_COMPLEX 值。</span><span class="sxs-lookup"><span data-stu-id="f27ec-123">Table implementers are only required to support the default type of display and can return the MAPI_E_TOO_COMPLEX value when a caller requests the other alternative.</span></span> <span data-ttu-id="f27ec-124">支持两种类型的能力是显示的最重要的消息存储提供程序实现文件夹内容表。</span><span class="sxs-lookup"><span data-stu-id="f27ec-124">The ability to support both types of display is most important for message store providers implementing folder contents tables.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f27ec-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f27ec-125">See also</span></span>



[<span data-ttu-id="f27ec-126">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="f27ec-126">MAPI Tables</span></span>](mapi-tables.md)

