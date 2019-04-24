---
title: PidTagIpmSentMailEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmSentMailEntryId
api_type:
- HeaderDef
ms.assetid: f6877435-6b26-4060-924f-a65591ad9538
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fd29afc93bc952bb619dfac752fae232bf7991cf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327846"
---
# <a name="pidtagipmsentmailentryid-canonical-property"></a><span data-ttu-id="f0371-103">PidTagIpmSentMailEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="f0371-103">PidTagIpmSentMailEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="f0371-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f0371-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f0371-105">包含标准人际邮件 (IPM) "已发送邮件" 文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="f0371-105">Contains the entry identifier of the standard interpersonal message (IPM) Sent Items folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f0371-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f0371-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f0371-107">PR_IPM_SENTMAIL_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="f0371-107">PR_IPM_SENTMAIL_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="f0371-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f0371-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f0371-109">0x35E4</span><span class="sxs-lookup"><span data-stu-id="f0371-109">0x35E4</span></span>  <br/> |
|<span data-ttu-id="f0371-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f0371-110">Data type:</span></span>  <br/> |<span data-ttu-id="f0371-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="f0371-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="f0371-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f0371-112">Area:</span></span>  <br/> |<span data-ttu-id="f0371-113">Folder</span><span class="sxs-lookup"><span data-stu-id="f0371-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f0371-114">注解</span><span class="sxs-lookup"><span data-stu-id="f0371-114">Remarks</span></span>

<span data-ttu-id="f0371-115">发送时, 人际邮件通常放在 "已发送邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f0371-115">After being sent, interpersonal messages are usually placed in the Sent Items folder.</span></span> <span data-ttu-id="f0371-116">客户端可以使用此属性在提交的邮件上设置**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="f0371-116">A client can use this property to set the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property on a submitted message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="f0371-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="f0371-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f0371-118">头文件</span><span class="sxs-lookup"><span data-stu-id="f0371-118">Header files</span></span>

<span data-ttu-id="f0371-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="f0371-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="f0371-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f0371-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="f0371-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="f0371-121">Mapitags.h</span></span>
  
> <span data-ttu-id="f0371-122">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f0371-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f0371-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0371-123">See also</span></span>



[<span data-ttu-id="f0371-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f0371-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f0371-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f0371-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f0371-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f0371-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f0371-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f0371-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

