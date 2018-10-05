---
title: PidLidFileUnder 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFileUnder
api_type:
- COM
ms.assetid: 55afc4bb-c5fc-4162-a293-7d82644b1965
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 02aa1766421f7c116eabac4c9661be1b5b1adee1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393564"
---
# <a name="pidlidfileunder-canonical-property"></a><span data-ttu-id="1ad5f-103">PidLidFileUnder 规范属性</span><span class="sxs-lookup"><span data-stu-id="1ad5f-103">PidLidFileUnder Canonical Property</span></span>

  
  
<span data-ttu-id="1ad5f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1ad5f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1ad5f-105">指定联系人的所属存档时显示的联系人列表的名称。</span><span class="sxs-lookup"><span data-stu-id="1ad5f-105">Specifies the name under which the contact is filed when displaying a list of contacts.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1ad5f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1ad5f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1ad5f-107">dispidFileUnder</span><span class="sxs-lookup"><span data-stu-id="1ad5f-107">dispidFileUnder</span></span>  <br/> |
|<span data-ttu-id="1ad5f-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="1ad5f-108">Property set:</span></span>  <br/> |<span data-ttu-id="1ad5f-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="1ad5f-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="1ad5f-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="1ad5f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="1ad5f-111">0x00008005</span><span class="sxs-lookup"><span data-stu-id="1ad5f-111">0x00008005</span></span>  <br/> |
|<span data-ttu-id="1ad5f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1ad5f-112">Data type:</span></span>  <br/> |<span data-ttu-id="1ad5f-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="1ad5f-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="1ad5f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="1ad5f-114">Area:</span></span>  <br/> |<span data-ttu-id="1ad5f-115">联系人</span><span class="sxs-lookup"><span data-stu-id="1ad5f-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1ad5f-116">说明</span><span class="sxs-lookup"><span data-stu-id="1ad5f-116">Remarks</span></span>

<span data-ttu-id="1ad5f-117">应用程序应将视为空 PT_UNICODE 此属性，如果缺少从联系人。</span><span class="sxs-lookup"><span data-stu-id="1ad5f-117">The application should treat this property as an empty PT_UNICODE if it is missing from the contact.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1ad5f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="1ad5f-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1ad5f-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="1ad5f-119">Protocol specifications</span></span>

<span data-ttu-id="1ad5f-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1ad5f-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1ad5f-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="1ad5f-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1ad5f-122">[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1ad5f-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1ad5f-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="1ad5f-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1ad5f-124">头文件</span><span class="sxs-lookup"><span data-stu-id="1ad5f-124">Header files</span></span>

<span data-ttu-id="1ad5f-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1ad5f-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="1ad5f-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1ad5f-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1ad5f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ad5f-127">See also</span></span>



[<span data-ttu-id="1ad5f-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1ad5f-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1ad5f-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1ad5f-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1ad5f-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1ad5f-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1ad5f-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1ad5f-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

