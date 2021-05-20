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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437320"
---
# <a name="pidtagipmsentmailentryid-canonical-property"></a><span data-ttu-id="d25d0-103">PidTagIpmSentMailEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="d25d0-103">PidTagIpmSentMailEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="d25d0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d25d0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d25d0-105">包含 IPM 和"已发送 (文件夹中) 邮件的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="d25d0-105">Contains the entry identifier of the standard interpersonal message (IPM) Sent Items folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d25d0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d25d0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d25d0-107">PR_IPM_SENTMAIL_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="d25d0-107">PR_IPM_SENTMAIL_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="d25d0-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d25d0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d25d0-109">0x35E4</span><span class="sxs-lookup"><span data-stu-id="d25d0-109">0x35E4</span></span>  <br/> |
|<span data-ttu-id="d25d0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d25d0-110">Data type:</span></span>  <br/> |<span data-ttu-id="d25d0-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d25d0-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d25d0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d25d0-112">Area:</span></span>  <br/> |<span data-ttu-id="d25d0-113">文件夹</span><span class="sxs-lookup"><span data-stu-id="d25d0-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d25d0-114">备注</span><span class="sxs-lookup"><span data-stu-id="d25d0-114">Remarks</span></span>

<span data-ttu-id="d25d0-115">发送后，通常将邮件放入"已发送项目"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d25d0-115">After being sent, interpersonal messages are usually placed in the Sent Items folder.</span></span> <span data-ttu-id="d25d0-116">客户端可以使用此属性对提交的邮件PR_SENTMAIL_ENTRYID ( [PidTagSentMailEntryId) PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)属性。</span><span class="sxs-lookup"><span data-stu-id="d25d0-116">A client can use this property to set the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property on a submitted message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d25d0-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="d25d0-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d25d0-118">头文件</span><span class="sxs-lookup"><span data-stu-id="d25d0-118">Header files</span></span>

<span data-ttu-id="d25d0-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d25d0-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="d25d0-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d25d0-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="d25d0-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d25d0-121">Mapitags.h</span></span>
  
> <span data-ttu-id="d25d0-122">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d25d0-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d25d0-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d25d0-123">See also</span></span>



[<span data-ttu-id="d25d0-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d25d0-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d25d0-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d25d0-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d25d0-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d25d0-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d25d0-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d25d0-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

