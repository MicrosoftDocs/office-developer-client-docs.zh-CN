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
ms.openlocfilehash: a2a6d273495df52adb83393dc5549b0872c8f6f3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341739"
---
# <a name="srestriction"></a><span data-ttu-id="cc02a-103">SRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-103">SRestriction</span></span>

  
  
<span data-ttu-id="cc02a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cc02a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cc02a-105">介绍用于将表的视图限制为特定行的筛选器。</span><span class="sxs-lookup"><span data-stu-id="cc02a-105">Describes a filter for limiting the view of a table to particular rows.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cc02a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="cc02a-106">Header file:</span></span>  <br/> |<span data-ttu-id="cc02a-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="cc02a-107">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="cc02a-108">Members</span><span class="sxs-lookup"><span data-stu-id="cc02a-108">Members</span></span>

 <span data-ttu-id="cc02a-109">**rt**</span><span class="sxs-lookup"><span data-stu-id="cc02a-109">**rt**</span></span>
  
> <span data-ttu-id="cc02a-110">限制类型。</span><span class="sxs-lookup"><span data-stu-id="cc02a-110">The restriction type.</span></span> <span data-ttu-id="cc02a-111">可能的值如下所示:</span><span class="sxs-lookup"><span data-stu-id="cc02a-111">Possible values are as follows:</span></span> 
    
<span data-ttu-id="cc02a-112">RES_AND</span><span class="sxs-lookup"><span data-stu-id="cc02a-112">RES_AND</span></span> 
  
> <span data-ttu-id="cc02a-113">**和**限制, 这将对限制应用按位**and**运算。</span><span class="sxs-lookup"><span data-stu-id="cc02a-113">An **AND** restriction, which applies a bitwise **AND** operation to a restriction.</span></span> 
    
<span data-ttu-id="cc02a-114">RES_BITMASK</span><span class="sxs-lookup"><span data-stu-id="cc02a-114">RES_BITMASK</span></span> 
  
> <span data-ttu-id="cc02a-115">一个位掩码限制, 它将位掩码应用于属性值。</span><span class="sxs-lookup"><span data-stu-id="cc02a-115">A bitmask restriction, which applies a bitmask to a property value.</span></span>
    
<span data-ttu-id="cc02a-116">RES_COMMENT</span><span class="sxs-lookup"><span data-stu-id="cc02a-116">RES_COMMENT</span></span> 
  
> <span data-ttu-id="cc02a-117">一种注释限制, 它将注释与限制相关联。</span><span class="sxs-lookup"><span data-stu-id="cc02a-117">A comment restriction, which associates a comment with a restriction.</span></span>
    
<span data-ttu-id="cc02a-118">RES_COMPAREPROPS</span><span class="sxs-lookup"><span data-stu-id="cc02a-118">RES_COMPAREPROPS</span></span> 
  
> <span data-ttu-id="cc02a-119">属性比较限制, 它将比较两个属性值。</span><span class="sxs-lookup"><span data-stu-id="cc02a-119">A property comparison restriction, which compares two property values.</span></span>
    
<span data-ttu-id="cc02a-120">RES_CONTENT</span><span class="sxs-lookup"><span data-stu-id="cc02a-120">RES_CONTENT</span></span> 
  
> <span data-ttu-id="cc02a-121">内容限制, 用于搜索特定内容的属性值。</span><span class="sxs-lookup"><span data-stu-id="cc02a-121">A content restriction, which searches a property value for specific content.</span></span>
    
<span data-ttu-id="cc02a-122">RES_EXIST</span><span class="sxs-lookup"><span data-stu-id="cc02a-122">RES_EXIST</span></span> 
  
> <span data-ttu-id="cc02a-123">一个存在的限制, 用于确定是否支持某个属性。</span><span class="sxs-lookup"><span data-stu-id="cc02a-123">An exist restriction, which determines whether a property is supported.</span></span>
    
<span data-ttu-id="cc02a-124">RES_NOT</span><span class="sxs-lookup"><span data-stu-id="cc02a-124">RES_NOT</span></span> 
  
> <span data-ttu-id="cc02a-125">一个**不**受限制, 它将逻辑**非**操作应用于限制。</span><span class="sxs-lookup"><span data-stu-id="cc02a-125">A **NOT** restriction, which applies a logical **NOT** operation to a restriction.</span></span> 
    
<span data-ttu-id="cc02a-126">RES_OR</span><span class="sxs-lookup"><span data-stu-id="cc02a-126">RES_OR</span></span> 
  
> <span data-ttu-id="cc02a-127">**或**限制, 这将对限制应用逻辑**或**操作。</span><span class="sxs-lookup"><span data-stu-id="cc02a-127">An **OR** restriction, which applies a logical **OR** operation to a restriction.</span></span> 
    
<span data-ttu-id="cc02a-128">RES_PROPERTY</span><span class="sxs-lookup"><span data-stu-id="cc02a-128">RES_PROPERTY</span></span> 
  
> <span data-ttu-id="cc02a-129">属性限制, 用于确定属性值是否与特定值匹配。</span><span class="sxs-lookup"><span data-stu-id="cc02a-129">A property restriction, which determines whether a property value matches a particular value.</span></span>
    
<span data-ttu-id="cc02a-130">RES_SIZE</span><span class="sxs-lookup"><span data-stu-id="cc02a-130">RES_SIZE</span></span> 
  
> <span data-ttu-id="cc02a-131">大小限制, 用于确定属性值是否为特定大小。</span><span class="sxs-lookup"><span data-stu-id="cc02a-131">A size restriction, which determines whether a property value is a particular size.</span></span>
    
<span data-ttu-id="cc02a-132">RES_SUBRESTRICTION</span><span class="sxs-lookup"><span data-stu-id="cc02a-132">RES_SUBRESTRICTION</span></span> 
  
> <span data-ttu-id="cc02a-133">子对象限制, 它对邮件的附件或收件人应用限制。</span><span class="sxs-lookup"><span data-stu-id="cc02a-133">A sub-object restriction, which applies a restriction to a message's attachments or recipients.</span></span>
    
 <span data-ttu-id="cc02a-134">**res**</span><span class="sxs-lookup"><span data-stu-id="cc02a-134">**res**</span></span>
  
> <span data-ttu-id="cc02a-135">限制结构的联合, 用于描述要应用的筛选器。</span><span class="sxs-lookup"><span data-stu-id="cc02a-135">Union of restriction structures describing the filter to be applied.</span></span> <span data-ttu-id="cc02a-136">**res**成员中包含的特定结构取决于**rt**成员的值。</span><span class="sxs-lookup"><span data-stu-id="cc02a-136">The specific structure included in the **res** member depends on the value of the **rt** member.</span></span> <span data-ttu-id="cc02a-137">在下表中列出了限制类型和结构之间的映射。</span><span class="sxs-lookup"><span data-stu-id="cc02a-137">The mapping between restriction type and structure is listed in the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="cc02a-138">**限制类型**</span><span class="sxs-lookup"><span data-stu-id="cc02a-138">**Restriction type**</span></span> <br/> |<span data-ttu-id="cc02a-139">**限制结构**</span><span class="sxs-lookup"><span data-stu-id="cc02a-139">**Restriction structure**</span></span> <br/> |
|<span data-ttu-id="cc02a-140">RES_AND</span><span class="sxs-lookup"><span data-stu-id="cc02a-140">RES_AND</span></span>  <br/> |[<span data-ttu-id="cc02a-141">SAndRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-141">SAndRestriction</span></span>](sandrestriction.md) <br/> |
|<span data-ttu-id="cc02a-142">RES_BITMASK</span><span class="sxs-lookup"><span data-stu-id="cc02a-142">RES_BITMASK</span></span>  <br/> |[<span data-ttu-id="cc02a-143">SBitMaskRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-143">SBitMaskRestriction</span></span>](sbitmaskrestriction.md) <br/> |
|<span data-ttu-id="cc02a-144">RES_COMMENT</span><span class="sxs-lookup"><span data-stu-id="cc02a-144">RES_COMMENT</span></span>  <br/> |[<span data-ttu-id="cc02a-145">SCommentRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-145">SCommentRestriction</span></span>](scommentrestriction.md) <br/> |
|<span data-ttu-id="cc02a-146">RES_COMPAREPROPS</span><span class="sxs-lookup"><span data-stu-id="cc02a-146">RES_COMPAREPROPS</span></span>  <br/> |[<span data-ttu-id="cc02a-147">SComparePropsRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-147">SComparePropsRestriction</span></span>](scomparepropsrestriction.md) <br/> |
|<span data-ttu-id="cc02a-148">RES_CONTENT</span><span class="sxs-lookup"><span data-stu-id="cc02a-148">RES_CONTENT</span></span>  <br/> |[<span data-ttu-id="cc02a-149">SContentRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-149">SContentRestriction</span></span>](scontentrestriction.md) <br/> |
|<span data-ttu-id="cc02a-150">RES_EXIST</span><span class="sxs-lookup"><span data-stu-id="cc02a-150">RES_EXIST</span></span>  <br/> |[<span data-ttu-id="cc02a-151">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-151">SExistRestriction</span></span>](sexistrestriction.md) <br/> |
|<span data-ttu-id="cc02a-152">RES_NOT</span><span class="sxs-lookup"><span data-stu-id="cc02a-152">RES_NOT</span></span>  <br/> |[<span data-ttu-id="cc02a-153">SNotRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-153">SNotRestriction</span></span>](snotrestriction.md) <br/> |
|<span data-ttu-id="cc02a-154">RES_OR</span><span class="sxs-lookup"><span data-stu-id="cc02a-154">RES_OR</span></span>  <br/> |[<span data-ttu-id="cc02a-155">SOrRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-155">SOrRestriction</span></span>](sorrestriction.md) <br/> |
|<span data-ttu-id="cc02a-156">RES_PROPERTY</span><span class="sxs-lookup"><span data-stu-id="cc02a-156">RES_PROPERTY</span></span>  <br/> |[<span data-ttu-id="cc02a-157">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-157">SPropertyRestriction</span></span>](spropertyrestriction.md) <br/> |
|<span data-ttu-id="cc02a-158">RES_SIZE</span><span class="sxs-lookup"><span data-stu-id="cc02a-158">RES_SIZE</span></span>  <br/> |[<span data-ttu-id="cc02a-159">SSizeRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-159">SSizeRestriction</span></span>](ssizerestriction.md) <br/> |
|<span data-ttu-id="cc02a-160">RES_SUBRESTRICTION</span><span class="sxs-lookup"><span data-stu-id="cc02a-160">RES_SUBRESTRICTION</span></span>  <br/> |[<span data-ttu-id="cc02a-161">SSubRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-161">SSubRestriction</span></span>](ssubrestriction.md) <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cc02a-162">注解</span><span class="sxs-lookup"><span data-stu-id="cc02a-162">Remarks</span></span>

<span data-ttu-id="cc02a-163">客户端使用**SRestriction**结构来限制其表视图中的行数和类型, 并在文件夹中搜索特定邮件。</span><span class="sxs-lookup"><span data-stu-id="cc02a-163">Clients use an **SRestriction** structure to limit the number and type of rows in their view of a table and to search for specific messages in a folder.</span></span> <span data-ttu-id="cc02a-164">若要对表施加限制, 客户端可以调用[IMAPITable:: Restrict](imapitable-restrict.md)或[IMAPITable:: FindRow](imapitable-findrow.md)。</span><span class="sxs-lookup"><span data-stu-id="cc02a-164">To impose the limitation on a table, clients call either [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md).</span></span> <span data-ttu-id="cc02a-165">若要对文件夹施加限制, 客户端可以调用文件夹的[IMAPIContainer:: SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法。</span><span class="sxs-lookup"><span data-stu-id="cc02a-165">To impose the limitation on a folder, clients call the folder's [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) method.</span></span> 
  
<span data-ttu-id="cc02a-166">有关如何对表使用限制的信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="cc02a-166">For information about how to use restrictions with tables, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cc02a-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc02a-167">See also</span></span>



[<span data-ttu-id="cc02a-168">SAndRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-168">SAndRestriction</span></span>](sandrestriction.md)
  
[<span data-ttu-id="cc02a-169">SBitMaskRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-169">SBitMaskRestriction</span></span>](sbitmaskrestriction.md)
  
[<span data-ttu-id="cc02a-170">SCommentRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-170">SCommentRestriction</span></span>](scommentrestriction.md)
  
[<span data-ttu-id="cc02a-171">SComparePropsRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-171">SComparePropsRestriction</span></span>](scomparepropsrestriction.md)
  
[<span data-ttu-id="cc02a-172">SContentRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-172">SContentRestriction</span></span>](scontentrestriction.md)
  
[<span data-ttu-id="cc02a-173">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-173">SExistRestriction</span></span>](sexistrestriction.md)
  
[<span data-ttu-id="cc02a-174">SNotRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-174">SNotRestriction</span></span>](snotrestriction.md)
  
[<span data-ttu-id="cc02a-175">SOrRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-175">SOrRestriction</span></span>](sorrestriction.md)
  
[<span data-ttu-id="cc02a-176">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-176">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="cc02a-177">SSizeRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-177">SSizeRestriction</span></span>](ssizerestriction.md)
  
[<span data-ttu-id="cc02a-178">SSubRestriction</span><span class="sxs-lookup"><span data-stu-id="cc02a-178">SSubRestriction</span></span>](ssubrestriction.md)


[<span data-ttu-id="cc02a-179">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="cc02a-179">MAPI Structures</span></span>](mapi-structures.md)

