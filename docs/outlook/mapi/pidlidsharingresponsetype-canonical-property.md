---
title: PidLidSharingResponseType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingResponseType
api_type:
- COM
ms.assetid: c27b1239-3612-4bb3-9f22-4b89ee9900cd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 34e8a3c73715a75b8007646e5ba3b0dc3e1ae919
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331190"
---
# <a name="pidlidsharingresponsetype-canonical-property"></a><span data-ttu-id="25b26-103">PidLidSharingResponseType 规范属性</span><span class="sxs-lookup"><span data-stu-id="25b26-103">PidLidSharingResponseType Canonical Property</span></span>

  
  
<span data-ttu-id="25b26-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="25b26-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="25b26-105">指定共享请求的收件人响应的响应类型。</span><span class="sxs-lookup"><span data-stu-id="25b26-105">Specifies the type of response with which the recipient of the sharing request responded.</span></span> <span data-ttu-id="25b26-106">这是共享邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="25b26-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="25b26-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="25b26-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="25b26-108">dispidSharingResponseType</span><span class="sxs-lookup"><span data-stu-id="25b26-108">dispidSharingResponseType</span></span>  <br/> |
|<span data-ttu-id="25b26-109">属性集：</span><span class="sxs-lookup"><span data-stu-id="25b26-109">Property set:</span></span>  <br/> |<span data-ttu-id="25b26-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="25b26-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="25b26-111">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="25b26-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="25b26-112">0x00008A27</span><span class="sxs-lookup"><span data-stu-id="25b26-112">0x00008A27</span></span>  <br/> |
|<span data-ttu-id="25b26-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="25b26-113">Data type:</span></span>  <br/> |<span data-ttu-id="25b26-114">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="25b26-114">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="25b26-115">区域：</span><span class="sxs-lookup"><span data-stu-id="25b26-115">Area:</span></span>  <br/> |<span data-ttu-id="25b26-116">共享</span><span class="sxs-lookup"><span data-stu-id="25b26-116">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="25b26-117">备注</span><span class="sxs-lookup"><span data-stu-id="25b26-117">Remarks</span></span>

<span data-ttu-id="25b26-118">此属性的值必须设置为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="25b26-118">The value of this property must be set to one of the following values:</span></span>
  
|<span data-ttu-id="25b26-119">**值**</span><span class="sxs-lookup"><span data-stu-id="25b26-119">**Value**</span></span>|<span data-ttu-id="25b26-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="25b26-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="25b26-121">0x00000000</span><span class="sxs-lookup"><span data-stu-id="25b26-121">0x00000000</span></span>  <br/> |<span data-ttu-id="25b26-122">无响应</span><span class="sxs-lookup"><span data-stu-id="25b26-122">No response</span></span>  <br/> |
|<span data-ttu-id="25b26-123">0x00000001</span><span class="sxs-lookup"><span data-stu-id="25b26-123">0x00000001</span></span>  <br/> |<span data-ttu-id="25b26-124">Accepted</span><span class="sxs-lookup"><span data-stu-id="25b26-124">Accepted</span></span>  <br/> |
|<span data-ttu-id="25b26-125">0x00000002</span><span class="sxs-lookup"><span data-stu-id="25b26-125">0x00000002</span></span>  <br/> |<span data-ttu-id="25b26-126">已拒绝</span><span class="sxs-lookup"><span data-stu-id="25b26-126">Denied</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="25b26-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="25b26-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="25b26-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="25b26-128">Protocol specifications</span></span>

<span data-ttu-id="25b26-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="25b26-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="25b26-130">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="25b26-130">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="25b26-131">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="25b26-131">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="25b26-132">在客户端之间共享邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="25b26-132">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="25b26-133">头文件</span><span class="sxs-lookup"><span data-stu-id="25b26-133">Header files</span></span>

<span data-ttu-id="25b26-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="25b26-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="25b26-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="25b26-135">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="25b26-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25b26-136">See also</span></span>



[<span data-ttu-id="25b26-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="25b26-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="25b26-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="25b26-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="25b26-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="25b26-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="25b26-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="25b26-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

