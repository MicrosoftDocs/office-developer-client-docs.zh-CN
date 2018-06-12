---
title: PidLidEmail2OriginalDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail2OriginalDisplayName
api_type:
- COM
ms.assetid: 0b648ef6-86ed-40ee-b068-8fcde7e0fe75
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 2b3f59633fcea0b895cd024dbbbc106c8d492bf0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776750"
---
# <a name="pidlidemail2originaldisplayname-canonical-property"></a><span data-ttu-id="ff540-103">PidLidEmail2OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff540-103">PidLidEmail2OriginalDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="ff540-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ff540-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ff540-105">指定对应于指定为该联系人的电子邮件地址的第二个显示名称。</span><span class="sxs-lookup"><span data-stu-id="ff540-105">Specifies the second display name that corresponds to the email address specified for the contact.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ff540-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="ff540-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ff540-107">dispidEmail2OriginalDisplayName</span><span class="sxs-lookup"><span data-stu-id="ff540-107">dispidEmail2OriginalDisplayName</span></span>  <br/> |
|<span data-ttu-id="ff540-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="ff540-108">Property set:</span></span>  <br/> |<span data-ttu-id="ff540-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="ff540-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="ff540-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="ff540-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ff540-111">0x00008094</span><span class="sxs-lookup"><span data-stu-id="ff540-111">0x00008094</span></span>  <br/> |
|<span data-ttu-id="ff540-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ff540-112">Data type:</span></span>  <br/> |<span data-ttu-id="ff540-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ff540-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ff540-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ff540-114">Area:</span></span>  <br/> |<span data-ttu-id="ff540-115">联系人</span><span class="sxs-lookup"><span data-stu-id="ff540-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ff540-116">备注</span><span class="sxs-lookup"><span data-stu-id="ff540-116">Remarks</span></span>

<span data-ttu-id="ff540-117">如果**dispidEmail2AddrType** ([PidLidEmail2AddressType](pidlidemail2addresstype-canonical-property.md)) 属性的值为"SMTP"，各自的**PidLidEmail2OriginalDisplayName**属性的值应等于各自**的值dispidEmail2EmailAddress** ([PidLidEmail2EmailAddress](pidlidemail2emailaddress-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ff540-117">If the value of the **dispidEmail2AddrType** ([PidLidEmail2AddressType](pidlidemail2addresstype-canonical-property.md)) property is "SMTP", the value of the respective **PidLidEmail2OriginalDisplayName** property should equal the value of the respective **dispidEmail2EmailAddress** ([PidLidEmail2EmailAddress](pidlidemail2emailaddress-canonical-property.md)) property.</span></span> <span data-ttu-id="ff540-118">此属性的用途是显示的替代的用户友好地址，它等效于**dispidEmail2EmailAddress**中。</span><span class="sxs-lookup"><span data-stu-id="ff540-118">The purpose of this property is to display an alternative user-friendly address that is equivalent to the one in the **dispidEmail2EmailAddress**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ff540-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="ff540-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ff540-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="ff540-120">Protocol specifications</span></span>

<span data-ttu-id="ff540-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff540-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff540-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ff540-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ff540-123">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff540-123">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff540-124">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="ff540-124">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ff540-125">头文件</span><span class="sxs-lookup"><span data-stu-id="ff540-125">Header files</span></span>

<span data-ttu-id="ff540-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ff540-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="ff540-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ff540-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ff540-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff540-128">See also</span></span>



[<span data-ttu-id="ff540-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ff540-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ff540-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff540-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ff540-131">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ff540-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ff540-132">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ff540-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

