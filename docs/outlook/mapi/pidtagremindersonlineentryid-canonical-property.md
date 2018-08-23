---
title: PidTagRemindersOnlineEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRemindersOnlineEntryId
api_type:
- COM
ms.assetid: cad25cca-248d-4845-9d60-7aa60f2dda62
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b3d1d2a20720bd1c4b15464cd24aac4415721ae8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563175"
---
# <a name="pidtagremindersonlineentryid-canonical-property"></a><span data-ttu-id="1052d-103">PidTagRemindersOnlineEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="1052d-103">PidTagRemindersOnlineEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="1052d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1052d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1052d-105">包含提醒文件夹的**EntryID** 。</span><span class="sxs-lookup"><span data-stu-id="1052d-105">Contains the **EntryID** of the reminders folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1052d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1052d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1052d-107">PR_REM_ONLINE_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="1052d-107">PR_REM_ONLINE_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="1052d-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="1052d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1052d-109">0x36D5</span><span class="sxs-lookup"><span data-stu-id="1052d-109">0x36D5</span></span>  <br/> |
|<span data-ttu-id="1052d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1052d-110">Data type:</span></span>  <br/> |<span data-ttu-id="1052d-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="1052d-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="1052d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1052d-112">Area:</span></span>  <br/> |<span data-ttu-id="1052d-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="1052d-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1052d-114">注解</span><span class="sxs-lookup"><span data-stu-id="1052d-114">Remarks</span></span>

<span data-ttu-id="1052d-115">此属性存储和消息存储库的根文件夹中收件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="1052d-115">This property is stored in the Inbox folder and in the root folder of the message store.</span></span> <span data-ttu-id="1052d-116">若要访问特定的邮件存储区上的属性，请执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="1052d-116">To access the property on a specific message store, do the following.</span></span> 
  
1. <span data-ttu-id="1052d-117">首先，查找收件箱文件夹中的属性。</span><span class="sxs-lookup"><span data-stu-id="1052d-117">First, look for the property in the Inbox folder.</span></span> <span data-ttu-id="1052d-118">使用[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)获取收件箱文件夹的**EntryID**的引用。</span><span class="sxs-lookup"><span data-stu-id="1052d-118">Use [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) to obtain a reference to the **EntryID** for the Inbox folder.</span></span> 
    
2. <span data-ttu-id="1052d-119">如果**IMsgStore::GetReceiveFolder**操作成功，则使用**EntryID**的收件箱和[IMsgStore::OpenEntry](imsgstore-openentry.md)引用打开收件箱并获取**IMAPIFolder**对象的引用。</span><span class="sxs-lookup"><span data-stu-id="1052d-119">If **IMsgStore::GetReceiveFolder** is successful, then use the reference to the **EntryID** of the Inbox and [IMsgStore::OpenEntry](imsgstore-openentry.md) to open the Inbox and obtain a reference to an **IMAPIFolder** object.</span></span> 
    
3. <span data-ttu-id="1052d-120">如果**IMsgStore::OpenEntry**成功，然后使用**IMAPIFolder**对象和[IMAPIProp::GetProps](imapiprop-getprops.md)返回的参考获取所需的属性。</span><span class="sxs-lookup"><span data-stu-id="1052d-120">If **IMsgStore::OpenEntry** is successful, then use the returned reference to the **IMAPIFolder** object and [IMAPIProp::GetProps](imapiprop-getprops.md) to obtain the desired property.</span></span> 
    
4. <span data-ttu-id="1052d-121">如果步骤 1、 2 或 3 失败，查找的根文件夹中的属性。</span><span class="sxs-lookup"><span data-stu-id="1052d-121">If Step 1, 2, or 3 fails, look for the property in the root folder.</span></span> <span data-ttu-id="1052d-122">若要执行的操作，使用**IMsgStore::OpenEntry**，指定 NULL 的**lpEntryID**，打开的邮件存储区的根文件夹，并获取**IMAPIFolder**对象的引用。</span><span class="sxs-lookup"><span data-stu-id="1052d-122">To do that, use **IMsgStore::OpenEntry**, specifying NULL for **lpEntryID**, to open the root folder of the message store and obtain a reference to the **IMAPIFolder** object.</span></span> 
    
5. <span data-ttu-id="1052d-123">如果成功打开根文件夹，然后使用**IMAPIFolder**对象和**IMAPIProp::GetProps**返回的参考获取所需的属性。</span><span class="sxs-lookup"><span data-stu-id="1052d-123">If opening the root folder is successful, then use the returned reference to the **IMAPIFolder** object and **IMAPIProp::GetProps** to obtain the desired property.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="1052d-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="1052d-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1052d-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="1052d-125">Protocol specifications</span></span>

<span data-ttu-id="1052d-126">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1052d-126">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1052d-127">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="1052d-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1052d-128">[[MS OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1052d-128">[[MS-OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1052d-129">指定的属性和用于创建和邮箱中查找的特殊文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="1052d-129">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1052d-130">头文件</span><span class="sxs-lookup"><span data-stu-id="1052d-130">Header files</span></span>

<span data-ttu-id="1052d-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1052d-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="1052d-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1052d-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="1052d-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1052d-133">Mapitags.h</span></span>
  
> <span data-ttu-id="1052d-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1052d-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1052d-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1052d-135">See also</span></span>



[<span data-ttu-id="1052d-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1052d-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1052d-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1052d-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1052d-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1052d-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1052d-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1052d-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

