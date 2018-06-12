---
title: PidTagOriginatorCertificate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginatorCertificate
api_type:
- COM
ms.assetid: 65f890d8-9d25-408e-ab29-89991278b92d
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 871ce5f594a75b9441d0434c3be47b2718540576
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777982"
---
# <a name="pidtagoriginatorcertificate-canonical-property"></a><span data-ttu-id="9bf30-103">PidTagOriginatorCertificate 规范属性</span><span class="sxs-lookup"><span data-stu-id="9bf30-103">PidTagOriginatorCertificate Canonical Property</span></span>

  
  
<span data-ttu-id="9bf30-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9bf30-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9bf30-105">包含消息创建者 ASN.1 证书。</span><span class="sxs-lookup"><span data-stu-id="9bf30-105">Contains an ASN.1 certificate for the message originator.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9bf30-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="9bf30-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9bf30-107">PR_ORIGINATOR_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="9bf30-107">PR_ORIGINATOR_CERTIFICATE</span></span>  <br/> |
|<span data-ttu-id="9bf30-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="9bf30-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9bf30-109">0x0022</span><span class="sxs-lookup"><span data-stu-id="9bf30-109">0x0022</span></span>  <br/> |
|<span data-ttu-id="9bf30-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9bf30-110">Data type:</span></span>  <br/> |<span data-ttu-id="9bf30-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="9bf30-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="9bf30-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9bf30-112">Area:</span></span>  <br/> |<span data-ttu-id="9bf30-113">MIME</span><span class="sxs-lookup"><span data-stu-id="9bf30-113">MIME</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9bf30-114">备注</span><span class="sxs-lookup"><span data-stu-id="9bf30-114">Remarks</span></span>

<span data-ttu-id="9bf30-115">此属性为原始发件人的**PR_USER_CERTIFICATE** ([PidTagUserCertificate](pidtagusercertificate-canonical-property.md)) 属性的副本。</span><span class="sxs-lookup"><span data-stu-id="9bf30-115">This property is a copy of the originator's **PR_USER_CERTIFICATE** ([PidTagUserCertificate](pidtagusercertificate-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9bf30-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="9bf30-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="9bf30-117">头文件</span><span class="sxs-lookup"><span data-stu-id="9bf30-117">Header files</span></span>

<span data-ttu-id="9bf30-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9bf30-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="9bf30-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9bf30-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="9bf30-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9bf30-120">Mapitags.h</span></span>
  
> <span data-ttu-id="9bf30-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9bf30-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9bf30-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9bf30-122">See also</span></span>



[<span data-ttu-id="9bf30-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9bf30-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9bf30-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9bf30-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9bf30-125">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9bf30-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9bf30-126">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9bf30-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

