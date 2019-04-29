---
title: PidTagOriginatingMtaCertificate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginatingMtaCertificate
api_type:
- COM
ms.assetid: f6b7ff0c-19a0-4cad-8868-c05397fcebf4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6f78609537b85a89617e7b2fa8f30a4ba952805b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414807"
---
# <a name="pidtagoriginatingmtacertificate-canonical-property"></a><span data-ttu-id="ad529-103">PidTagOriginatingMtaCertificate 规范属性</span><span class="sxs-lookup"><span data-stu-id="ad529-103">PidTagOriginatingMtaCertificate Canonical Property</span></span>

  
  
<span data-ttu-id="ad529-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ad529-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ad529-105">包含发出邮件的邮件传输代理 (MTA) 的标识符。</span><span class="sxs-lookup"><span data-stu-id="ad529-105">Contains an identifier for the message transfer agent (MTA) that originated the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ad529-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ad529-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ad529-107">PR_ORIGINATING_MTA_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="ad529-107">PR_ORIGINATING_MTA_CERTIFICATE</span></span>  <br/> |
|<span data-ttu-id="ad529-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ad529-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ad529-109">0x0E25</span><span class="sxs-lookup"><span data-stu-id="ad529-109">0x0E25</span></span>  <br/> |
|<span data-ttu-id="ad529-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ad529-110">Data type:</span></span>  <br/> |<span data-ttu-id="ad529-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="ad529-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="ad529-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ad529-112">Area:</span></span>  <br/> |<span data-ttu-id="ad529-113">服务器</span><span class="sxs-lookup"><span data-stu-id="ad529-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ad529-114">说明</span><span class="sxs-lookup"><span data-stu-id="ad529-114">Remarks</span></span>

<span data-ttu-id="ad529-115">如果设置此属性, 则该属性在 "已发送邮件" 文件夹中的已发送邮件中可用。</span><span class="sxs-lookup"><span data-stu-id="ad529-115">This property, if set, is available on sent messages in the Sent Items folder.</span></span>
  
<span data-ttu-id="ad529-116">此属性对应于每个邮件的400个报告属性。</span><span class="sxs-lookup"><span data-stu-id="ad529-116">This property corresponds to the X.400 report per-message attribute.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ad529-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="ad529-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="ad529-118">头文件</span><span class="sxs-lookup"><span data-stu-id="ad529-118">Header files</span></span>

<span data-ttu-id="ad529-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ad529-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="ad529-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ad529-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="ad529-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="ad529-121">Mapitags.h</span></span>
  
> <span data-ttu-id="ad529-122">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ad529-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ad529-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad529-123">See also</span></span>



[<span data-ttu-id="ad529-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ad529-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ad529-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ad529-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ad529-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ad529-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ad529-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ad529-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

