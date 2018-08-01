---
title: PidLidEmail3OriginalDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail3OriginalDisplayName
api_type:
- COM
ms.assetid: f3fa392a-c3b1-46dd-bf9b-5ce310719542
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ac90910e143d05c17b73aa6a1062cd0999b0d3c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776775"
---
# <a name="pidlidemail3originaldisplayname-canonical-property"></a><span data-ttu-id="6efe9-103">PidLidEmail3OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="6efe9-103">PidLidEmail3OriginalDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="6efe9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6efe9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6efe9-105">指定对应于指定为该联系人的电子邮件地址的第三个显示名称。</span><span class="sxs-lookup"><span data-stu-id="6efe9-105">Specifies the third display name that corresponds to the email address that is specified for the contact.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6efe9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6efe9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6efe9-107">dispidEmail3OriginalDisplayName</span><span class="sxs-lookup"><span data-stu-id="6efe9-107">dispidEmail3OriginalDisplayName</span></span>  <br/> |
|<span data-ttu-id="6efe9-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="6efe9-108">Property set:</span></span>  <br/> |<span data-ttu-id="6efe9-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="6efe9-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="6efe9-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="6efe9-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="6efe9-111">0x000080A4</span><span class="sxs-lookup"><span data-stu-id="6efe9-111">0x000080A4</span></span>  <br/> |
|<span data-ttu-id="6efe9-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6efe9-112">Data type:</span></span>  <br/> |<span data-ttu-id="6efe9-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="6efe9-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="6efe9-114">区域：</span><span class="sxs-lookup"><span data-stu-id="6efe9-114">Area:</span></span>  <br/> |<span data-ttu-id="6efe9-115">联系人</span><span class="sxs-lookup"><span data-stu-id="6efe9-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6efe9-116">说明</span><span class="sxs-lookup"><span data-stu-id="6efe9-116">Remarks</span></span>

<span data-ttu-id="6efe9-117">如果**dispidEmail3AddrType** ([PidLidEmail3AddressType](pidlidemail3addresstype-canonical-property.md)) 属性的值为"SMTP"，各自**dispidEmail3OriginalDisplayName**属性的值应等于各自**的值dispidEmail3EmailAddress** ([PidLidEmail3EmailAddress](pidlidemail3emailaddress-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="6efe9-117">If the value of the **dispidEmail3AddrType** ([PidLidEmail3AddressType](pidlidemail3addresstype-canonical-property.md)) property is "SMTP", the value of the respective **dispidEmail3OriginalDisplayName** property should equal the value of the respective **dispidEmail3EmailAddress** ([PidLidEmail3EmailAddress](pidlidemail3emailaddress-canonical-property.md)).</span></span> <span data-ttu-id="6efe9-118">此属性的用途是显示的替代的用户友好地址，它等效于**dispidEmail3EmailAddress**中。</span><span class="sxs-lookup"><span data-stu-id="6efe9-118">The purpose of this property is to display an alternative user-friendly address that is equivalent to the one in the **dispidEmail3EmailAddress**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6efe9-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="6efe9-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6efe9-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="6efe9-120">Protocol specifications</span></span>

<span data-ttu-id="6efe9-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6efe9-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6efe9-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6efe9-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6efe9-123">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6efe9-123">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6efe9-124">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="6efe9-124">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6efe9-125">头文件</span><span class="sxs-lookup"><span data-stu-id="6efe9-125">Header files</span></span>

<span data-ttu-id="6efe9-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6efe9-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="6efe9-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6efe9-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6efe9-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6efe9-128">See also</span></span>



[<span data-ttu-id="6efe9-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6efe9-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6efe9-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6efe9-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6efe9-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6efe9-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6efe9-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6efe9-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

