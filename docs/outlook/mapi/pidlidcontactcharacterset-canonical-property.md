---
title: PidLidContactCharacterSet 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidContactCharacterSet
api_type:
- COM
ms.assetid: a167e199-a9b2-47f9-a90e-2abc7c29828c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0329147463db38fb8c547214788366444daed312
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319703"
---
# <a name="pidlidcontactcharacterset-canonical-property"></a><span data-ttu-id="68ab8-103">PidLidContactCharacterSet 规范属性</span><span class="sxs-lookup"><span data-stu-id="68ab8-103">PidLidContactCharacterSet Canonical Property</span></span>

  
  
<span data-ttu-id="68ab8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="68ab8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="68ab8-105">指定用于此联系人的字符集。</span><span class="sxs-lookup"><span data-stu-id="68ab8-105">Specifies the character set used for this contact.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="68ab8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="68ab8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="68ab8-107">dispidContactCharSet</span><span class="sxs-lookup"><span data-stu-id="68ab8-107">dispidContactCharSet</span></span>  <br/> |
|<span data-ttu-id="68ab8-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="68ab8-108">Property set:</span></span>  <br/> |<span data-ttu-id="68ab8-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="68ab8-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="68ab8-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="68ab8-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="68ab8-111">0x00008023</span><span class="sxs-lookup"><span data-stu-id="68ab8-111">0x00008023</span></span>  <br/> |
|<span data-ttu-id="68ab8-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="68ab8-112">Data type:</span></span>  <br/> |<span data-ttu-id="68ab8-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="68ab8-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="68ab8-114">区域：</span><span class="sxs-lookup"><span data-stu-id="68ab8-114">Area:</span></span>  <br/> |<span data-ttu-id="68ab8-115">联系人</span><span class="sxs-lookup"><span data-stu-id="68ab8-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="68ab8-116">备注</span><span class="sxs-lookup"><span data-stu-id="68ab8-116">Remarks</span></span>

<span data-ttu-id="68ab8-117">应用程序可以使用此属性帮助为 **dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)) 、dispidFileUnderList ([PidLidFileUnderList](pidlidfileunderlist-canonical-property.md)) 和 **dispidFileUnderId** ([PidLidFileUnderId](pidlidfileunderid-canonical-property.md)) 属性生成与字符集相关的选项列表。 </span><span class="sxs-lookup"><span data-stu-id="68ab8-117">Applications can use this property to aid in generating a character-set dependent list of choices for the **dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)) , **dispidFileUnderList** ([PidLidFileUnderList](pidlidfileunderlist-canonical-property.md)) , and **dispidFileUnderId** ([PidLidFileUnderId](pidlidfileunderid-canonical-property.md)) properties.</span></span> <span data-ttu-id="68ab8-118">如果属性的值为"0x00000000"或"0x00000001"，则应用程序应该将该属性视为未设置。</span><span class="sxs-lookup"><span data-stu-id="68ab8-118">If the value of the property is "0x00000000" or "0x00000001", applications should treat the property as not being set.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="68ab8-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="68ab8-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="68ab8-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="68ab8-120">Protocol specifications</span></span>

<span data-ttu-id="68ab8-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="68ab8-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="68ab8-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="68ab8-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="68ab8-123">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="68ab8-123">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="68ab8-124">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="68ab8-124">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="68ab8-125">头文件</span><span class="sxs-lookup"><span data-stu-id="68ab8-125">Header files</span></span>

<span data-ttu-id="68ab8-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="68ab8-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="68ab8-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="68ab8-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="68ab8-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68ab8-128">See also</span></span>



[<span data-ttu-id="68ab8-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="68ab8-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="68ab8-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="68ab8-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="68ab8-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="68ab8-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="68ab8-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="68ab8-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

