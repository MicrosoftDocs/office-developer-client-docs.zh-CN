---
title: PidLidImageAttachmentsCompressionLevel 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidImageAttachmentsCompressionLevel
api_type:
- COM
ms.assetid: cc169ba8-e9b7-42ad-8f0e-77b0843f95ea
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8600cc7071fbe5c08d5df074f9bf59f4320b7f18
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357580"
---
# <a name="pidlidimageattachmentscompressionlevel-canonical-property"></a><span data-ttu-id="50b71-103">PidLidImageAttachmentsCompressionLevel 规范属性</span><span class="sxs-lookup"><span data-stu-id="50b71-103">PidLidImageAttachmentsCompressionLevel Canonical Property</span></span>

  
  
<span data-ttu-id="50b71-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="50b71-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="50b71-105">定义要应用于图像附件的压缩级别。</span><span class="sxs-lookup"><span data-stu-id="50b71-105">Defines a compression level to apply on image attachments.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="50b71-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="50b71-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="50b71-107">dispidImgAttchmtsCompressLevel</span><span class="sxs-lookup"><span data-stu-id="50b71-107">dispidImgAttchmtsCompressLevel</span></span>  <br/> |
|<span data-ttu-id="50b71-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="50b71-108">Property set:</span></span>  <br/> |<span data-ttu-id="50b71-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="50b71-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="50b71-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="50b71-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="50b71-111">0x00008593</span><span class="sxs-lookup"><span data-stu-id="50b71-111">0x00008593</span></span>  <br/> |
|<span data-ttu-id="50b71-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="50b71-112">Data type:</span></span>  <br/> |<span data-ttu-id="50b71-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="50b71-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="50b71-114">区域：</span><span class="sxs-lookup"><span data-stu-id="50b71-114">Area:</span></span>  <br/> |<span data-ttu-id="50b71-115">运行时配置</span><span class="sxs-lookup"><span data-stu-id="50b71-115">Run-time configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="50b71-116">注解</span><span class="sxs-lookup"><span data-stu-id="50b71-116">Remarks</span></span>

<span data-ttu-id="50b71-117">以下是有效的压缩级别:</span><span class="sxs-lookup"><span data-stu-id="50b71-117">The following are valid compression levels:</span></span>
  
```cpp
enum PictureCompressLevel
{
 pclOriginal = 0,
 pclEmail = 1,
 pclWeb = 2,
 pclDocuments = 3,
};
```

## <a name="related-resources"></a><span data-ttu-id="50b71-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="50b71-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="50b71-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="50b71-119">Protocol specifications</span></span>

<span data-ttu-id="50b71-120">[[毫秒-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="50b71-120">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="50b71-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="50b71-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="50b71-122">头文件</span><span class="sxs-lookup"><span data-stu-id="50b71-122">Header files</span></span>

<span data-ttu-id="50b71-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="50b71-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="50b71-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="50b71-124">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="50b71-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50b71-125">See also</span></span>



[<span data-ttu-id="50b71-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="50b71-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="50b71-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="50b71-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="50b71-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="50b71-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="50b71-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="50b71-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

