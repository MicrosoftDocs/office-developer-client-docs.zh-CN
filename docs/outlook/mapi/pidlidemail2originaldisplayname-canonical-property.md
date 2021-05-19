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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7fb7e5afa6a1c050a5d91274bc4f82439fb98640
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337959"
---
# <a name="pidlidemail2originaldisplayname-canonical-property"></a><span data-ttu-id="b22cd-103">PidLidEmail2OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="b22cd-103">PidLidEmail2OriginalDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="b22cd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b22cd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b22cd-105">指定对应于显示名称电子邮件地址的第二个联系人。</span><span class="sxs-lookup"><span data-stu-id="b22cd-105">Specifies the second display name that corresponds to the email address specified for the contact.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b22cd-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b22cd-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b22cd-107">dispidEmail2OriginalDisplayName</span><span class="sxs-lookup"><span data-stu-id="b22cd-107">dispidEmail2OriginalDisplayName</span></span>  <br/> |
|<span data-ttu-id="b22cd-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="b22cd-108">Property set:</span></span>  <br/> |<span data-ttu-id="b22cd-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="b22cd-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="b22cd-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="b22cd-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b22cd-111">0x00008094</span><span class="sxs-lookup"><span data-stu-id="b22cd-111">0x00008094</span></span>  <br/> |
|<span data-ttu-id="b22cd-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b22cd-112">Data type:</span></span>  <br/> |<span data-ttu-id="b22cd-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b22cd-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="b22cd-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b22cd-114">Area:</span></span>  <br/> |<span data-ttu-id="b22cd-115">联系人</span><span class="sxs-lookup"><span data-stu-id="b22cd-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b22cd-116">备注</span><span class="sxs-lookup"><span data-stu-id="b22cd-116">Remarks</span></span>

<span data-ttu-id="b22cd-117">如果 **dispidEmail2AddrType** ([PidLidEmail2AddressType](pidlidemail2addresstype-canonical-property.md)) 属性的值为"SMTP"，则各个 **PidLidEmail2OriginalDisplayName** 属性的值应等于各自的 **dispidEmail2EmailAddress** ([PidLidEmail2EmailAddress](pidlidemail2emailaddress-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b22cd-117">If the value of the **dispidEmail2AddrType** ([PidLidEmail2AddressType](pidlidemail2addresstype-canonical-property.md)) property is "SMTP", the value of the respective **PidLidEmail2OriginalDisplayName** property should equal the value of the respective **dispidEmail2EmailAddress** ([PidLidEmail2EmailAddress](pidlidemail2emailaddress-canonical-property.md)) property.</span></span> <span data-ttu-id="b22cd-118">此属性的目的是显示与 **dispidEmail2EmailAddress** 中的用户友好地址等效的替代用户友好地址。</span><span class="sxs-lookup"><span data-stu-id="b22cd-118">The purpose of this property is to display an alternative user-friendly address that is equivalent to the one in the **dispidEmail2EmailAddress**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b22cd-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="b22cd-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b22cd-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="b22cd-120">Protocol specifications</span></span>

<span data-ttu-id="b22cd-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b22cd-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b22cd-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="b22cd-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b22cd-123">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b22cd-123">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b22cd-124">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b22cd-124">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b22cd-125">头文件</span><span class="sxs-lookup"><span data-stu-id="b22cd-125">Header files</span></span>

<span data-ttu-id="b22cd-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b22cd-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="b22cd-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b22cd-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b22cd-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b22cd-128">See also</span></span>



[<span data-ttu-id="b22cd-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b22cd-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b22cd-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b22cd-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b22cd-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b22cd-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b22cd-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b22cd-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

