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
ms.openlocfilehash: c4a46710311f2c4d26ec3d667c7bf535df69f595
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777357"
---
# <a name="pidtagattachnumber-canonical-property"></a><span data-ttu-id="98629-103">PidTagAttachNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="98629-103">PidTagAttachNumber Canonical Property</span></span>

  
  
<span data-ttu-id="98629-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="98629-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="98629-105">包含唯一标识其父消息中的附件数。</span><span class="sxs-lookup"><span data-stu-id="98629-105">Contains a number that uniquely identifies the attachment within its parent message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="98629-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="98629-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="98629-107">PR_ATTACH_NUM</span><span class="sxs-lookup"><span data-stu-id="98629-107">PR_ATTACH_NUM</span></span>  <br/> |
|<span data-ttu-id="98629-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="98629-108">Identifier:</span></span>  <br/> |<span data-ttu-id="98629-109">0x0E21</span><span class="sxs-lookup"><span data-stu-id="98629-109">0x0E21</span></span>  <br/> |
|<span data-ttu-id="98629-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="98629-110">Data type:</span></span>  <br/> |<span data-ttu-id="98629-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="98629-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="98629-112">区域：</span><span class="sxs-lookup"><span data-stu-id="98629-112">Area:</span></span>  <br/> |<span data-ttu-id="98629-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="98629-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="98629-114">说明</span><span class="sxs-lookup"><span data-stu-id="98629-114">Remarks</span></span>

<span data-ttu-id="98629-115">消息存储生成和维护此属性。</span><span class="sxs-lookup"><span data-stu-id="98629-115">Message stores generate and maintain this property.</span></span> <span data-ttu-id="98629-116">附件数是次要排序关键字后的呈现位置，以对附件表。</span><span class="sxs-lookup"><span data-stu-id="98629-116">The attachment number is the secondary sort key, after the rendering position, in the attachment table.</span></span> 
  
 <span data-ttu-id="98629-117">**PR_ATTACH_NUM**用于与[IMessage::OpenAttach](imessage-openattach.md)方法打开附件。</span><span class="sxs-lookup"><span data-stu-id="98629-117">**PR_ATTACH_NUM** is used to open the attachment with the [IMessage::OpenAttach](imessage-openattach.md) method.</span></span> <span data-ttu-id="98629-118">客户端应用程序的会话中的邮件附件的**PR_ATTACH_NUM**属性保持不变，只要附件表处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="98629-118">Within a client application's session, the **PR_ATTACH_NUM** property of a message attachment remains constant as long as the attachment table is open.</span></span> 
  
<span data-ttu-id="98629-119">消息存储将更改传播到使用**IMessage::CreateAttach**和**IMessage::DeleteAttach**方法的表。</span><span class="sxs-lookup"><span data-stu-id="98629-119">The message store propagates changes to the table using the **IMessage::CreateAttach** and **IMessage::DeleteAttach** methods.</span></span> <span data-ttu-id="98629-120">自行选择消息存储可以生成对打开附件表的表通知，以便客户端可以重新同步到这些更改。</span><span class="sxs-lookup"><span data-stu-id="98629-120">At its option the message store can generate table notifications on open attachment tables so that clients can resynchronize to those changes.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="98629-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="98629-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="98629-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="98629-122">Protocol specifications</span></span>

<span data-ttu-id="98629-123">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="98629-123">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="98629-124">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="98629-124">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="98629-125">头文件</span><span class="sxs-lookup"><span data-stu-id="98629-125">Header files</span></span>

<span data-ttu-id="98629-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="98629-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="98629-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="98629-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="98629-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="98629-128">Mapitags.h</span></span>
  
> <span data-ttu-id="98629-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="98629-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="98629-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98629-130">See also</span></span>



[<span data-ttu-id="98629-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="98629-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="98629-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="98629-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="98629-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="98629-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="98629-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="98629-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

