---
title: PidTagIpmDraftsEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmDraftsEntryId
api_type:
- HeaderDef
ms.assetid: 17d64211-6265-41f4-b016-3677d75af966
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e259c86803147d782469c8d86b23694d8b54e69d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327886"
---
# <a name="pidtagipmdraftsentryid-canonical-property"></a><span data-ttu-id="2decf-103">PidTagIpmDraftsEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="2decf-103">PidTagIpmDraftsEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="2decf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2decf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2decf-105">包含"草稿Outlook的 **EntryID。**</span><span class="sxs-lookup"><span data-stu-id="2decf-105">Contains the **EntryID** of the Outlook Drafts folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2decf-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2decf-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2decf-107">PR_IPM_DRAFTS_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="2decf-107">PR_IPM_DRAFTS_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="2decf-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2decf-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2decf-109">0x36D7</span><span class="sxs-lookup"><span data-stu-id="2decf-109">0x36D7</span></span>  <br/> |
|<span data-ttu-id="2decf-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2decf-110">Data type:</span></span>  <br/> |<span data-ttu-id="2decf-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="2decf-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="2decf-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2decf-112">Area:</span></span>  <br/> |<span data-ttu-id="2decf-113">文件夹</span><span class="sxs-lookup"><span data-stu-id="2decf-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2decf-114">备注</span><span class="sxs-lookup"><span data-stu-id="2decf-114">Remarks</span></span>

<span data-ttu-id="2decf-115">此属性存储在收件箱文件夹以及邮件存储的根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2decf-115">This property is stored in the Inbox folder as well as the root folder of the message store.</span></span> <span data-ttu-id="2decf-116">若要访问特定邮件存储上的 属性，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="2decf-116">To access the property on a specific message store, do the following:</span></span> 
  
1. <span data-ttu-id="2decf-117">首先，在"收件箱"文件夹中查找 属性。</span><span class="sxs-lookup"><span data-stu-id="2decf-117">First, look for the property in the Inbox folder.</span></span> <span data-ttu-id="2decf-118">使用 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md) 获取对 **"收件箱"文件夹的 EntryID** 的引用。</span><span class="sxs-lookup"><span data-stu-id="2decf-118">Use [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) to obtain a reference to the **EntryID** for the Inbox folder.</span></span> 
    
2. <span data-ttu-id="2decf-119">如果 **IMsgStore：：GetReceiveFolder** 成功，则使用对收件箱和 [IMsgStore：：OpenEntry](imsgstore-openentry.md) **的 EntryID** 的引用打开收件箱并获取对 **IMAPIFolder** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="2decf-119">If **IMsgStore::GetReceiveFolder** is successful, then use the reference to the **EntryID** of the Inbox and [IMsgStore::OpenEntry](imsgstore-openentry.md) to open the Inbox and obtain a reference to an **IMAPIFolder** object.</span></span> 
    
3. <span data-ttu-id="2decf-120">如果 **IMsgStore：：OpenEntry** 成功，则使用对 **IMAPIFolder** 对象和 [IMAPIProp：：GetProps](imapiprop-getprops.md) 的返回引用获取所需属性。</span><span class="sxs-lookup"><span data-stu-id="2decf-120">If **IMsgStore::OpenEntry** is successful, then use the returned reference to the **IMAPIFolder** object and [IMAPIProp::GetProps](imapiprop-getprops.md) to obtain the desired property.</span></span> 
    
4. <span data-ttu-id="2decf-121">如果步骤 1、2 或 3 失败，则查找根文件夹中的属性。</span><span class="sxs-lookup"><span data-stu-id="2decf-121">If Step 1, 2, or 3 fails, look for the property in the root folder.</span></span> <span data-ttu-id="2decf-122">为此，请使用 **IMsgStore：：OpenEntry（** 为 **lpEntryID** 指定 NULL）打开邮件存储的根文件夹并获取对 **IMAPIFolder** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="2decf-122">To do that, use **IMsgStore::OpenEntry**, specifying NULL for **lpEntryID**, to open the root folder of the message store and obtain a reference to the **IMAPIFolder** object.</span></span> 
    
5. <span data-ttu-id="2decf-123">如果打开根文件夹成功，则使用返回的 **对 IMAPIFolder** 对象和 **IMAPIProp：：GetProps** 的引用获取所需属性。</span><span class="sxs-lookup"><span data-stu-id="2decf-123">If opening the root folder is successful, then use the returned reference to the **IMAPIFolder** object and **IMAPIProp::GetProps** to obtain the desired property.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="2decf-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="2decf-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2decf-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="2decf-125">Protocol specifications</span></span>

<span data-ttu-id="2decf-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2decf-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2decf-127">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="2decf-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2decf-128">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2decf-128">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2decf-129">指定用于创建和定位邮箱中特殊文件夹的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2decf-129">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2decf-130">头文件</span><span class="sxs-lookup"><span data-stu-id="2decf-130">Header files</span></span>

<span data-ttu-id="2decf-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2decf-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="2decf-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2decf-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="2decf-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2decf-133">Mapitags.h</span></span>
  
> <span data-ttu-id="2decf-134">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2decf-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2decf-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2decf-135">See also</span></span>



[<span data-ttu-id="2decf-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2decf-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2decf-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2decf-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2decf-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2decf-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2decf-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2decf-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

