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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dcbf8a323f5178a5a2e39d0963dd19415ab835bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342692"
---
# <a name="pidtagmemberrights-canonical-property"></a><span data-ttu-id="604c7-103">PidTagMemberRights 规范属性</span><span class="sxs-lookup"><span data-stu-id="604c7-103">PidTagMemberRights Canonical Property</span></span>

  
  
<span data-ttu-id="604c7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="604c7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="604c7-105">包含一组指示此成员在文件夹或邮箱中的权限的位。</span><span class="sxs-lookup"><span data-stu-id="604c7-105">Contains a set of bits that indicated the rights of this member on a folder or mailbox.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="604c7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="604c7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="604c7-107">PR_MEMBER_RIGHTS</span><span class="sxs-lookup"><span data-stu-id="604c7-107">PR_MEMBER_RIGHTS</span></span>  <br/> |
|<span data-ttu-id="604c7-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="604c7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="604c7-109">0x6673</span><span class="sxs-lookup"><span data-stu-id="604c7-109">0x6673</span></span>  <br/> |
|<span data-ttu-id="604c7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="604c7-110">Data type:</span></span>  <br/> |<span data-ttu-id="604c7-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="604c7-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="604c7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="604c7-112">Area:</span></span>  <br/> |<span data-ttu-id="604c7-113">访问控制</span><span class="sxs-lookup"><span data-stu-id="604c7-113">Access Control</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="604c7-114">注解</span><span class="sxs-lookup"><span data-stu-id="604c7-114">Remarks</span></span>

<span data-ttu-id="604c7-115">[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口使用此属性定义对文件夹上的成员的权限。</span><span class="sxs-lookup"><span data-stu-id="604c7-115">This property is used by the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface to define rights of a member on a folder.</span></span> <span data-ttu-id="604c7-116">可以显示和修改这些权限。</span><span class="sxs-lookup"><span data-stu-id="604c7-116">These rights can be displayed and modified.</span></span> <span data-ttu-id="604c7-117">以下值是为此属性定义的权限。</span><span class="sxs-lookup"><span data-stu-id="604c7-117">The following values are rights defined for this property.</span></span> 
  
<span data-ttu-id="604c7-118">frightsReadAny</span><span class="sxs-lookup"><span data-stu-id="604c7-118">frightsReadAny</span></span>
  
> <span data-ttu-id="604c7-119">Member 可以读取任何邮件。</span><span class="sxs-lookup"><span data-stu-id="604c7-119">Member can read any messages.</span></span>
    
<span data-ttu-id="604c7-120">frightsCreate</span><span class="sxs-lookup"><span data-stu-id="604c7-120">frightsCreate</span></span>
  
> <span data-ttu-id="604c7-121">成员可以创建邮件。</span><span class="sxs-lookup"><span data-stu-id="604c7-121">Member can create messages.</span></span>
    
<span data-ttu-id="604c7-122">frightsEditOwned</span><span class="sxs-lookup"><span data-stu-id="604c7-122">frightsEditOwned</span></span>
  
> <span data-ttu-id="604c7-123">Member 可以编辑用户拥有的任何邮件。</span><span class="sxs-lookup"><span data-stu-id="604c7-123">Member can edit any messages owned by the user.</span></span>
    
<span data-ttu-id="604c7-124">frightsDeleteOwned</span><span class="sxs-lookup"><span data-stu-id="604c7-124">frightsDeleteOwned</span></span>
  
> <span data-ttu-id="604c7-125">Member 可删除用户拥有的任何邮件。</span><span class="sxs-lookup"><span data-stu-id="604c7-125">Member can delete any messages owned by the user.</span></span>
    
<span data-ttu-id="604c7-126">frightsEditAny</span><span class="sxs-lookup"><span data-stu-id="604c7-126">frightsEditAny</span></span>
  
> <span data-ttu-id="604c7-127">Member 可以编辑任何邮件。</span><span class="sxs-lookup"><span data-stu-id="604c7-127">Member can edit any message.</span></span>
    
<span data-ttu-id="604c7-128">frightsDeleteAny</span><span class="sxs-lookup"><span data-stu-id="604c7-128">frightsDeleteAny</span></span>
  
> <span data-ttu-id="604c7-129">Member 可以删除任何邮件。</span><span class="sxs-lookup"><span data-stu-id="604c7-129">Member can delete any message.</span></span>
    
<span data-ttu-id="604c7-130">frightsCreateSubfolder</span><span class="sxs-lookup"><span data-stu-id="604c7-130">frightsCreateSubfolder</span></span>
  
> <span data-ttu-id="604c7-131">Member 可以为文件夹创建子文件夹。</span><span class="sxs-lookup"><span data-stu-id="604c7-131">Member can create subfolders for the folder.</span></span>
    
<span data-ttu-id="604c7-132">frightsOwner</span><span class="sxs-lookup"><span data-stu-id="604c7-132">frightsOwner</span></span>
  
> <span data-ttu-id="604c7-133">成员拥有对该文件夹的所有以前的权限。</span><span class="sxs-lookup"><span data-stu-id="604c7-133">Member has all the previous rights on the folder.</span></span>
    
<span data-ttu-id="604c7-134">frightsContact</span><span class="sxs-lookup"><span data-stu-id="604c7-134">frightsContact</span></span>
  
> <span data-ttu-id="604c7-135">成员可以让您的姓名显示为文件夹中的联系人。</span><span class="sxs-lookup"><span data-stu-id="604c7-135">Member can have your name appear as the contact on the folder.</span></span>
    
<span data-ttu-id="604c7-136">frightsVisible</span><span class="sxs-lookup"><span data-stu-id="604c7-136">frightsVisible</span></span>
  
> <span data-ttu-id="604c7-137">成员可查看该文件夹是否存在。</span><span class="sxs-lookup"><span data-stu-id="604c7-137">Member can see that the folder exists.</span></span>
    
<span data-ttu-id="604c7-138">rightsNone</span><span class="sxs-lookup"><span data-stu-id="604c7-138">rightsNone</span></span>
  
> <span data-ttu-id="604c7-139">成员对该文件夹没有权限。</span><span class="sxs-lookup"><span data-stu-id="604c7-139">Member does not have rights on the folder.</span></span>
    
<span data-ttu-id="604c7-140">rightsReadOnly</span><span class="sxs-lookup"><span data-stu-id="604c7-140">rightsReadOnly</span></span>
  
> <span data-ttu-id="604c7-141">Member 可以读取文件夹中的任何邮件。</span><span class="sxs-lookup"><span data-stu-id="604c7-141">Member can read any message in the folder.</span></span>
    
<span data-ttu-id="604c7-142">rightsReadWrite</span><span class="sxs-lookup"><span data-stu-id="604c7-142">rightsReadWrite</span></span>
  
> <span data-ttu-id="604c7-143">Member 可以对文件夹中的任何邮件进行读取和写入。</span><span class="sxs-lookup"><span data-stu-id="604c7-143">Member can read from and write to any message in the folder.</span></span>
    
<span data-ttu-id="604c7-144">rightsAll</span><span class="sxs-lookup"><span data-stu-id="604c7-144">rightsAll</span></span>
  
> <span data-ttu-id="604c7-145">成员拥有对该文件夹的所有以前的权限。</span><span class="sxs-lookup"><span data-stu-id="604c7-145">Member has all the previous rights on the folder.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="604c7-146">相关资源</span><span class="sxs-lookup"><span data-stu-id="604c7-146">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="604c7-147">协议规范</span><span class="sxs-lookup"><span data-stu-id="604c7-147">Protocol specifications</span></span>

<span data-ttu-id="604c7-148">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="604c7-148">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="604c7-149">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="604c7-149">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="604c7-150">[[毫秒-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="604c7-150">[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="604c7-151">处理文件夹操作。</span><span class="sxs-lookup"><span data-stu-id="604c7-151">Handles folder operations.</span></span>
    
<span data-ttu-id="604c7-152">[[毫秒-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="604c7-152">[[MS-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="604c7-153">处理存储在服务器上的文件夹权限列表的检索。</span><span class="sxs-lookup"><span data-stu-id="604c7-153">Handles the retrieval of folder permission lists that are stored on the server.</span></span>
    
<span data-ttu-id="604c7-154">[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="604c7-154">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="604c7-155">指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历项目代表另一个用户操作时与之进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="604c7-155">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar items when they act on behalf of another user.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="604c7-156">头文件</span><span class="sxs-lookup"><span data-stu-id="604c7-156">Header files</span></span>

<span data-ttu-id="604c7-157">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="604c7-157">Mapidefs.h</span></span>
  
> <span data-ttu-id="604c7-158">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="604c7-158">Provides data type definitions.</span></span>
    
<span data-ttu-id="604c7-159">Mapitags</span><span class="sxs-lookup"><span data-stu-id="604c7-159">Mapitags.h</span></span>
  
> <span data-ttu-id="604c7-160">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="604c7-160">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="604c7-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="604c7-161">See also</span></span>



[<span data-ttu-id="604c7-162">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="604c7-162">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)


[<span data-ttu-id="604c7-163">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="604c7-163">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="604c7-164">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="604c7-164">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="604c7-165">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="604c7-165">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="604c7-166">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="604c7-166">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

