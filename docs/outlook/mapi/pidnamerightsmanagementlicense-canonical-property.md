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
ms.openlocfilehash: 1f528332c52664ac472670566c905d36dac65bfc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565527"
---
# <a name="pidnamerightsmanagementlicense-canonical-property"></a><span data-ttu-id="5a994-103">PidNameRightsManagementLicense 规范属性</span><span class="sxs-lookup"><span data-stu-id="5a994-103">PidNameRightsManagementLicense Canonical Property</span></span>

  
  
<span data-ttu-id="5a994-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5a994-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5a994-105">缓存权限管理电子邮件的使用许可证。</span><span class="sxs-lookup"><span data-stu-id="5a994-105">Caches the use license for the rights-managed email message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5a994-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="5a994-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="5a994-107">无</span><span class="sxs-lookup"><span data-stu-id="5a994-107">None</span></span>  <br/> |
|<span data-ttu-id="5a994-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="5a994-108">Property set:</span></span>  <br/> |<span data-ttu-id="5a994-109">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="5a994-109">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="5a994-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="5a994-110">Property name:</span></span>  <br/> |<span data-ttu-id="5a994-111">DRMLicense</span><span class="sxs-lookup"><span data-stu-id="5a994-111">DRMLicense</span></span>  <br/> |
|<span data-ttu-id="5a994-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5a994-112">Data type:</span></span>  <br/> |<span data-ttu-id="5a994-113">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="5a994-113">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="5a994-114">区域：</span><span class="sxs-lookup"><span data-stu-id="5a994-114">Area:</span></span>  <br/> |<span data-ttu-id="5a994-115">安全邮件</span><span class="sxs-lookup"><span data-stu-id="5a994-115">Secure messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5a994-116">注解</span><span class="sxs-lookup"><span data-stu-id="5a994-116">Remarks</span></span>

<span data-ttu-id="5a994-117">如果该属性是存在对权限管理电子邮件，第一个此多个二进制属性的值必须包含权限管理电子邮件 （作为 [RFC1950] 中指定） 的 ZLIB 压缩的使用许可证。</span><span class="sxs-lookup"><span data-stu-id="5a994-117">If the property is present on a rights-managed email message, the first value of this multiple binary property must contain the ZLIB (as specified in [RFC1950]) compressed use license for the rights-managed email message.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5a994-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="5a994-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5a994-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="5a994-119">Protocol specifications</span></span>

<span data-ttu-id="5a994-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5a994-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5a994-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="5a994-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5a994-122">[[MS OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5a994-122">[[MS-OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5a994-123">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="5a994-123">Specifies the properties of rights-managed encoded messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5a994-124">头文件</span><span class="sxs-lookup"><span data-stu-id="5a994-124">Header files</span></span>

<span data-ttu-id="5a994-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5a994-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="5a994-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5a994-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5a994-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a994-127">See also</span></span>



[<span data-ttu-id="5a994-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5a994-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5a994-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5a994-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5a994-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5a994-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5a994-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5a994-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

