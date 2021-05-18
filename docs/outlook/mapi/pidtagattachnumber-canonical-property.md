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
ms.openlocfilehash: 474ffaf2317cadd214074419f09bb913b1eee4ff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327249"
---
# <a name="pidtagattachnumber-canonical-property"></a><span data-ttu-id="373ec-103">PidTagAttachNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="373ec-103">PidTagAttachNumber Canonical Property</span></span>

  
  
<span data-ttu-id="373ec-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="373ec-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="373ec-105">包含一个唯一标识其父邮件中的附件的编号。</span><span class="sxs-lookup"><span data-stu-id="373ec-105">Contains a number that uniquely identifies the attachment within its parent message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="373ec-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="373ec-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="373ec-107">PR_ATTACH_NUM</span><span class="sxs-lookup"><span data-stu-id="373ec-107">PR_ATTACH_NUM</span></span>  <br/> |
|<span data-ttu-id="373ec-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="373ec-108">Identifier:</span></span>  <br/> |<span data-ttu-id="373ec-109">0x0E21</span><span class="sxs-lookup"><span data-stu-id="373ec-109">0x0E21</span></span>  <br/> |
|<span data-ttu-id="373ec-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="373ec-110">Data type:</span></span>  <br/> |<span data-ttu-id="373ec-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="373ec-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="373ec-112">区域：</span><span class="sxs-lookup"><span data-stu-id="373ec-112">Area:</span></span>  <br/> |<span data-ttu-id="373ec-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="373ec-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="373ec-114">备注</span><span class="sxs-lookup"><span data-stu-id="373ec-114">Remarks</span></span>

<span data-ttu-id="373ec-115">邮件存储将生成和维护此属性。</span><span class="sxs-lookup"><span data-stu-id="373ec-115">Message stores generate and maintain this property.</span></span> <span data-ttu-id="373ec-116">附件编号是附件表中呈现位置后的辅助排序键。</span><span class="sxs-lookup"><span data-stu-id="373ec-116">The attachment number is the secondary sort key, after the rendering position, in the attachment table.</span></span> 
  
 <span data-ttu-id="373ec-117">**PR_ATTACH_NUM** [IMessage：：OpenAttach 方法打开附件](imessage-openattach.md) 。</span><span class="sxs-lookup"><span data-stu-id="373ec-117">**PR_ATTACH_NUM** is used to open the attachment with the [IMessage::OpenAttach](imessage-openattach.md) method.</span></span> <span data-ttu-id="373ec-118">在客户端应用程序的会话中，只要PR_ATTACH_NUM表处于打开状态，邮件附件的 PR_ATTACH_NUM 属性就保持不变。</span><span class="sxs-lookup"><span data-stu-id="373ec-118">Within a client application's session, the **PR_ATTACH_NUM** property of a message attachment remains constant as long as the attachment table is open.</span></span> 
  
<span data-ttu-id="373ec-119">邮件存储使用 **IMessage：：CreateAttach** 和 **IMessage：:D eleteAttach** 方法将更改传播到表。</span><span class="sxs-lookup"><span data-stu-id="373ec-119">The message store propagates changes to the table using the **IMessage::CreateAttach** and **IMessage::DeleteAttach** methods.</span></span> <span data-ttu-id="373ec-120">邮件存储可以选择在打开的附件表上生成表通知，以便客户端可以重新同步这些更改。</span><span class="sxs-lookup"><span data-stu-id="373ec-120">At its option the message store can generate table notifications on open attachment tables so that clients can resynchronize to those changes.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="373ec-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="373ec-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="373ec-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="373ec-122">Protocol specifications</span></span>

<span data-ttu-id="373ec-123">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="373ec-123">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="373ec-124">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="373ec-124">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="373ec-125">头文件</span><span class="sxs-lookup"><span data-stu-id="373ec-125">Header files</span></span>

<span data-ttu-id="373ec-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="373ec-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="373ec-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="373ec-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="373ec-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="373ec-128">Mapitags.h</span></span>
  
> <span data-ttu-id="373ec-129">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="373ec-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="373ec-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="373ec-130">See also</span></span>



[<span data-ttu-id="373ec-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="373ec-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="373ec-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="373ec-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="373ec-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="373ec-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="373ec-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="373ec-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

