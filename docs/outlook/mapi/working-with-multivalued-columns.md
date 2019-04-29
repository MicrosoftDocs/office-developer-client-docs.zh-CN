---
title: 使用多值列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 911a41c3-c10f-4473-8853-fafb56b721ba
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 34f19e279c86e0c0856d242cf2aa13d744d46f13
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420183"
---
# <a name="working-with-multivalued-columns"></a><span data-ttu-id="79260-103">使用多值列</span><span class="sxs-lookup"><span data-stu-id="79260-103">Working with Multivalued Columns</span></span>

  
  
<span data-ttu-id="79260-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="79260-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="79260-105">多值列包含多值属性的数据, 这是一个具有基类型的值数组而不是单个值的属性。</span><span class="sxs-lookup"><span data-stu-id="79260-105">A multivalued column contains the data of a multivalued property, which is a property that has an array of values of the base type instead of a single value.</span></span> <span data-ttu-id="79260-106">由于没有表在其默认列集中包含多值属性, 只有当表的用户请求多值属性时, 才会将这些属性包含在表中。</span><span class="sxs-lookup"><span data-stu-id="79260-106">Because none of the tables include multivalued properties in their default column sets, multivalued properties are included in a table only if the user of the table requests it.</span></span> 
  
<span data-ttu-id="79260-107">多值列可在表中显示:</span><span class="sxs-lookup"><span data-stu-id="79260-107">Multivalued columns can be displayed in tables:</span></span>
  
- <span data-ttu-id="79260-108">在单个行中, 所有属性值显示在单个列实例中。</span><span class="sxs-lookup"><span data-stu-id="79260-108">In a single row, with all of the property values appearing in the single column instance.</span></span> <span data-ttu-id="79260-109">此为默认选项。</span><span class="sxs-lookup"><span data-stu-id="79260-109">This is the default.</span></span>
    
    - <span data-ttu-id="79260-110">和</span><span class="sxs-lookup"><span data-stu-id="79260-110">Or -</span></span>
    
- <span data-ttu-id="79260-111">在一系列行中, 每个属性值占一行。</span><span class="sxs-lookup"><span data-stu-id="79260-111">In a series of rows, with one row for each of the property values.</span></span> <span data-ttu-id="79260-112">每个唯一值显示在其自己的行中的列中, 其中的行数与多值属性中的值相同。</span><span class="sxs-lookup"><span data-stu-id="79260-112">Each unique value appears in the column in its own row with there being as many rows as there are values in the multivalued property.</span></span> <span data-ttu-id="79260-113">每行的**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性的值都是唯一的, 但其他列的值相同。</span><span class="sxs-lookup"><span data-stu-id="79260-113">Each row has a unique value for the **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property, but the same values for the other columns.</span></span> <span data-ttu-id="79260-114">如果某行包含多个值的多个列 (例如, 分别具有_M_和_N_个值的两个列), 则在表中显示该行的_M\*N_个实例。</span><span class="sxs-lookup"><span data-stu-id="79260-114">If a row contains more than one column with multiple values, for example, two columns with  _M_ and  _N_ values respectively, then  _M\*N_ instances of the row appear in the table.</span></span> 
    
<span data-ttu-id="79260-115">通过调用[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法并在多值列的属性类型中设置 MVI_FLAG 标志, 表用户将请求显示非默认类型的显示。</span><span class="sxs-lookup"><span data-stu-id="79260-115">A table user requests the nondefault type of display by calling the [IMAPITable::SetColumns](imapitable-setcolumns.md) method with the MVI_FLAG flag set in the property type of the multivalued column.</span></span> <span data-ttu-id="79260-116">MVI_FLAG 标志是一个常量, 定义为将 MV_FLAG 和 MV_INSTANCE 标志与逻辑**OR**运算结合使用的结果。</span><span class="sxs-lookup"><span data-stu-id="79260-116">The MVI_FLAG flag is a constant defined as the result of combining the MV_FLAG and MV_INSTANCE flags with a logical **OR** operation.</span></span> <span data-ttu-id="79260-117">除了在**SetColumns**中使用之外, 还可以将 MVI_FLAG 传递到_lpSortCriteria_参数中的[imapitable:: SortTable](imapitable-sorttable.md)和[imapitable:: Restrict](imapitable-restrict.md) in _ulPropTag_的**lpRestriction**成员参数.</span><span class="sxs-lookup"><span data-stu-id="79260-117">In addition to being used in **SetColumns**, MVI_FLAG can also be passed to [IMAPITable::SortTable](imapitable-sorttable.md) in the  _lpSortCriteria_ parameter and [IMAPITable::Restrict](imapitable-restrict.md) in the **ulPropTag** member of the  _lpRestriction_ parameter.</span></span> <span data-ttu-id="79260-118">传递 MVI_FLAG 时, **SortTable**的执行方式类似于**SetColumns**, 为多值列中的每个值添加一行, 并对实例中的单个值进行排序。</span><span class="sxs-lookup"><span data-stu-id="79260-118">When passed the MVI_FLAG, **SortTable** performs similarly to **SetColumns**, adding one row for each value in the multivalued column and sorting on the single values in the instances.</span></span> <span data-ttu-id="79260-119">为每个值添加一个行。</span><span class="sxs-lookup"><span data-stu-id="79260-119">One row is added for each value.</span></span> 
  
 <span data-ttu-id="79260-120">但是,**限制**不会将多值列展开为其他计算行。</span><span class="sxs-lookup"><span data-stu-id="79260-120">**Restrict**, however, does not expand the multivalued column into additional computed rows.</span></span> <span data-ttu-id="79260-121">带有 MVI_FLAG 集的多值列指示服务提供程序在限制表时使用该列。</span><span class="sxs-lookup"><span data-stu-id="79260-121">A multivalued column with the MVI_FLAG set instructs the service provider to use that column in restricting the table.</span></span> <span data-ttu-id="79260-122">如果限制中有属性值, 则它必须是与将由[IMAPITable:: QueryRows](imapitable-queryrows.md)为列返回的值相同的单个值属性标记。</span><span class="sxs-lookup"><span data-stu-id="79260-122">If there is a property value in the restriction, it must be a single value property tag identical to the one that would be returned by [IMAPITable::QueryRows](imapitable-queryrows.md) for the column.</span></span> 
  
<span data-ttu-id="79260-123">表实施者只需支持默认类型的显示, 并且可以在呼叫者请求其他替代项时返回 MAPI_E_TOO_COMPLEX 值。</span><span class="sxs-lookup"><span data-stu-id="79260-123">Table implementers are only required to support the default type of display and can return the MAPI_E_TOO_COMPLEX value when a caller requests the other alternative.</span></span> <span data-ttu-id="79260-124">支持这两种类型的显示对实现文件夹内容表的邮件存储提供程序最重要。</span><span class="sxs-lookup"><span data-stu-id="79260-124">The ability to support both types of display is most important for message store providers implementing folder contents tables.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="79260-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79260-125">See also</span></span>



[<span data-ttu-id="79260-126">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="79260-126">MAPI Tables</span></span>](mapi-tables.md)

