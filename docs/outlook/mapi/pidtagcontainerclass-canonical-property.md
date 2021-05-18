---
title: PidTagContainerClass 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContainerClass
api_type:
- HeaderDef
ms.assetid: db249e9e-f1f0-4b95-8cd9-daa7c53ddb32
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c5b80831607f473208ce987a720c7e80e44b6d80
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283147"
---
# <a name="pidtagcontainerclass-canonical-property"></a><span data-ttu-id="8668d-103">PidTagContainerClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="8668d-103">PidTagContainerClass Canonical Property</span></span>

  
  
<span data-ttu-id="8668d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8668d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8668d-105">包含描述文件夹类型的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="8668d-105">Contains a text string describing the type of a folder.</span></span> <span data-ttu-id="8668d-106">尽管通常忽略此属性，® Exchange Server 2003 邮箱管理器Exchange Server Microsoft 2003 之前的版本预期此属性存在。</span><span class="sxs-lookup"><span data-stu-id="8668d-106">Although this property is generally ignored, versions of Microsoft® Exchange Server prior to Exchange Server 2003 Mailbox Manager expect this property to be present.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8668d-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8668d-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="8668d-108">PR_CONTAINER_CLASS、PR_CONTAINER_CLASS_A、PR_CONTAINER_CLASS_W</span><span class="sxs-lookup"><span data-stu-id="8668d-108">PR_CONTAINER_CLASS, PR_CONTAINER_CLASS_A, PR_CONTAINER_CLASS_W</span></span>  <br/> |
|<span data-ttu-id="8668d-109">标识符:</span><span class="sxs-lookup"><span data-stu-id="8668d-109">Identifier:</span></span>  <br/> |<span data-ttu-id="8668d-110">0x3613</span><span class="sxs-lookup"><span data-stu-id="8668d-110">0x3613</span></span>  <br/> |
|<span data-ttu-id="8668d-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8668d-111">Data type:</span></span>  <br/> |<span data-ttu-id="8668d-112">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="8668d-112">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="8668d-113">区域：</span><span class="sxs-lookup"><span data-stu-id="8668d-113">Area:</span></span>  <br/> |<span data-ttu-id="8668d-114">容器</span><span class="sxs-lookup"><span data-stu-id="8668d-114">Container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8668d-115">备注</span><span class="sxs-lookup"><span data-stu-id="8668d-115">Remarks</span></span>

<span data-ttu-id="8668d-116">这些属性通常不由 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="8668d-116">These properties are not normally used by Exchange Server.</span></span> <span data-ttu-id="8668d-117">但是，Microsoft Office Outlook®将它们附加到邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="8668d-117">However, Microsoft Office Outlook® attaches them to mailbox folders.</span></span> <span data-ttu-id="8668d-118">此外，Exchange Server 2003 邮箱Exchange Server之前的版本可能无法正确处理没有这些属性的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8668d-118">In addition, versions of Exchange Server prior to Exchange Server 2003 Mailbox Manager might incorrectly handle folders that do not have these properties.</span></span>
  
<span data-ttu-id="8668d-119">可以在下表中为这些属性分配字符串值。</span><span class="sxs-lookup"><span data-stu-id="8668d-119">These properties can be assigned the string values in the following table.</span></span>
  
|<span data-ttu-id="8668d-120">**值**</span><span class="sxs-lookup"><span data-stu-id="8668d-120">**Value**</span></span>|<span data-ttu-id="8668d-121">**文件夹内容**</span><span class="sxs-lookup"><span data-stu-id="8668d-121">**Contents of Folder**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8668d-122">IPF。约会</span><span class="sxs-lookup"><span data-stu-id="8668d-122">IPF.Appointment</span></span>  <br/> |<span data-ttu-id="8668d-123">约会</span><span class="sxs-lookup"><span data-stu-id="8668d-123">Appointments</span></span>  <br/> |
|<span data-ttu-id="8668d-124">IPF。联系人</span><span class="sxs-lookup"><span data-stu-id="8668d-124">IPF.Contact</span></span>  <br/> |<span data-ttu-id="8668d-125">联系人</span><span class="sxs-lookup"><span data-stu-id="8668d-125">Contacts</span></span>  <br/> |
|<span data-ttu-id="8668d-126">IPF。日记</span><span class="sxs-lookup"><span data-stu-id="8668d-126">IPF.Journal</span></span>  <br/> |<span data-ttu-id="8668d-127">Outlook日记条目</span><span class="sxs-lookup"><span data-stu-id="8668d-127">Outlook Journal entries</span></span>  <br/> |
|<span data-ttu-id="8668d-128">IPF。注意</span><span class="sxs-lookup"><span data-stu-id="8668d-128">IPF.Note</span></span>  <br/> |<span data-ttu-id="8668d-129">邮件消息和注释</span><span class="sxs-lookup"><span data-stu-id="8668d-129">Mail Messages and notes</span></span>  <br/> |
|<span data-ttu-id="8668d-130">IPF。StickyNote</span><span class="sxs-lookup"><span data-stu-id="8668d-130">IPF.StickyNote</span></span>  <br/> |<span data-ttu-id="8668d-131">Outlook 便笺</span><span class="sxs-lookup"><span data-stu-id="8668d-131">Outlook Sticky Notes</span></span>  <br/> |
|<span data-ttu-id="8668d-132">IPF。任务</span><span class="sxs-lookup"><span data-stu-id="8668d-132">IPF.Task</span></span>  <br/> |<span data-ttu-id="8668d-133">Outlook 任务</span><span class="sxs-lookup"><span data-stu-id="8668d-133">Outlook Tasks</span></span>  <br/> |
   
<span data-ttu-id="8668d-134">对于包含邮件的文件夹，这些属性应设置为 IPF。注意。</span><span class="sxs-lookup"><span data-stu-id="8668d-134">For folders that contain mail messages, these properties should be set to IPF.Note.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="8668d-135">相关资源</span><span class="sxs-lookup"><span data-stu-id="8668d-135">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8668d-136">协议规范</span><span class="sxs-lookup"><span data-stu-id="8668d-136">Protocol specifications</span></span>

<span data-ttu-id="8668d-137">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8668d-137">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8668d-138">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="8668d-138">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8668d-139">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8668d-139">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8668d-140">指定用于创建和定位邮箱中特殊文件夹的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8668d-140">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="8668d-141">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8668d-141">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8668d-142">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8668d-142">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="8668d-143">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8668d-143">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8668d-144">指定联系人和个人通讯组列表对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8668d-144">Specifies the properties and operations that are permissible for contact and personal distribution list objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8668d-145">头文件</span><span class="sxs-lookup"><span data-stu-id="8668d-145">Header files</span></span>

<span data-ttu-id="8668d-146">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8668d-146">Mapidefs.h</span></span>
  
> <span data-ttu-id="8668d-147">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8668d-147">Provides data type definitions.</span></span>
    
<span data-ttu-id="8668d-148">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8668d-148">Mapitags.h</span></span>
  
> <span data-ttu-id="8668d-149">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8668d-149">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8668d-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8668d-150">See also</span></span>



[<span data-ttu-id="8668d-151">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8668d-151">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8668d-152">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8668d-152">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8668d-153">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8668d-153">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8668d-154">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8668d-154">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

