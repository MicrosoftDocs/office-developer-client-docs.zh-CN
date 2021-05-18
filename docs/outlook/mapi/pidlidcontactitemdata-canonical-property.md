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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319507"
---
# <a name="pidlidcontactitemdata-canonical-property"></a><span data-ttu-id="f79f8-103">PidLidContactItemData 规范属性</span><span class="sxs-lookup"><span data-stu-id="f79f8-103">PidLidContactItemData Canonical Property</span></span>

  
  
<span data-ttu-id="f79f8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f79f8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f79f8-105">用于显示联系人信息。</span><span class="sxs-lookup"><span data-stu-id="f79f8-105">Used to display the contact information.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f79f8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f79f8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f79f8-107">dispidContactItemData</span><span class="sxs-lookup"><span data-stu-id="f79f8-107">dispidContactItemData</span></span>  <br/> |
|<span data-ttu-id="f79f8-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="f79f8-108">Property set:</span></span>  <br/> |<span data-ttu-id="f79f8-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="f79f8-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="f79f8-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="f79f8-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="f79f8-111">0x00008007</span><span class="sxs-lookup"><span data-stu-id="f79f8-111">0x00008007</span></span>  <br/> |
|<span data-ttu-id="f79f8-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f79f8-112">Data type:</span></span>  <br/> |<span data-ttu-id="f79f8-113">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="f79f8-113">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="f79f8-114">区域：</span><span class="sxs-lookup"><span data-stu-id="f79f8-114">Area:</span></span>  <br/> |<span data-ttu-id="f79f8-115">联系人</span><span class="sxs-lookup"><span data-stu-id="f79f8-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f79f8-116">备注</span><span class="sxs-lookup"><span data-stu-id="f79f8-116">Remarks</span></span>

<span data-ttu-id="f79f8-117">如果存在，则属性必须具有六个条目，每个条目对应于应用程序用户界面中的可见字段。</span><span class="sxs-lookup"><span data-stu-id="f79f8-117">If present, the property must have six entries, each corresponding to a visible field in the application's user interface.</span></span>
  
|<span data-ttu-id="f79f8-118">**多值属性中从 1 到 1 的索引**</span><span class="sxs-lookup"><span data-stu-id="f79f8-118">**One-based index into the multi-valued property**</span></span>|<span data-ttu-id="f79f8-119">**值必须是下列值之一**</span><span class="sxs-lookup"><span data-stu-id="f79f8-119">**The value must be one of the following**</span></span>|<span data-ttu-id="f79f8-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="f79f8-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f79f8-121">1</span><span class="sxs-lookup"><span data-stu-id="f79f8-121">1</span></span>  <br/> |<span data-ttu-id="f79f8-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="f79f8-122">0x00000001</span></span>  <br/> |<span data-ttu-id="f79f8-123">应用程序应显示联系人的住宅地址。</span><span class="sxs-lookup"><span data-stu-id="f79f8-123">The application should display the contact's home address.</span></span>  <br/> |
|<span data-ttu-id="f79f8-124">1</span><span class="sxs-lookup"><span data-stu-id="f79f8-124">1</span></span>  <br/> |<span data-ttu-id="f79f8-125">0x00000002 或 0x00000000</span><span class="sxs-lookup"><span data-stu-id="f79f8-125">0x00000002 or 0x00000000</span></span>  <br/> |<span data-ttu-id="f79f8-126">应用程序应显示联系人的工作。</span><span class="sxs-lookup"><span data-stu-id="f79f8-126">The application should display the contact's work.</span></span>  <br/> |
|<span data-ttu-id="f79f8-127">1</span><span class="sxs-lookup"><span data-stu-id="f79f8-127">1</span></span>  <br/> |<span data-ttu-id="f79f8-128">0x00000003</span><span class="sxs-lookup"><span data-stu-id="f79f8-128">0x00000003</span></span>  <br/> |<span data-ttu-id="f79f8-129">应用程序应显示联系人的其他地址。</span><span class="sxs-lookup"><span data-stu-id="f79f8-129">The application should display the contact's other address.</span></span>  <br/> |
|<span data-ttu-id="f79f8-130">2</span><span class="sxs-lookup"><span data-stu-id="f79f8-130">2</span></span>  <br/> |<span data-ttu-id="f79f8-131">0x00008080</span><span class="sxs-lookup"><span data-stu-id="f79f8-131">0x00008080</span></span>  <br/> |<span data-ttu-id="f79f8-132">应用程序应显示 Email1。</span><span class="sxs-lookup"><span data-stu-id="f79f8-132">The application should display Email1.</span></span>  <br/> |
|<span data-ttu-id="f79f8-133">2</span><span class="sxs-lookup"><span data-stu-id="f79f8-133">2</span></span>  <br/> |<span data-ttu-id="f79f8-134">0x00008090</span><span class="sxs-lookup"><span data-stu-id="f79f8-134">0x00008090</span></span>  <br/> |<span data-ttu-id="f79f8-135">应用程序应显示 Email2。</span><span class="sxs-lookup"><span data-stu-id="f79f8-135">The application should display Email2.</span></span>  <br/> |
|<span data-ttu-id="f79f8-136">2</span><span class="sxs-lookup"><span data-stu-id="f79f8-136">2</span></span>  <br/> |<span data-ttu-id="f79f8-137">0x000080A0</span><span class="sxs-lookup"><span data-stu-id="f79f8-137">0x000080A0</span></span>  <br/> |<span data-ttu-id="f79f8-138">应用程序应显示 Email3。</span><span class="sxs-lookup"><span data-stu-id="f79f8-138">The application should display Email3.</span></span>  <br/> |
|<span data-ttu-id="f79f8-139">3,4,5,6</span><span class="sxs-lookup"><span data-stu-id="f79f8-139">3,4,5,6</span></span>  <br/> |<span data-ttu-id="f79f8-140">PropertyID [[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)中指定的任何电话属性或任何传真号码。</span><span class="sxs-lookup"><span data-stu-id="f79f8-140">PropertyID of any of the telephone properties or any of the fax numbers that are specified in [[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx).</span></span>  <br/> |<span data-ttu-id="f79f8-141">应用程序应显示相应的属性。</span><span class="sxs-lookup"><span data-stu-id="f79f8-141">The application should display the corresponding property.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="f79f8-142">相关资源</span><span class="sxs-lookup"><span data-stu-id="f79f8-142">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f79f8-143">协议规范</span><span class="sxs-lookup"><span data-stu-id="f79f8-143">Protocol specifications</span></span>

<span data-ttu-id="f79f8-144">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f79f8-144">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f79f8-145">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="f79f8-145">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f79f8-146">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f79f8-146">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f79f8-147">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="f79f8-147">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f79f8-148">头文件</span><span class="sxs-lookup"><span data-stu-id="f79f8-148">Header files</span></span>

<span data-ttu-id="f79f8-149">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f79f8-149">Mapidefs.h</span></span>
  
> <span data-ttu-id="f79f8-150">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f79f8-150">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f79f8-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f79f8-151">See also</span></span>



[<span data-ttu-id="f79f8-152">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f79f8-152">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f79f8-153">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f79f8-153">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f79f8-154">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f79f8-154">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f79f8-155">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f79f8-155">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

