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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 7c5cfa8f80895896eab9af5ce1f249b9b06cf425
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777977"
---
# <a name="pidtagoriginatingmtacertificate-canonical-property"></a><span data-ttu-id="610ab-103">PidTagOriginatingMtaCertificate 规范属性</span><span class="sxs-lookup"><span data-stu-id="610ab-103">PidTagOriginatingMtaCertificate Canonical Property</span></span>

  
  
<span data-ttu-id="610ab-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="610ab-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="610ab-105">发出邮件的邮件传输代理 (MTA) 中包含的标识符。</span><span class="sxs-lookup"><span data-stu-id="610ab-105">Contains an identifier for the message transfer agent (MTA) that originated the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="610ab-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="610ab-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="610ab-107">PR_ORIGINATING_MTA_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="610ab-107">PR_ORIGINATING_MTA_CERTIFICATE</span></span>  <br/> |
|<span data-ttu-id="610ab-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="610ab-108">Identifier:</span></span>  <br/> |<span data-ttu-id="610ab-109">0x0E25</span><span class="sxs-lookup"><span data-stu-id="610ab-109">0x0E25</span></span>  <br/> |
|<span data-ttu-id="610ab-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="610ab-110">Data type:</span></span>  <br/> |<span data-ttu-id="610ab-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="610ab-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="610ab-112">区域：</span><span class="sxs-lookup"><span data-stu-id="610ab-112">Area:</span></span>  <br/> |<span data-ttu-id="610ab-113">Server</span><span class="sxs-lookup"><span data-stu-id="610ab-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="610ab-114">备注</span><span class="sxs-lookup"><span data-stu-id="610ab-114">Remarks</span></span>

<span data-ttu-id="610ab-115">此属性，如果设置，可在发送邮件已发送邮件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="610ab-115">This property, if set, is available on sent messages in the Sent Items folder.</span></span>
  
<span data-ttu-id="610ab-116">此属性对应于 X.400 报告每封邮件属性。</span><span class="sxs-lookup"><span data-stu-id="610ab-116">This property corresponds to the X.400 report per-message attribute.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="610ab-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="610ab-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="610ab-118">头文件</span><span class="sxs-lookup"><span data-stu-id="610ab-118">Header files</span></span>

<span data-ttu-id="610ab-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="610ab-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="610ab-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="610ab-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="610ab-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="610ab-121">Mapitags.h</span></span>
  
> <span data-ttu-id="610ab-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="610ab-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="610ab-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="610ab-123">See also</span></span>



[<span data-ttu-id="610ab-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="610ab-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="610ab-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="610ab-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="610ab-126">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="610ab-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="610ab-127">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="610ab-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

