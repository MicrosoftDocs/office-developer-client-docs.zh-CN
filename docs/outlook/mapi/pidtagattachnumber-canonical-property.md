---
title: PidTagAttachNumber 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachNumber
api_type:
- HeaderDef
ms.assetid: 507e0f2c-383c-4e2f-917b-159913f7234d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f6de157864bff5be41b6e030d555be7b60dcda5e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594752"
---
# <a name="pidtagattachnumber-canonical-property"></a><span data-ttu-id="f74cd-103">PidTagAttachNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="f74cd-103">PidTagAttachNumber Canonical Property</span></span>

  
  
<span data-ttu-id="f74cd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f74cd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f74cd-105">包含唯一标识其父消息中的附件数。</span><span class="sxs-lookup"><span data-stu-id="f74cd-105">Contains a number that uniquely identifies the attachment within its parent message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f74cd-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f74cd-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f74cd-107">PR_ATTACH_NUM</span><span class="sxs-lookup"><span data-stu-id="f74cd-107">PR_ATTACH_NUM</span></span>  <br/> |
|<span data-ttu-id="f74cd-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f74cd-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f74cd-109">0x0E21</span><span class="sxs-lookup"><span data-stu-id="f74cd-109">0x0E21</span></span>  <br/> |
|<span data-ttu-id="f74cd-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f74cd-110">Data type:</span></span>  <br/> |<span data-ttu-id="f74cd-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="f74cd-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="f74cd-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f74cd-112">Area:</span></span>  <br/> |<span data-ttu-id="f74cd-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="f74cd-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f74cd-114">注解</span><span class="sxs-lookup"><span data-stu-id="f74cd-114">Remarks</span></span>

<span data-ttu-id="f74cd-115">消息存储生成和维护此属性。</span><span class="sxs-lookup"><span data-stu-id="f74cd-115">Message stores generate and maintain this property.</span></span> <span data-ttu-id="f74cd-116">附件数是次要排序关键字后的呈现位置，以对附件表。</span><span class="sxs-lookup"><span data-stu-id="f74cd-116">The attachment number is the secondary sort key, after the rendering position, in the attachment table.</span></span> 
  
 <span data-ttu-id="f74cd-117">**PR_ATTACH_NUM**用于与[IMessage::OpenAttach](imessage-openattach.md)方法打开附件。</span><span class="sxs-lookup"><span data-stu-id="f74cd-117">**PR_ATTACH_NUM** is used to open the attachment with the [IMessage::OpenAttach](imessage-openattach.md) method.</span></span> <span data-ttu-id="f74cd-118">客户端应用程序的会话中的邮件附件的**PR_ATTACH_NUM**属性保持不变，只要附件表处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="f74cd-118">Within a client application's session, the **PR_ATTACH_NUM** property of a message attachment remains constant as long as the attachment table is open.</span></span> 
  
<span data-ttu-id="f74cd-119">消息存储将更改传播到使用**IMessage::CreateAttach**和**IMessage::DeleteAttach**方法的表。</span><span class="sxs-lookup"><span data-stu-id="f74cd-119">The message store propagates changes to the table using the **IMessage::CreateAttach** and **IMessage::DeleteAttach** methods.</span></span> <span data-ttu-id="f74cd-120">自行选择消息存储可以生成对打开附件表的表通知，以便客户端可以重新同步到这些更改。</span><span class="sxs-lookup"><span data-stu-id="f74cd-120">At its option the message store can generate table notifications on open attachment tables so that clients can resynchronize to those changes.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="f74cd-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="f74cd-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f74cd-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="f74cd-122">Protocol specifications</span></span>

<span data-ttu-id="f74cd-123">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f74cd-123">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f74cd-124">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="f74cd-124">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f74cd-125">头文件</span><span class="sxs-lookup"><span data-stu-id="f74cd-125">Header files</span></span>

<span data-ttu-id="f74cd-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f74cd-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="f74cd-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f74cd-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="f74cd-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f74cd-128">Mapitags.h</span></span>
  
> <span data-ttu-id="f74cd-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f74cd-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f74cd-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f74cd-130">See also</span></span>



[<span data-ttu-id="f74cd-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f74cd-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f74cd-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f74cd-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f74cd-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f74cd-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f74cd-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f74cd-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

