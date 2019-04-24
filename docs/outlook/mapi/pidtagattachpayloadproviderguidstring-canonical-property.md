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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5051784ea08316477f3c8888ada9170e3d99c2b5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361101"
---
# <a name="pidtagattachpayloadproviderguidstring-canonical-property"></a><span data-ttu-id="4831a-103">PidTagAttachPayloadProviderGuidString 规范属性</span><span class="sxs-lookup"><span data-stu-id="4831a-103">PidTagAttachPayloadProviderGuidString Canonical Property</span></span>

  
  
<span data-ttu-id="4831a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4831a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4831a-105">包含 MIME X 有效负载提供程序-Guid 标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="4831a-105">Contains the value of a MIME X-Payload-Provider-Guid header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4831a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4831a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4831a-107">PR_ATTACH_PAYLOAD_PROV_GUID_STR、PR_ATTACH_PAYLOAD_PROV_GUID_STR_A、PR_ATTACH_PAYLOAD_PROV_GUID_STR_W</span><span class="sxs-lookup"><span data-stu-id="4831a-107">PR_ATTACH_PAYLOAD_PROV_GUID_STR, PR_ATTACH_PAYLOAD_PROV_GUID_STR_A, PR_ATTACH_PAYLOAD_PROV_GUID_STR_W</span></span>  <br/> |
|<span data-ttu-id="4831a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4831a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4831a-109">0x3719</span><span class="sxs-lookup"><span data-stu-id="4831a-109">0x3719</span></span>  <br/> |
|<span data-ttu-id="4831a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4831a-110">Data type:</span></span>  <br/> |<span data-ttu-id="4831a-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4831a-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="4831a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4831a-112">Area:</span></span>  <br/> |<span data-ttu-id="4831a-113">Outlook 应用程序</span><span class="sxs-lookup"><span data-stu-id="4831a-113">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4831a-114">注解</span><span class="sxs-lookup"><span data-stu-id="4831a-114">Remarks</span></span>

<span data-ttu-id="4831a-115">若要设置这些属性的值, mime 客户端应将 X 有效载荷提供程序-Guid 标头字段写入将作为附件进行分析的 MIME 实体。</span><span class="sxs-lookup"><span data-stu-id="4831a-115">To set the value of these properties, MIME clients should write an X-Payload-Provider-Guid header field to a MIME entity that will be analyzed as an attachment.</span></span>
  
<span data-ttu-id="4831a-116">MIME 读取器必须将此头字段值复制到相应属性的值。</span><span class="sxs-lookup"><span data-stu-id="4831a-116">MIME readers must copy this header field value to the value of the corresponding property.</span></span> <span data-ttu-id="4831a-117">mime 阅读者在作为邮件或邮件正文而不是附件进行分析的 MIME 实体上显示时, 应忽略此头字段。</span><span class="sxs-lookup"><span data-stu-id="4831a-117">MIME readers should ignore this header field when it appears on a MIME entity that is analyzed as a message or message body, rather than as an attachment.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4831a-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="4831a-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4831a-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="4831a-119">Protocol specifications</span></span>

<span data-ttu-id="4831a-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4831a-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4831a-121">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="4831a-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4831a-122">[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4831a-122">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4831a-123">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="4831a-123">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4831a-124">头文件</span><span class="sxs-lookup"><span data-stu-id="4831a-124">Header files</span></span>

<span data-ttu-id="4831a-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="4831a-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="4831a-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4831a-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="4831a-127">Mapitags</span><span class="sxs-lookup"><span data-stu-id="4831a-127">Mapitags.h</span></span>
  
> <span data-ttu-id="4831a-128">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4831a-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4831a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4831a-129">See also</span></span>



[<span data-ttu-id="4831a-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4831a-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4831a-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4831a-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4831a-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4831a-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4831a-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4831a-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

