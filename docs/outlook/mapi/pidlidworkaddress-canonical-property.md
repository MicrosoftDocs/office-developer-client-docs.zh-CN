---
title: PidLidWorkAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidWorkAddress
api_type:
- COM
ms.assetid: fc3c0ab3-6920-4e82-bc69-6c083159628f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7d09de701b9b7ecf168a914e40d91f514fa636cd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341746"
---
# <a name="pidlidworkaddress-canonical-property"></a><span data-ttu-id="a123e-103">PidLidWorkAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="a123e-103">PidLidWorkAddress Canonical Property</span></span>

  
  
<span data-ttu-id="a123e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a123e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a123e-105">指定联系人的完整工作地址。</span><span class="sxs-lookup"><span data-stu-id="a123e-105">Specifies the contact's complete work address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a123e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a123e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a123e-107">dispidWorkAddress</span><span class="sxs-lookup"><span data-stu-id="a123e-107">dispidWorkAddress</span></span>  <br/> |
|<span data-ttu-id="a123e-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="a123e-108">Property set:</span></span>  <br/> |<span data-ttu-id="a123e-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="a123e-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="a123e-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="a123e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="a123e-111">0x0000801B</span><span class="sxs-lookup"><span data-stu-id="a123e-111">0x0000801B</span></span>  <br/> |
|<span data-ttu-id="a123e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a123e-112">Data type:</span></span>  <br/> |<span data-ttu-id="a123e-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a123e-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="a123e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="a123e-114">Area:</span></span>  <br/> |<span data-ttu-id="a123e-115">联系人</span><span class="sxs-lookup"><span data-stu-id="a123e-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a123e-116">备注</span><span class="sxs-lookup"><span data-stu-id="a123e-116">Remarks</span></span>

<span data-ttu-id="a123e-117">此属性应该是其他物理地址属性的组合，并且基于客户端区域设置。</span><span class="sxs-lookup"><span data-stu-id="a123e-117">This property should be a combination of other physical address properties, and is based on client locale.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a123e-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="a123e-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a123e-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="a123e-119">Protocol specifications</span></span>

<span data-ttu-id="a123e-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a123e-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a123e-121">提供属性集定义和对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="a123e-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a123e-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a123e-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a123e-123">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="a123e-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a123e-124">头文件</span><span class="sxs-lookup"><span data-stu-id="a123e-124">Header files</span></span>

<span data-ttu-id="a123e-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a123e-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="a123e-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a123e-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a123e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a123e-127">See also</span></span>



[<span data-ttu-id="a123e-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a123e-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a123e-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a123e-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a123e-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a123e-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a123e-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a123e-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

