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
# <a name="pidtagcontainerclass-canonical-property"></a><span data-ttu-id="690f1-103">PidTagContainerClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="690f1-103">PidTagContainerClass Canonical Property</span></span>

  
  
<span data-ttu-id="690f1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="690f1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="690f1-105">包含描述文件夹类型的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="690f1-105">Contains a text string describing the type of a folder.</span></span> <span data-ttu-id="690f1-106">虽然通常忽略此属性, 但在 Exchange server 2003 邮箱管理器之前的 Microsoft ® Exchange server 版本要求此属性存在。</span><span class="sxs-lookup"><span data-stu-id="690f1-106">Although this property is generally ignored, versions of Microsoft® Exchange Server prior to Exchange Server 2003 Mailbox Manager expect this property to be present.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="690f1-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="690f1-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="690f1-108">PR_CONTAINER_CLASS、PR_CONTAINER_CLASS_A、PR_CONTAINER_CLASS_W</span><span class="sxs-lookup"><span data-stu-id="690f1-108">PR_CONTAINER_CLASS, PR_CONTAINER_CLASS_A, PR_CONTAINER_CLASS_W</span></span>  <br/> |
|<span data-ttu-id="690f1-109">标识符:</span><span class="sxs-lookup"><span data-stu-id="690f1-109">Identifier:</span></span>  <br/> |<span data-ttu-id="690f1-110">0x3613</span><span class="sxs-lookup"><span data-stu-id="690f1-110">0x3613</span></span>  <br/> |
|<span data-ttu-id="690f1-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="690f1-111">Data type:</span></span>  <br/> |<span data-ttu-id="690f1-112">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="690f1-112">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="690f1-113">区域：</span><span class="sxs-lookup"><span data-stu-id="690f1-113">Area:</span></span>  <br/> |<span data-ttu-id="690f1-114">Container</span><span class="sxs-lookup"><span data-stu-id="690f1-114">Container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="690f1-115">注解</span><span class="sxs-lookup"><span data-stu-id="690f1-115">Remarks</span></span>

<span data-ttu-id="690f1-116">Exchange Server 通常不使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="690f1-116">These properties are not normally used by Exchange Server.</span></span> <span data-ttu-id="690f1-117">但是, Microsoft Office Outlook ®会将其附加到邮箱文件夹中。</span><span class="sxs-lookup"><span data-stu-id="690f1-117">However, Microsoft Office Outlook® attaches them to mailbox folders.</span></span> <span data-ttu-id="690f1-118">此外, exchange server 2003 邮箱管理器之前的 exchange server 版本可能会错误地处理不具有这些属性的文件夹。</span><span class="sxs-lookup"><span data-stu-id="690f1-118">In addition, versions of Exchange Server prior to Exchange Server 2003 Mailbox Manager might incorrectly handle folders that do not have these properties.</span></span>
  
<span data-ttu-id="690f1-119">可以将下表中的字符串值分配给这些属性。</span><span class="sxs-lookup"><span data-stu-id="690f1-119">These properties can be assigned the string values in the following table.</span></span>
  
|<span data-ttu-id="690f1-120">**值**</span><span class="sxs-lookup"><span data-stu-id="690f1-120">**Value**</span></span>|<span data-ttu-id="690f1-121">**文件夹的内容**</span><span class="sxs-lookup"><span data-stu-id="690f1-121">**Contents of Folder**</span></span>|
|:-----|:-----|
|<span data-ttu-id="690f1-122">限.日程</span><span class="sxs-lookup"><span data-stu-id="690f1-122">IPF.Appointment</span></span>  <br/> |<span data-ttu-id="690f1-123">约会</span><span class="sxs-lookup"><span data-stu-id="690f1-123">Appointments</span></span>  <br/> |
|<span data-ttu-id="690f1-124">限.信息</span><span class="sxs-lookup"><span data-stu-id="690f1-124">IPF.Contact</span></span>  <br/> |<span data-ttu-id="690f1-125">联系人</span><span class="sxs-lookup"><span data-stu-id="690f1-125">Contacts</span></span>  <br/> |
|<span data-ttu-id="690f1-126">限.日志</span><span class="sxs-lookup"><span data-stu-id="690f1-126">IPF.Journal</span></span>  <br/> |<span data-ttu-id="690f1-127">Outlook 日记条目</span><span class="sxs-lookup"><span data-stu-id="690f1-127">Outlook Journal entries</span></span>  <br/> |
|<span data-ttu-id="690f1-128">限.便笺</span><span class="sxs-lookup"><span data-stu-id="690f1-128">IPF.Note</span></span>  <br/> |<span data-ttu-id="690f1-129">邮件和笔记</span><span class="sxs-lookup"><span data-stu-id="690f1-129">Mail Messages and notes</span></span>  <br/> |
|<span data-ttu-id="690f1-130">限.ipm.stickynote</span><span class="sxs-lookup"><span data-stu-id="690f1-130">IPF.StickyNote</span></span>  <br/> |<span data-ttu-id="690f1-131">Outlook 粘滞便笺</span><span class="sxs-lookup"><span data-stu-id="690f1-131">Outlook Sticky Notes</span></span>  <br/> |
|<span data-ttu-id="690f1-132">限.任务</span><span class="sxs-lookup"><span data-stu-id="690f1-132">IPF.Task</span></span>  <br/> |<span data-ttu-id="690f1-133">Outlook 任务</span><span class="sxs-lookup"><span data-stu-id="690f1-133">Outlook Tasks</span></span>  <br/> |
   
<span data-ttu-id="690f1-134">对于包含邮件的文件夹, 应将这些属性设置为 IPF。便笺.</span><span class="sxs-lookup"><span data-stu-id="690f1-134">For folders that contain mail messages, these properties should be set to IPF.Note.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="690f1-135">相关资源</span><span class="sxs-lookup"><span data-stu-id="690f1-135">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="690f1-136">协议规范</span><span class="sxs-lookup"><span data-stu-id="690f1-136">Protocol specifications</span></span>

<span data-ttu-id="690f1-137">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="690f1-137">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="690f1-138">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="690f1-138">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="690f1-139">[[毫秒-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="690f1-139">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="690f1-140">指定用于创建和定位邮箱中的特殊文件夹的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="690f1-140">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="690f1-141">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="690f1-141">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="690f1-142">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="690f1-142">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="690f1-143">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="690f1-143">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="690f1-144">指定允许用于联系人和个人通讯组列表对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="690f1-144">Specifies the properties and operations that are permissible for contact and personal distribution list objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="690f1-145">头文件</span><span class="sxs-lookup"><span data-stu-id="690f1-145">Header files</span></span>

<span data-ttu-id="690f1-146">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="690f1-146">Mapidefs.h</span></span>
  
> <span data-ttu-id="690f1-147">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="690f1-147">Provides data type definitions.</span></span>
    
<span data-ttu-id="690f1-148">Mapitags</span><span class="sxs-lookup"><span data-stu-id="690f1-148">Mapitags.h</span></span>
  
> <span data-ttu-id="690f1-149">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="690f1-149">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="690f1-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="690f1-150">See also</span></span>



[<span data-ttu-id="690f1-151">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="690f1-151">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="690f1-152">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="690f1-152">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="690f1-153">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="690f1-153">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="690f1-154">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="690f1-154">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

