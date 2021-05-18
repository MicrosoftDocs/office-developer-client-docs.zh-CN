---
title: PidTagIpmContactEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmContactEntryId
api_type:
- HeaderDef
ms.assetid: fccbbb15-dd08-4310-83d7-bf57eb3ed5de
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8f0c79fa098b8bca0518921a25d88a229e23e955
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327900"
---
# <a name="pidtagipmcontactentryid-canonical-property"></a><span data-ttu-id="15563-103">PidTagIpmContactEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="15563-103">PidTagIpmContactEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="15563-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="15563-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="15563-105">包含 **联系人** 文件夹Outlook条目 ID。</span><span class="sxs-lookup"><span data-stu-id="15563-105">Contains the **EntryID** of the Outlook Contacts folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="15563-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="15563-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="15563-107">PR_IPM_CONTACT_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="15563-107">PR_IPM_CONTACT_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="15563-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="15563-108">Identifier:</span></span>  <br/> |<span data-ttu-id="15563-109">0x36D1</span><span class="sxs-lookup"><span data-stu-id="15563-109">0x36D1</span></span>  <br/> |
|<span data-ttu-id="15563-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="15563-110">Data type:</span></span>  <br/> |<span data-ttu-id="15563-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="15563-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="15563-112">区域：</span><span class="sxs-lookup"><span data-stu-id="15563-112">Area:</span></span>  <br/> |<span data-ttu-id="15563-113">文件夹</span><span class="sxs-lookup"><span data-stu-id="15563-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="15563-114">备注</span><span class="sxs-lookup"><span data-stu-id="15563-114">Remarks</span></span>

<span data-ttu-id="15563-115">此属性存储在收件箱文件夹和邮件存储的根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="15563-115">This property is stored in the Inbox folder and in the root folder of the message store.</span></span> <span data-ttu-id="15563-116">若要访问特定邮件存储上的 属性，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="15563-116">To access the property on a specific message store, do the following:</span></span> 
  
1. <span data-ttu-id="15563-117">首先，在"收件箱"文件夹中查找 属性。</span><span class="sxs-lookup"><span data-stu-id="15563-117">First, look for the property in the Inbox folder.</span></span> <span data-ttu-id="15563-118">使用 **IMsgStore：：GetReceiveFolder** 获取对 **"收件箱"文件夹的 EntryID** 的引用。</span><span class="sxs-lookup"><span data-stu-id="15563-118">Use **IMsgStore::GetReceiveFolder** to obtain a reference to the **EntryID** for the Inbox folder.</span></span> 
    
2. <span data-ttu-id="15563-119">如果 **IMsgStore：：GetReceiveFolder** 成功，则使用对收件箱和 **IMsgStore：：OpenEntry** **的 EntryID** 的引用打开收件箱并获取对 **IMAPIFolder** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="15563-119">If **IMsgStore::GetReceiveFolder** is successful, then use the reference to the **EntryID** of the Inbox and **IMsgStore::OpenEntry** to open the Inbox and obtain a reference to an **IMAPIFolder** object.</span></span> 
    
3. <span data-ttu-id="15563-120">如果 **IMsgStore：：OpenEntry** 成功，则使用对 **IMAPIFolder** 对象和 **IMAPIProp：：GetProps** 的返回引用获取所需属性。</span><span class="sxs-lookup"><span data-stu-id="15563-120">If **IMsgStore::OpenEntry** is successful, then use the returned reference to the **IMAPIFolder** object and **IMAPIProp::GetProps** to obtain the desired property.</span></span> 
    
4. <span data-ttu-id="15563-121">如果步骤 1、2 或 3 失败，则查找根文件夹中的属性。</span><span class="sxs-lookup"><span data-stu-id="15563-121">If Step 1, 2, or 3 fails, look for the property in the root folder.</span></span> <span data-ttu-id="15563-122">为此，请使用 **IMsgStore：：OpenEntry（** 为 \*\* lpEntryID \*\* 指定 NULL）打开邮件存储的根文件夹并获取对 **IMAPIFolder** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="15563-122">To do that, use **IMsgStore::OpenEntry**, specifying NULL for \*\* lpEntryID \*\*, to open the root folder of the message store and obtain a reference to the **IMAPIFolder** object.</span></span> 
    
5. <span data-ttu-id="15563-123">如果打开根文件夹成功，则使用返回的 **对 IMAPIFolder** 对象和 **IMAPIProp：：GetProps** 的引用获取所需属性。</span><span class="sxs-lookup"><span data-stu-id="15563-123">If opening the root folder is successful, then use the returned reference to the **IMAPIFolder** object and **IMAPIProp::GetProps** to obtain the desired property.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="15563-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="15563-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="15563-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="15563-125">Protocol specifications</span></span>

<span data-ttu-id="15563-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15563-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15563-127">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="15563-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="15563-128">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15563-128">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15563-129">指定用于创建和定位邮箱中特殊文件夹的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="15563-129">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="15563-130">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15563-130">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15563-131">指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。</span><span class="sxs-lookup"><span data-stu-id="15563-131">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="15563-132">头文件</span><span class="sxs-lookup"><span data-stu-id="15563-132">Header files</span></span>

<span data-ttu-id="15563-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="15563-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="15563-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="15563-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="15563-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="15563-135">Mapitags.h</span></span>
  
> <span data-ttu-id="15563-136">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="15563-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="15563-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15563-137">See also</span></span>



[<span data-ttu-id="15563-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="15563-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="15563-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="15563-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="15563-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="15563-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="15563-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="15563-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

