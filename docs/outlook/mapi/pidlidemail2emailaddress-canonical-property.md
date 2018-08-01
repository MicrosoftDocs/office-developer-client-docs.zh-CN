---
title: PidLidEmail2EmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail2EmailAddress
api_type:
- COM
ms.assetid: 89b33a24-395a-4a3f-bc05-a44529399d7c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0c1c463ee6a24f6ef0026264b6790ba50b146a09
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776756"
---
# <a name="pidlidemail2emailaddress-canonical-property"></a><span data-ttu-id="6f975-103">PidLidEmail2EmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="6f975-103">PidLidEmail2EmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="6f975-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6f975-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6f975-105">指定联系人的第二个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6f975-105">Specifies the second email address of the contact.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6f975-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6f975-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6f975-107">dispidEmail2EmailAddress</span><span class="sxs-lookup"><span data-stu-id="6f975-107">dispidEmail2EmailAddress</span></span>  <br/> |
|<span data-ttu-id="6f975-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="6f975-108">Property set:</span></span>  <br/> |<span data-ttu-id="6f975-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="6f975-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="6f975-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="6f975-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="6f975-111">0x00008093</span><span class="sxs-lookup"><span data-stu-id="6f975-111">0x00008093</span></span>  <br/> |
|<span data-ttu-id="6f975-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6f975-112">Data type:</span></span>  <br/> |<span data-ttu-id="6f975-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="6f975-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="6f975-114">区域：</span><span class="sxs-lookup"><span data-stu-id="6f975-114">Area:</span></span>  <br/> |<span data-ttu-id="6f975-115">联系人</span><span class="sxs-lookup"><span data-stu-id="6f975-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6f975-116">说明</span><span class="sxs-lookup"><span data-stu-id="6f975-116">Remarks</span></span>

<span data-ttu-id="6f975-117">此属性的值必须是适用于此电子邮件地址为指定的地址类型。</span><span class="sxs-lookup"><span data-stu-id="6f975-117">The value of this property must be appropriate for the address type specified for this email address.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6f975-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="6f975-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6f975-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="6f975-119">Protocol specifications</span></span>

<span data-ttu-id="6f975-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6f975-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6f975-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6f975-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6f975-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6f975-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6f975-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="6f975-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6f975-124">头文件</span><span class="sxs-lookup"><span data-stu-id="6f975-124">Header files</span></span>

<span data-ttu-id="6f975-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6f975-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="6f975-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6f975-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6f975-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f975-127">See also</span></span>



[<span data-ttu-id="6f975-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6f975-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6f975-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6f975-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6f975-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6f975-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6f975-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6f975-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

