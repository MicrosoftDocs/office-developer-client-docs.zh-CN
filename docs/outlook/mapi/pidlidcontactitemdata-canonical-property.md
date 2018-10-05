---
title: PidLidContactItemData 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidContactItemData
api_type:
- COM
ms.assetid: 411e8f81-c2b9-440a-9e9a-d6add5e4be63
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 031e5483539ce17c8b9b994690985c2349573e27
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400803"
---
# <a name="pidlidcontactitemdata-canonical-property"></a><span data-ttu-id="83892-103">PidLidContactItemData 规范属性</span><span class="sxs-lookup"><span data-stu-id="83892-103">PidLidContactItemData Canonical Property</span></span>

  
  
<span data-ttu-id="83892-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="83892-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="83892-105">用于显示的联系人信息。</span><span class="sxs-lookup"><span data-stu-id="83892-105">Used to display the contact information.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="83892-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="83892-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="83892-107">dispidContactItemData</span><span class="sxs-lookup"><span data-stu-id="83892-107">dispidContactItemData</span></span>  <br/> |
|<span data-ttu-id="83892-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="83892-108">Property set:</span></span>  <br/> |<span data-ttu-id="83892-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="83892-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="83892-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="83892-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="83892-111">0x00008007</span><span class="sxs-lookup"><span data-stu-id="83892-111">0x00008007</span></span>  <br/> |
|<span data-ttu-id="83892-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="83892-112">Data type:</span></span>  <br/> |<span data-ttu-id="83892-113">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="83892-113">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="83892-114">区域：</span><span class="sxs-lookup"><span data-stu-id="83892-114">Area:</span></span>  <br/> |<span data-ttu-id="83892-115">联系人</span><span class="sxs-lookup"><span data-stu-id="83892-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="83892-116">说明</span><span class="sxs-lookup"><span data-stu-id="83892-116">Remarks</span></span>

<span data-ttu-id="83892-117">如果存在此参数，则该属性必须具有六个条目，每个对应于应用程序的用户界面中可见字段。</span><span class="sxs-lookup"><span data-stu-id="83892-117">If present, the property must have six entries, each corresponding to a visible field in the application's user interface.</span></span>
  
|<span data-ttu-id="83892-118">**基于一个索引的多值属性**</span><span class="sxs-lookup"><span data-stu-id="83892-118">**One-based index into the multi-valued property**</span></span>|<span data-ttu-id="83892-119">**值必须是下列选项之一**</span><span class="sxs-lookup"><span data-stu-id="83892-119">**The value must be one of the following**</span></span>|<span data-ttu-id="83892-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="83892-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="83892-121">1</span><span class="sxs-lookup"><span data-stu-id="83892-121">1</span></span>  <br/> |<span data-ttu-id="83892-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="83892-122">0x00000001</span></span>  <br/> |<span data-ttu-id="83892-123">应用程序应显示联系人的住宅地址。</span><span class="sxs-lookup"><span data-stu-id="83892-123">The application should display the contact's home address.</span></span>  <br/> |
|<span data-ttu-id="83892-124">1</span><span class="sxs-lookup"><span data-stu-id="83892-124">1</span></span>  <br/> |<span data-ttu-id="83892-125">0x00000002:uc 或 0x00000000</span><span class="sxs-lookup"><span data-stu-id="83892-125">0x00000002 or 0x00000000</span></span>  <br/> |<span data-ttu-id="83892-126">应用程序应显示联系人的工作。</span><span class="sxs-lookup"><span data-stu-id="83892-126">The application should display the contact's work.</span></span>  <br/> |
|<span data-ttu-id="83892-127">1</span><span class="sxs-lookup"><span data-stu-id="83892-127">1</span></span>  <br/> |<span data-ttu-id="83892-128">0x00000003</span><span class="sxs-lookup"><span data-stu-id="83892-128">0x00000003</span></span>  <br/> |<span data-ttu-id="83892-129">应用程序应显示联系人的其他地址。</span><span class="sxs-lookup"><span data-stu-id="83892-129">The application should display the contact's other address.</span></span>  <br/> |
|<span data-ttu-id="83892-130">2</span><span class="sxs-lookup"><span data-stu-id="83892-130">2</span></span>  <br/> |<span data-ttu-id="83892-131">0x00008080</span><span class="sxs-lookup"><span data-stu-id="83892-131">0x00008080</span></span>  <br/> |<span data-ttu-id="83892-132">应用程序应显示电子邮件 1。</span><span class="sxs-lookup"><span data-stu-id="83892-132">The application should display Email1.</span></span>  <br/> |
|<span data-ttu-id="83892-133">2</span><span class="sxs-lookup"><span data-stu-id="83892-133">2</span></span>  <br/> |<span data-ttu-id="83892-134">0x00008090</span><span class="sxs-lookup"><span data-stu-id="83892-134">0x00008090</span></span>  <br/> |<span data-ttu-id="83892-135">应用程序应显示电子邮件 2。</span><span class="sxs-lookup"><span data-stu-id="83892-135">The application should display Email2.</span></span>  <br/> |
|<span data-ttu-id="83892-136">2</span><span class="sxs-lookup"><span data-stu-id="83892-136">2</span></span>  <br/> |<span data-ttu-id="83892-137">0x000080A0</span><span class="sxs-lookup"><span data-stu-id="83892-137">0x000080A0</span></span>  <br/> |<span data-ttu-id="83892-138">应用程序应显示电子邮件 3。</span><span class="sxs-lookup"><span data-stu-id="83892-138">The application should display Email3.</span></span>  <br/> |
|<span data-ttu-id="83892-139">3,4,5,6</span><span class="sxs-lookup"><span data-stu-id="83892-139">3,4,5,6</span></span>  <br/> |<span data-ttu-id="83892-140">PropertyID 的任一电话属性或任何[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)中指定的传真号码。</span><span class="sxs-lookup"><span data-stu-id="83892-140">PropertyID of any of the telephone properties or any of the fax numbers that are specified in [[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx).</span></span>  <br/> |<span data-ttu-id="83892-141">应用程序应显示的相应属性。</span><span class="sxs-lookup"><span data-stu-id="83892-141">The application should display the corresponding property.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="83892-142">相关资源</span><span class="sxs-lookup"><span data-stu-id="83892-142">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="83892-143">协议规范</span><span class="sxs-lookup"><span data-stu-id="83892-143">Protocol specifications</span></span>

<span data-ttu-id="83892-144">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="83892-144">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="83892-145">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="83892-145">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="83892-146">[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="83892-146">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="83892-147">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="83892-147">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="83892-148">头文件</span><span class="sxs-lookup"><span data-stu-id="83892-148">Header files</span></span>

<span data-ttu-id="83892-149">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="83892-149">Mapidefs.h</span></span>
  
> <span data-ttu-id="83892-150">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="83892-150">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="83892-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83892-151">See also</span></span>



[<span data-ttu-id="83892-152">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="83892-152">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="83892-153">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="83892-153">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="83892-154">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="83892-154">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="83892-155">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="83892-155">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

