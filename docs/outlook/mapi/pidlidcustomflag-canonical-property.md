---
title: PidLidCustomFlag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCustomFlag
api_type:
- COM
ms.assetid: bfb7fd1e-774f-9a2f-fbbe-ba7f68ed8663
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5d97f56946512266bb7a08aa6b4a4ff78dded56a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776737"
---
# <a name="pidlidcustomflag-canonical-property"></a><span data-ttu-id="62ce2-103">PidLidCustomFlag 规范属性</span><span class="sxs-lookup"><span data-stu-id="62ce2-103">PidLidCustomFlag Canonical Property</span></span>

  
  
<span data-ttu-id="62ce2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="62ce2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="62ce2-105">指定一条消息自定义方式，例如，使用自定义属性保存的位掩码。</span><span class="sxs-lookup"><span data-stu-id="62ce2-105">A bitmask that specifies how a message is customized, for example, saved with custom properties.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="62ce2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="62ce2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="62ce2-107">dispidCustomFlag</span><span class="sxs-lookup"><span data-stu-id="62ce2-107">dispidCustomFlag</span></span>  <br/> |
|<span data-ttu-id="62ce2-108">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="62ce2-108">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="62ce2-109">0x00008251</span><span class="sxs-lookup"><span data-stu-id="62ce2-109">0x00008251</span></span>  <br/> |
|<span data-ttu-id="62ce2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="62ce2-110">Data type:</span></span>  <br/> |<span data-ttu-id="62ce2-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="62ce2-111">PT_LONG</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="62ce2-112">说明</span><span class="sxs-lookup"><span data-stu-id="62ce2-112">Remarks</span></span>

<span data-ttu-id="62ce2-113">若要检索此属性的值，首先使用**[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)** 获取的属性标记，然后指定**[IMAPIProp::GetProps](imapiprop-getprops.md)** 获取值中的此属性标记。</span><span class="sxs-lookup"><span data-stu-id="62ce2-113">To retrieve the value of this property, first use **[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)** to obtain the property tag, and then specify this property tag in **[IMAPIProp::GetProps](imapiprop-getprops.md)** to get the value.</span></span> 
  
<span data-ttu-id="62ce2-114">可能的标志如下所示：</span><span class="sxs-lookup"><span data-stu-id="62ce2-114">Possible Flags are as follows:</span></span>
  
****

|<span data-ttu-id="62ce2-115">**常量**</span><span class="sxs-lookup"><span data-stu-id="62ce2-115">**Constant**</span></span>|<span data-ttu-id="62ce2-116">**值**</span><span class="sxs-lookup"><span data-stu-id="62ce2-116">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="62ce2-117">INSP_ONEOFFFLAGS</span><span class="sxs-lookup"><span data-stu-id="62ce2-117">INSP_ONEOFFFLAGS</span></span>  <br/> |<span data-ttu-id="62ce2-118">0x0D000000</span><span class="sxs-lookup"><span data-stu-id="62ce2-118">0x0D000000</span></span>  <br/> |
|<span data-ttu-id="62ce2-119">INSP_PROPDEFINITION</span><span class="sxs-lookup"><span data-stu-id="62ce2-119">INSP_PROPDEFINITION</span></span>  <br/> |<span data-ttu-id="62ce2-120">0x02000000</span><span class="sxs-lookup"><span data-stu-id="62ce2-120">0x02000000</span></span>  <br/> |
   
<span data-ttu-id="62ce2-121">当调用**IMAPIProp::GetIDsFromNames**，指定以下值所指的输入的参数*lppPropNames* **[MAPINAMEID](mapinameid.md)** 结构。</span><span class="sxs-lookup"><span data-stu-id="62ce2-121">When calling **IMAPIProp::GetIDsFromNames**, specify the following values for the **[MAPINAMEID](mapinameid.md)** structure pointed to by the input parameter  *lppPropNames*  .</span></span> 
  
****

|<span data-ttu-id="62ce2-122">**成员**</span><span class="sxs-lookup"><span data-stu-id="62ce2-122">**Member**</span></span>|<span data-ttu-id="62ce2-123">**值**</span><span class="sxs-lookup"><span data-stu-id="62ce2-123">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="62ce2-124">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="62ce2-124">lpGuid:</span></span>  <br/> |<span data-ttu-id="62ce2-125">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="62ce2-125">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="62ce2-126">ulKind:</span><span class="sxs-lookup"><span data-stu-id="62ce2-126">ulKind:</span></span>  <br/> |<span data-ttu-id="62ce2-127">MNID_ID</span><span class="sxs-lookup"><span data-stu-id="62ce2-127">MNID_ID</span></span>  <br/> |
|<span data-ttu-id="62ce2-128">Kind.lID:</span><span class="sxs-lookup"><span data-stu-id="62ce2-128">Kind.lID:</span></span>  <br/> |<span data-ttu-id="62ce2-129">dispidCustomFlag</span><span class="sxs-lookup"><span data-stu-id="62ce2-129">dispidCustomFlag</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="62ce2-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="62ce2-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="62ce2-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="62ce2-131">Protocol specifications</span></span>

<span data-ttu-id="62ce2-132">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="62ce2-132">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="62ce2-133">提供属性集定义。</span><span class="sxs-lookup"><span data-stu-id="62ce2-133">Provides property set definitions.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="62ce2-134">头文件</span><span class="sxs-lookup"><span data-stu-id="62ce2-134">Header files</span></span>

<span data-ttu-id="62ce2-135">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="62ce2-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="62ce2-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="62ce2-136">Provides data type definitions.</span></span>
    
<span data-ttu-id="62ce2-137">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="62ce2-137">Mapitags.h</span></span>
  
> <span data-ttu-id="62ce2-138">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="62ce2-138">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="62ce2-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62ce2-139">See also</span></span>



[<span data-ttu-id="62ce2-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="62ce2-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="62ce2-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="62ce2-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="62ce2-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="62ce2-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="62ce2-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="62ce2-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

