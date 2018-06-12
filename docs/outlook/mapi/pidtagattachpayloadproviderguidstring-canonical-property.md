---
title: PidTagAttachPayloadProviderGuidString 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachPayloadProviderGuidString
api_type:
- HeaderDef
ms.assetid: c9d4b561-53b3-492b-9324-9376dd7abddf
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 9e581f040b3d7d9e204dd41431b1eba650b971a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777363"
---
# <a name="pidtagattachpayloadproviderguidstring-canonical-property"></a><span data-ttu-id="66374-103">PidTagAttachPayloadProviderGuidString 规范属性</span><span class="sxs-lookup"><span data-stu-id="66374-103">PidTagAttachPayloadProviderGuidString Canonical Property</span></span>

  
  
<span data-ttu-id="66374-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="66374-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="66374-105">包含 MIME X-负载的提供程序的 Guid 标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="66374-105">Contains the value of a MIME X-Payload-Provider-Guid header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="66374-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="66374-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="66374-107">PR_ATTACH_PAYLOAD_PROV_GUID_STR，PR_ATTACH_PAYLOAD_PROV_GUID_STR_A，PR_ATTACH_PAYLOAD_PROV_GUID_STR_W</span><span class="sxs-lookup"><span data-stu-id="66374-107">PR_ATTACH_PAYLOAD_PROV_GUID_STR, PR_ATTACH_PAYLOAD_PROV_GUID_STR_A, PR_ATTACH_PAYLOAD_PROV_GUID_STR_W</span></span>  <br/> |
|<span data-ttu-id="66374-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="66374-108">Identifier:</span></span>  <br/> |<span data-ttu-id="66374-109">0x3719</span><span class="sxs-lookup"><span data-stu-id="66374-109">0x3719</span></span>  <br/> |
|<span data-ttu-id="66374-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="66374-110">Data type:</span></span>  <br/> |<span data-ttu-id="66374-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="66374-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="66374-112">区域：</span><span class="sxs-lookup"><span data-stu-id="66374-112">Area:</span></span>  <br/> |<span data-ttu-id="66374-113">Outlook 应用程序</span><span class="sxs-lookup"><span data-stu-id="66374-113">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="66374-114">备注</span><span class="sxs-lookup"><span data-stu-id="66374-114">Remarks</span></span>

<span data-ttu-id="66374-115">若要设置这些属性的值，MIME 客户端应写入 X 负载提供程序 Guid 标头字段将分析作为附件的 MIME 实体。</span><span class="sxs-lookup"><span data-stu-id="66374-115">To set the value of these properties, MIME clients should write an X-Payload-Provider-Guid header field to a MIME entity that will be analyzed as an attachment.</span></span>
  
<span data-ttu-id="66374-116">MIME 读者必须将此标头字段值复制到相应属性的值。</span><span class="sxs-lookup"><span data-stu-id="66374-116">MIME readers must copy this header field value to the value of the corresponding property.</span></span> <span data-ttu-id="66374-117">分析作为邮件或邮件正文中，而不是作为附件的 MIME 实体上出现时，MIME 读者应忽略此标头字段。</span><span class="sxs-lookup"><span data-stu-id="66374-117">MIME readers should ignore this header field when it appears on a MIME entity that is analyzed as a message or message body, rather than as an attachment.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="66374-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="66374-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="66374-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="66374-119">Protocol specifications</span></span>

<span data-ttu-id="66374-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="66374-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="66374-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="66374-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="66374-122">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="66374-122">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="66374-123">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="66374-123">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="66374-124">头文件</span><span class="sxs-lookup"><span data-stu-id="66374-124">Header files</span></span>

<span data-ttu-id="66374-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="66374-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="66374-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="66374-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="66374-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="66374-127">Mapitags.h</span></span>
  
> <span data-ttu-id="66374-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="66374-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="66374-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66374-129">See also</span></span>



[<span data-ttu-id="66374-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="66374-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="66374-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="66374-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="66374-132">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="66374-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="66374-133">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="66374-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

