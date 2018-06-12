---
title: PidTagMemberRights 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMemberRights
api_type:
- HeaderDef
ms.assetid: 3e526b93-1f64-41ea-b43c-5b03fe1c56ed
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 2ffc6973d2670402ec8095120eea3db02f529d0a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777847"
---
# <a name="pidtagmemberrights-canonical-property"></a><span data-ttu-id="43bdc-103">PidTagMemberRights 规范属性</span><span class="sxs-lookup"><span data-stu-id="43bdc-103">PidTagMemberRights Canonical Property</span></span>

  
  
<span data-ttu-id="43bdc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="43bdc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="43bdc-105">包含一组所指示文件夹或邮箱上的此成员的权限的位。</span><span class="sxs-lookup"><span data-stu-id="43bdc-105">Contains a set of bits that indicated the rights of this member on a folder or mailbox.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="43bdc-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="43bdc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="43bdc-107">PR_MEMBER_RIGHTS</span><span class="sxs-lookup"><span data-stu-id="43bdc-107">PR_MEMBER_RIGHTS</span></span>  <br/> |
|<span data-ttu-id="43bdc-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="43bdc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="43bdc-109">0x6673</span><span class="sxs-lookup"><span data-stu-id="43bdc-109">0x6673</span></span>  <br/> |
|<span data-ttu-id="43bdc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="43bdc-110">Data type:</span></span>  <br/> |<span data-ttu-id="43bdc-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="43bdc-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="43bdc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="43bdc-112">Area:</span></span>  <br/> |<span data-ttu-id="43bdc-113">访问控制</span><span class="sxs-lookup"><span data-stu-id="43bdc-113">Access Control</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="43bdc-114">备注</span><span class="sxs-lookup"><span data-stu-id="43bdc-114">Remarks</span></span>

<span data-ttu-id="43bdc-115">此属性由[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口用于在文件夹中定义的成员的权限。</span><span class="sxs-lookup"><span data-stu-id="43bdc-115">This property is used by the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface to define rights of a member on a folder.</span></span> <span data-ttu-id="43bdc-116">可以显示和修改这些权限。</span><span class="sxs-lookup"><span data-stu-id="43bdc-116">These rights can be displayed and modified.</span></span> <span data-ttu-id="43bdc-117">下面的值为此属性定义的权限。</span><span class="sxs-lookup"><span data-stu-id="43bdc-117">The following values are rights defined for this property.</span></span> 
  
<span data-ttu-id="43bdc-118">frightsReadAny</span><span class="sxs-lookup"><span data-stu-id="43bdc-118">frightsReadAny</span></span>
  
> <span data-ttu-id="43bdc-119">成员可以读取任何消息。</span><span class="sxs-lookup"><span data-stu-id="43bdc-119">Member can read any messages.</span></span>
    
<span data-ttu-id="43bdc-120">frightsCreate</span><span class="sxs-lookup"><span data-stu-id="43bdc-120">frightsCreate</span></span>
  
> <span data-ttu-id="43bdc-121">成员可以创建邮件。</span><span class="sxs-lookup"><span data-stu-id="43bdc-121">Member can create messages.</span></span>
    
<span data-ttu-id="43bdc-122">frightsEditOwned</span><span class="sxs-lookup"><span data-stu-id="43bdc-122">frightsEditOwned</span></span>
  
> <span data-ttu-id="43bdc-123">成员可以编辑用户所拥有的任何消息。</span><span class="sxs-lookup"><span data-stu-id="43bdc-123">Member can edit any messages owned by the user.</span></span>
    
<span data-ttu-id="43bdc-124">frightsDeleteOwned</span><span class="sxs-lookup"><span data-stu-id="43bdc-124">frightsDeleteOwned</span></span>
  
> <span data-ttu-id="43bdc-125">成员可以删除用户所拥有的任何消息。</span><span class="sxs-lookup"><span data-stu-id="43bdc-125">Member can delete any messages owned by the user.</span></span>
    
<span data-ttu-id="43bdc-126">frightsEditAny</span><span class="sxs-lookup"><span data-stu-id="43bdc-126">frightsEditAny</span></span>
  
> <span data-ttu-id="43bdc-127">成员可以编辑任何消息。</span><span class="sxs-lookup"><span data-stu-id="43bdc-127">Member can edit any message.</span></span>
    
<span data-ttu-id="43bdc-128">frightsDeleteAny</span><span class="sxs-lookup"><span data-stu-id="43bdc-128">frightsDeleteAny</span></span>
  
> <span data-ttu-id="43bdc-129">成员可以删除任何消息。</span><span class="sxs-lookup"><span data-stu-id="43bdc-129">Member can delete any message.</span></span>
    
<span data-ttu-id="43bdc-130">frightsCreateSubfolder</span><span class="sxs-lookup"><span data-stu-id="43bdc-130">frightsCreateSubfolder</span></span>
  
> <span data-ttu-id="43bdc-131">成员可以创建子文件夹。</span><span class="sxs-lookup"><span data-stu-id="43bdc-131">Member can create subfolders for the folder.</span></span>
    
<span data-ttu-id="43bdc-132">frightsOwner</span><span class="sxs-lookup"><span data-stu-id="43bdc-132">frightsOwner</span></span>
  
> <span data-ttu-id="43bdc-133">成员具有的文件夹的所有以前的权限。</span><span class="sxs-lookup"><span data-stu-id="43bdc-133">Member has all the previous rights on the folder.</span></span>
    
<span data-ttu-id="43bdc-134">frightsContact</span><span class="sxs-lookup"><span data-stu-id="43bdc-134">frightsContact</span></span>
  
> <span data-ttu-id="43bdc-135">成员可以具有您显示为的文件夹的联系人的姓名。</span><span class="sxs-lookup"><span data-stu-id="43bdc-135">Member can have your name appear as the contact on the folder.</span></span>
    
<span data-ttu-id="43bdc-136">frightsVisible</span><span class="sxs-lookup"><span data-stu-id="43bdc-136">frightsVisible</span></span>
  
> <span data-ttu-id="43bdc-137">成员都能看到该文件夹存在。</span><span class="sxs-lookup"><span data-stu-id="43bdc-137">Member can see that the folder exists.</span></span>
    
<span data-ttu-id="43bdc-138">rightsNone</span><span class="sxs-lookup"><span data-stu-id="43bdc-138">rightsNone</span></span>
  
> <span data-ttu-id="43bdc-139">成员的文件夹没有权限。</span><span class="sxs-lookup"><span data-stu-id="43bdc-139">Member does not have rights on the folder.</span></span>
    
<span data-ttu-id="43bdc-140">rightsReadOnly</span><span class="sxs-lookup"><span data-stu-id="43bdc-140">rightsReadOnly</span></span>
  
> <span data-ttu-id="43bdc-141">成员可以读取的文件夹中的任何消息。</span><span class="sxs-lookup"><span data-stu-id="43bdc-141">Member can read any message in the folder.</span></span>
    
<span data-ttu-id="43bdc-142">rightsReadWrite</span><span class="sxs-lookup"><span data-stu-id="43bdc-142">rightsReadWrite</span></span>
  
> <span data-ttu-id="43bdc-143">成员可以读取和写入到的文件夹中的任何消息。</span><span class="sxs-lookup"><span data-stu-id="43bdc-143">Member can read from and write to any message in the folder.</span></span>
    
<span data-ttu-id="43bdc-144">rightsAll</span><span class="sxs-lookup"><span data-stu-id="43bdc-144">rightsAll</span></span>
  
> <span data-ttu-id="43bdc-145">成员具有的文件夹的所有以前的权限。</span><span class="sxs-lookup"><span data-stu-id="43bdc-145">Member has all the previous rights on the folder.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="43bdc-146">相关资源</span><span class="sxs-lookup"><span data-stu-id="43bdc-146">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="43bdc-147">协议规范</span><span class="sxs-lookup"><span data-stu-id="43bdc-147">Protocol specifications</span></span>

<span data-ttu-id="43bdc-148">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43bdc-148">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43bdc-149">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="43bdc-149">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="43bdc-150">[[MS OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43bdc-150">[[MS-OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43bdc-151">处理文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="43bdc-151">Handles folder operations.</span></span>
    
<span data-ttu-id="43bdc-152">[[MS OXCPERM]](http://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43bdc-152">[[MS-OXCPERM]](http://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43bdc-153">处理检索存储在服务器的文件夹的权限列表。</span><span class="sxs-lookup"><span data-stu-id="43bdc-153">Handles the retrieval of folder permission lists that are stored on the server.</span></span>
    
<span data-ttu-id="43bdc-154">[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43bdc-154">[[MS-OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43bdc-155">指定连接到和配置为代理人，以及与邮件和日历项目交互的邮箱，当这些代表其他用户操作的方法。</span><span class="sxs-lookup"><span data-stu-id="43bdc-155">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar items when they act on behalf of another user.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="43bdc-156">头文件</span><span class="sxs-lookup"><span data-stu-id="43bdc-156">Header files</span></span>

<span data-ttu-id="43bdc-157">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="43bdc-157">Mapidefs.h</span></span>
  
> <span data-ttu-id="43bdc-158">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="43bdc-158">Provides data type definitions.</span></span>
    
<span data-ttu-id="43bdc-159">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="43bdc-159">Mapitags.h</span></span>
  
> <span data-ttu-id="43bdc-160">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="43bdc-160">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="43bdc-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43bdc-161">See also</span></span>



[<span data-ttu-id="43bdc-162">IExchangeModifyTable: IUnknown</span><span class="sxs-lookup"><span data-stu-id="43bdc-162">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)


[<span data-ttu-id="43bdc-163">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="43bdc-163">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="43bdc-164">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="43bdc-164">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="43bdc-165">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="43bdc-165">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="43bdc-166">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="43bdc-166">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

