---
title: PidNameRightsManagementLicense 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameRightsManagementLicense
api_type:
- COM
ms.assetid: ca3c9317-7873-4f37-b78f-b35467c81c29
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 889b823a55c39ebc19e52c8cc9a1d078a5732a01
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315020"
---
# <a name="pidnamerightsmanagementlicense-canonical-property"></a><span data-ttu-id="fc110-103">PidNameRightsManagementLicense 规范属性</span><span class="sxs-lookup"><span data-stu-id="fc110-103">PidNameRightsManagementLicense Canonical Property</span></span>

  
  
<span data-ttu-id="fc110-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fc110-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fc110-105">缓存权限管理电子邮件的使用许可证。</span><span class="sxs-lookup"><span data-stu-id="fc110-105">Caches the use license for the rights-managed email message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fc110-106">友好名称:</span><span class="sxs-lookup"><span data-stu-id="fc110-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="fc110-107">无</span><span class="sxs-lookup"><span data-stu-id="fc110-107">None</span></span>  <br/> |
|<span data-ttu-id="fc110-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="fc110-108">Property set:</span></span>  <br/> |<span data-ttu-id="fc110-109">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="fc110-109">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="fc110-110">属性名称:</span><span class="sxs-lookup"><span data-stu-id="fc110-110">Property name:</span></span>  <br/> |<span data-ttu-id="fc110-111">DRMLicense</span><span class="sxs-lookup"><span data-stu-id="fc110-111">DRMLicense</span></span>  <br/> |
|<span data-ttu-id="fc110-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fc110-112">Data type:</span></span>  <br/> |<span data-ttu-id="fc110-113">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="fc110-113">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="fc110-114">区域：</span><span class="sxs-lookup"><span data-stu-id="fc110-114">Area:</span></span>  <br/> |<span data-ttu-id="fc110-115">安全邮件</span><span class="sxs-lookup"><span data-stu-id="fc110-115">Secure messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fc110-116">注解</span><span class="sxs-lookup"><span data-stu-id="fc110-116">Remarks</span></span>

<span data-ttu-id="fc110-117">如果权限管理的电子邮件上存在该属性, 则此多个 binary 属性的第一个值必须包含权限管理电子邮件的 ZLIB (在 [RFC1950] 中指定) 压缩使用许可证。</span><span class="sxs-lookup"><span data-stu-id="fc110-117">If the property is present on a rights-managed email message, the first value of this multiple binary property must contain the ZLIB (as specified in [RFC1950]) compressed use license for the rights-managed email message.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="fc110-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="fc110-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fc110-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="fc110-119">Protocol specifications</span></span>

<span data-ttu-id="fc110-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fc110-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fc110-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="fc110-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fc110-122">[[毫秒-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fc110-122">[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fc110-123">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="fc110-123">Specifies the properties of rights-managed encoded messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fc110-124">头文件</span><span class="sxs-lookup"><span data-stu-id="fc110-124">Header files</span></span>

<span data-ttu-id="fc110-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="fc110-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="fc110-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fc110-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fc110-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc110-127">See also</span></span>



[<span data-ttu-id="fc110-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fc110-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fc110-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fc110-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fc110-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fc110-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fc110-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fc110-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

