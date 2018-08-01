---
title: SRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SRestriction
api_type:
- COM
ms.assetid: c12b4409-da6f-480b-87af-1e5baea2e8bd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9748229799641d62b1649491c432f10164b49192
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778867"
---
# <a name="srestriction"></a><span data-ttu-id="52592-103">SRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-103">SRestriction</span></span>

  
  
<span data-ttu-id="52592-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="52592-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="52592-105">介绍限制到特定行表的视图的筛选器。</span><span class="sxs-lookup"><span data-stu-id="52592-105">Describes a filter for limiting the view of a table to particular rows.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="52592-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="52592-106">Header file:</span></span>  <br/> |<span data-ttu-id="52592-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="52592-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SRestriction
{
  ULONG rt;
  union
  {
    SComparePropsRestriction resCompareProps;
    SAndRestriction resAnd;
    SOrRestriction resOr;
    SNotRestriction resNot;
    SContentRestriction resContent;
    SPropertyRestriction resProperty;
    SBitMaskRestriction resBitMask;
    SSizeRestriction resSize;
    SExistRestriction resExist;
    SSubRestriction resSub;
    SCommentRestriction resComment;
  } res;
} SRestriction;

```

## <a name="members"></a><span data-ttu-id="52592-108">Members</span><span class="sxs-lookup"><span data-stu-id="52592-108">Members</span></span>

 <span data-ttu-id="52592-109">**rt**</span><span class="sxs-lookup"><span data-stu-id="52592-109">**rt**</span></span>
  
> <span data-ttu-id="52592-110">限制类型。</span><span class="sxs-lookup"><span data-stu-id="52592-110">The restriction type.</span></span> <span data-ttu-id="52592-111">可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="52592-111">Possible values are as follows:</span></span> 
    
<span data-ttu-id="52592-112">RES_AND</span><span class="sxs-lookup"><span data-stu-id="52592-112">RES_AND</span></span> 
  
> <span data-ttu-id="52592-113">限制应用于的按位**AND**操作**和**限制。</span><span class="sxs-lookup"><span data-stu-id="52592-113">An **AND** restriction, which applies a bitwise **AND** operation to a restriction.</span></span> 
    
<span data-ttu-id="52592-114">RES_BITMASK</span><span class="sxs-lookup"><span data-stu-id="52592-114">RES_BITMASK</span></span> 
  
> <span data-ttu-id="52592-115">位掩码限制，适用于属性值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="52592-115">A bitmask restriction, which applies a bitmask to a property value.</span></span>
    
<span data-ttu-id="52592-116">RES_COMMENT</span><span class="sxs-lookup"><span data-stu-id="52592-116">RES_COMMENT</span></span> 
  
> <span data-ttu-id="52592-117">注释限制，将批注与限制相关联。</span><span class="sxs-lookup"><span data-stu-id="52592-117">A comment restriction, which associates a comment with a restriction.</span></span>
    
<span data-ttu-id="52592-118">RES_COMPAREPROPS</span><span class="sxs-lookup"><span data-stu-id="52592-118">RES_COMPAREPROPS</span></span> 
  
> <span data-ttu-id="52592-119">属性比较限制，比较两个属性值。</span><span class="sxs-lookup"><span data-stu-id="52592-119">A property comparison restriction, which compares two property values.</span></span>
    
<span data-ttu-id="52592-120">RES_CONTENT</span><span class="sxs-lookup"><span data-stu-id="52592-120">RES_CONTENT</span></span> 
  
> <span data-ttu-id="52592-121">内容限制，搜索特定内容的属性值。</span><span class="sxs-lookup"><span data-stu-id="52592-121">A content restriction, which searches a property value for specific content.</span></span>
    
<span data-ttu-id="52592-122">RES_EXIST</span><span class="sxs-lookup"><span data-stu-id="52592-122">RES_EXIST</span></span> 
  
> <span data-ttu-id="52592-123">确定是否支持属性存在限制。</span><span class="sxs-lookup"><span data-stu-id="52592-123">An exist restriction, which determines whether a property is supported.</span></span>
    
<span data-ttu-id="52592-124">RES_NOT</span><span class="sxs-lookup"><span data-stu-id="52592-124">RES_NOT</span></span> 
  
> <span data-ttu-id="52592-125">**不**限制，适用于限制的逻辑**NOT**操作。</span><span class="sxs-lookup"><span data-stu-id="52592-125">A **NOT** restriction, which applies a logical **NOT** operation to a restriction.</span></span> 
    
<span data-ttu-id="52592-126">RES_OR</span><span class="sxs-lookup"><span data-stu-id="52592-126">RES_OR</span></span> 
  
> <span data-ttu-id="52592-127">**或**限制，适用于限制的逻辑**OR**运算。</span><span class="sxs-lookup"><span data-stu-id="52592-127">An **OR** restriction, which applies a logical **OR** operation to a restriction.</span></span> 
    
<span data-ttu-id="52592-128">RES_PROPERTY</span><span class="sxs-lookup"><span data-stu-id="52592-128">RES_PROPERTY</span></span> 
  
> <span data-ttu-id="52592-129">属性限制，确定属性值是否与特定值匹配。</span><span class="sxs-lookup"><span data-stu-id="52592-129">A property restriction, which determines whether a property value matches a particular value.</span></span>
    
<span data-ttu-id="52592-130">RES_SIZE</span><span class="sxs-lookup"><span data-stu-id="52592-130">RES_SIZE</span></span> 
  
> <span data-ttu-id="52592-131">大小限制，确定属性值是否是特定大小。</span><span class="sxs-lookup"><span data-stu-id="52592-131">A size restriction, which determines whether a property value is a particular size.</span></span>
    
<span data-ttu-id="52592-132">RES_SUBRESTRICTION</span><span class="sxs-lookup"><span data-stu-id="52592-132">RES_SUBRESTRICTION</span></span> 
  
> <span data-ttu-id="52592-133">子对象限制，适用于邮件的附件或收件人的限制。</span><span class="sxs-lookup"><span data-stu-id="52592-133">A sub-object restriction, which applies a restriction to a message's attachments or recipients.</span></span>
    
 <span data-ttu-id="52592-134">**res**</span><span class="sxs-lookup"><span data-stu-id="52592-134">**res**</span></span>
  
> <span data-ttu-id="52592-135">要应用的描述筛选器的限制结构联合。</span><span class="sxs-lookup"><span data-stu-id="52592-135">Union of restriction structures describing the filter to be applied.</span></span> <span data-ttu-id="52592-136">**Res**成员中包含的特定结构取决于**rt**成员的值。</span><span class="sxs-lookup"><span data-stu-id="52592-136">The specific structure included in the **res** member depends on the value of the **rt** member.</span></span> <span data-ttu-id="52592-137">下表中列出的限制类型和结构之间的映射。</span><span class="sxs-lookup"><span data-stu-id="52592-137">The mapping between restriction type and structure is listed in the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="52592-138">**限制类型**</span><span class="sxs-lookup"><span data-stu-id="52592-138">**Restriction type**</span></span> <br/> |<span data-ttu-id="52592-139">**限制结构**</span><span class="sxs-lookup"><span data-stu-id="52592-139">**Restriction structure**</span></span> <br/> |
|<span data-ttu-id="52592-140">RES_AND</span><span class="sxs-lookup"><span data-stu-id="52592-140">RES_AND</span></span>  <br/> |[<span data-ttu-id="52592-141">SAndRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-141">SAndRestriction</span></span>](sandrestriction.md) <br/> |
|<span data-ttu-id="52592-142">RES_BITMASK</span><span class="sxs-lookup"><span data-stu-id="52592-142">RES_BITMASK</span></span>  <br/> |[<span data-ttu-id="52592-143">SBitMaskRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-143">SBitMaskRestriction</span></span>](sbitmaskrestriction.md) <br/> |
|<span data-ttu-id="52592-144">RES_COMMENT</span><span class="sxs-lookup"><span data-stu-id="52592-144">RES_COMMENT</span></span>  <br/> |[<span data-ttu-id="52592-145">SCommentRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-145">SCommentRestriction</span></span>](scommentrestriction.md) <br/> |
|<span data-ttu-id="52592-146">RES_COMPAREPROPS</span><span class="sxs-lookup"><span data-stu-id="52592-146">RES_COMPAREPROPS</span></span>  <br/> |[<span data-ttu-id="52592-147">SComparePropsRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-147">SComparePropsRestriction</span></span>](scomparepropsrestriction.md) <br/> |
|<span data-ttu-id="52592-148">RES_CONTENT</span><span class="sxs-lookup"><span data-stu-id="52592-148">RES_CONTENT</span></span>  <br/> |[<span data-ttu-id="52592-149">SContentRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-149">SContentRestriction</span></span>](scontentrestriction.md) <br/> |
|<span data-ttu-id="52592-150">RES_EXIST</span><span class="sxs-lookup"><span data-stu-id="52592-150">RES_EXIST</span></span>  <br/> |[<span data-ttu-id="52592-151">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-151">SExistRestriction</span></span>](sexistrestriction.md) <br/> |
|<span data-ttu-id="52592-152">RES_NOT</span><span class="sxs-lookup"><span data-stu-id="52592-152">RES_NOT</span></span>  <br/> |[<span data-ttu-id="52592-153">SNotRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-153">SNotRestriction</span></span>](snotrestriction.md) <br/> |
|<span data-ttu-id="52592-154">RES_OR</span><span class="sxs-lookup"><span data-stu-id="52592-154">RES_OR</span></span>  <br/> |[<span data-ttu-id="52592-155">SOrRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-155">SOrRestriction</span></span>](sorrestriction.md) <br/> |
|<span data-ttu-id="52592-156">RES_PROPERTY</span><span class="sxs-lookup"><span data-stu-id="52592-156">RES_PROPERTY</span></span>  <br/> |[<span data-ttu-id="52592-157">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-157">SPropertyRestriction</span></span>](spropertyrestriction.md) <br/> |
|<span data-ttu-id="52592-158">RES_SIZE</span><span class="sxs-lookup"><span data-stu-id="52592-158">RES_SIZE</span></span>  <br/> |[<span data-ttu-id="52592-159">SSizeRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-159">SSizeRestriction</span></span>](ssizerestriction.md) <br/> |
|<span data-ttu-id="52592-160">RES_SUBRESTRICTION</span><span class="sxs-lookup"><span data-stu-id="52592-160">RES_SUBRESTRICTION</span></span>  <br/> |[<span data-ttu-id="52592-161">SSubRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-161">SSubRestriction</span></span>](ssubrestriction.md) <br/> |
   
## <a name="remarks"></a><span data-ttu-id="52592-162">说明</span><span class="sxs-lookup"><span data-stu-id="52592-162">Remarks</span></span>

<span data-ttu-id="52592-163">若要限制的数量和类型，其表的视图中的行并搜索的文件夹中的特定邮件，则客户端使用**SRestriction**结构。</span><span class="sxs-lookup"><span data-stu-id="52592-163">Clients use an **SRestriction** structure to limit the number and type of rows in their view of a table and to search for specific messages in a folder.</span></span> <span data-ttu-id="52592-164">若要实施的限制表上，客户端调用[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)。</span><span class="sxs-lookup"><span data-stu-id="52592-164">To impose the limitation on a table, clients call either [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md).</span></span> <span data-ttu-id="52592-165">若要实施的文件夹的限制，客户端调用该文件夹的[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法。</span><span class="sxs-lookup"><span data-stu-id="52592-165">To impose the limitation on a folder, clients call the folder's [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) method.</span></span> 
  
<span data-ttu-id="52592-166">有关如何使用表的限制，请参阅[有关限制](about-restrictions.md)的信息。</span><span class="sxs-lookup"><span data-stu-id="52592-166">For information about how to use restrictions with tables, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="52592-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52592-167">See also</span></span>



[<span data-ttu-id="52592-168">SAndRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-168">SAndRestriction</span></span>](sandrestriction.md)
  
[<span data-ttu-id="52592-169">SBitMaskRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-169">SBitMaskRestriction</span></span>](sbitmaskrestriction.md)
  
[<span data-ttu-id="52592-170">SCommentRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-170">SCommentRestriction</span></span>](scommentrestriction.md)
  
[<span data-ttu-id="52592-171">SComparePropsRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-171">SComparePropsRestriction</span></span>](scomparepropsrestriction.md)
  
[<span data-ttu-id="52592-172">SContentRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-172">SContentRestriction</span></span>](scontentrestriction.md)
  
[<span data-ttu-id="52592-173">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-173">SExistRestriction</span></span>](sexistrestriction.md)
  
[<span data-ttu-id="52592-174">SNotRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-174">SNotRestriction</span></span>](snotrestriction.md)
  
[<span data-ttu-id="52592-175">SOrRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-175">SOrRestriction</span></span>](sorrestriction.md)
  
[<span data-ttu-id="52592-176">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-176">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="52592-177">SSizeRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-177">SSizeRestriction</span></span>](ssizerestriction.md)
  
[<span data-ttu-id="52592-178">SSubRestriction</span><span class="sxs-lookup"><span data-stu-id="52592-178">SSubRestriction</span></span>](ssubrestriction.md)


[<span data-ttu-id="52592-179">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="52592-179">MAPI Structures</span></span>](mapi-structures.md)

