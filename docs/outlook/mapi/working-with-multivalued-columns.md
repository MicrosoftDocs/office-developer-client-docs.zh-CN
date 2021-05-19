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
# <a name="working-with-multivalued-columns"></a><span data-ttu-id="93238-103">使用多值列</span><span class="sxs-lookup"><span data-stu-id="93238-103">Working with Multivalued Columns</span></span>

  
  
<span data-ttu-id="93238-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="93238-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="93238-105">多值列包含多值属性的数据，多值属性是一个包含基类型的值的数组而不是单个值的属性。</span><span class="sxs-lookup"><span data-stu-id="93238-105">A multivalued column contains the data of a multivalued property, which is a property that has an array of values of the base type instead of a single value.</span></span> <span data-ttu-id="93238-106">因为任何表的默认列集都没有多值属性，所以只有当表的用户请求表时，多值属性才包含在表中。</span><span class="sxs-lookup"><span data-stu-id="93238-106">Because none of the tables include multivalued properties in their default column sets, multivalued properties are included in a table only if the user of the table requests it.</span></span> 
  
<span data-ttu-id="93238-107">多值列可以显示在表中：</span><span class="sxs-lookup"><span data-stu-id="93238-107">Multivalued columns can be displayed in tables:</span></span>
  
- <span data-ttu-id="93238-108">在单行中，所有属性值都显示在单个列实例中。</span><span class="sxs-lookup"><span data-stu-id="93238-108">In a single row, with all of the property values appearing in the single column instance.</span></span> <span data-ttu-id="93238-109">这是默认选项。</span><span class="sxs-lookup"><span data-stu-id="93238-109">This is the default.</span></span>
    
    - <span data-ttu-id="93238-110">或 -</span><span class="sxs-lookup"><span data-stu-id="93238-110">Or -</span></span>
    
- <span data-ttu-id="93238-111">在一系列行中，每个属性值各有一行。</span><span class="sxs-lookup"><span data-stu-id="93238-111">In a series of rows, with one row for each of the property values.</span></span> <span data-ttu-id="93238-112">每个唯一值都显示在列内自己的行中，行数与多值属性中的值数一样。</span><span class="sxs-lookup"><span data-stu-id="93238-112">Each unique value appears in the column in its own row with there being as many rows as there are values in the multivalued property.</span></span> <span data-ttu-id="93238-113">每行具有[PidTagInstanceKey](pidtaginstancekey-canonical-property.md) PR_INSTANCE_KEY (的唯一) ，但其他列的值相同。 </span><span class="sxs-lookup"><span data-stu-id="93238-113">Each row has a unique value for the **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property, but the same values for the other columns.</span></span> <span data-ttu-id="93238-114">如果一行包含多个具有多个值的列，例如，两列分别具有  _M_ 和  _N_ 值，则  _行的 M \* N_ 实例将显示在表中。</span><span class="sxs-lookup"><span data-stu-id="93238-114">If a row contains more than one column with multiple values, for example, two columns with  _M_ and  _N_ values respectively, then  _M\*N_ instances of the row appear in the table.</span></span> 
    
<span data-ttu-id="93238-115">表用户通过调用 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 方法请求非默认类型的显示，该方法具有在多值列的属性类型中设置的 MVI_FLAG 标志。</span><span class="sxs-lookup"><span data-stu-id="93238-115">A table user requests the nondefault type of display by calling the [IMAPITable::SetColumns](imapitable-setcolumns.md) method with the MVI_FLAG flag set in the property type of the multivalued column.</span></span> <span data-ttu-id="93238-116">the MVI_FLAG flag is a constant defined as the result of combining the MV_FLAG and MV_INSTANCE flags with a logical **OR** operation.</span><span class="sxs-lookup"><span data-stu-id="93238-116">The MVI_FLAG flag is a constant defined as the result of combining the MV_FLAG and MV_INSTANCE flags with a logical **OR** operation.</span></span> <span data-ttu-id="93238-117">除了在 **SetColumns** 中使用之外，MVI_FLAG 还可以传递到 _lpSortCriteria_ 参数中的 [IMAPITable：：SortTable](imapitable-sorttable.md)和 _lpRestriction_ 参数的 **ulPropTag** 成员中的 [IMAPITable：：Restrict。](imapitable-restrict.md)</span><span class="sxs-lookup"><span data-stu-id="93238-117">In addition to being used in **SetColumns**, MVI_FLAG can also be passed to [IMAPITable::SortTable](imapitable-sorttable.md) in the  _lpSortCriteria_ parameter and [IMAPITable::Restrict](imapitable-restrict.md) in the **ulPropTag** member of the  _lpRestriction_ parameter.</span></span> <span data-ttu-id="93238-118">在传递MVI_FLAG时 **，SortTable** 的执行方式与 **SetColumns** 类似，即为多值列的每个值添加一行，并按实例中的单个值进行排序。</span><span class="sxs-lookup"><span data-stu-id="93238-118">When passed the MVI_FLAG, **SortTable** performs similarly to **SetColumns**, adding one row for each value in the multivalued column and sorting on the single values in the instances.</span></span> <span data-ttu-id="93238-119">每一个值添加一行。</span><span class="sxs-lookup"><span data-stu-id="93238-119">One row is added for each value.</span></span> 
  
 <span data-ttu-id="93238-120">**但是**，Restrict 不会将多值列展开到其他计算行中。</span><span class="sxs-lookup"><span data-stu-id="93238-120">**Restrict**, however, does not expand the multivalued column into additional computed rows.</span></span> <span data-ttu-id="93238-121">具有值集的多值MVI_FLAG指示服务提供商在限制表时使用该列。</span><span class="sxs-lookup"><span data-stu-id="93238-121">A multivalued column with the MVI_FLAG set instructs the service provider to use that column in restricting the table.</span></span> <span data-ttu-id="93238-122">如果限制中具有属性值，则它必须是一个值属性标记，该标记与 [IMAPITable：：QueryRows](imapitable-queryrows.md) 为列返回的值属性标记相同。</span><span class="sxs-lookup"><span data-stu-id="93238-122">If there is a property value in the restriction, it must be a single value property tag identical to the one that would be returned by [IMAPITable::QueryRows](imapitable-queryrows.md) for the column.</span></span> 
  
<span data-ttu-id="93238-123">表实现器只需要支持默认的显示类型，并且当调用方请求其他备选MAPI_E_TOO_COMPLEX可以返回值。</span><span class="sxs-lookup"><span data-stu-id="93238-123">Table implementers are only required to support the default type of display and can return the MAPI_E_TOO_COMPLEX value when a caller requests the other alternative.</span></span> <span data-ttu-id="93238-124">对于实现文件夹内容表的邮件存储提供程序来说，支持这两种显示类型的能力非常重要。</span><span class="sxs-lookup"><span data-stu-id="93238-124">The ability to support both types of display is most important for message store providers implementing folder contents tables.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="93238-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93238-125">See also</span></span>



[<span data-ttu-id="93238-126">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="93238-126">MAPI Tables</span></span>](mapi-tables.md)

