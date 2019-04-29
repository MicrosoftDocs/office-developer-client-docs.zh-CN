---
title: PidTagPstConfigurationFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: e4234ddf-d9dc-4dc9-8eda-dbbee151b5d7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e881c8eeffa29706591e07113d70a3670606f2be
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408941"
---
# <a name="pidtagpstconfigurationflags-canonical-property"></a><span data-ttu-id="57819-103">PidTagPstConfigurationFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="57819-103">PidTagPstConfigurationFlags Canonical Property</span></span>
  
<span data-ttu-id="57819-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="57819-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="57819-105">指定个人存储表 (.pst 文件) 的配置标志。</span><span class="sxs-lookup"><span data-stu-id="57819-105">Specfies configuration flags for a personal storage table (.pst file).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="57819-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="57819-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="57819-107">PR_PST_CONFIG_FLAGS</span><span class="sxs-lookup"><span data-stu-id="57819-107">PR_PST_CONFIG_FLAGS</span></span>  <br/> |
|<span data-ttu-id="57819-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="57819-108">Identifier:</span></span>  <br/> |<span data-ttu-id="57819-109">0x6770</span><span class="sxs-lookup"><span data-stu-id="57819-109">0x6770</span></span>  <br/> |
|<span data-ttu-id="57819-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="57819-110">Data type:</span></span>  <br/> |<span data-ttu-id="57819-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="57819-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="57819-112">区域：</span><span class="sxs-lookup"><span data-stu-id="57819-112">Area:</span></span>  <br/> |<span data-ttu-id="57819-113">个人存储表 (.pst) 内部</span><span class="sxs-lookup"><span data-stu-id="57819-113">Personal storage table (.pst) internal</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="57819-114">说明</span><span class="sxs-lookup"><span data-stu-id="57819-114">Remarks</span></span>

<span data-ttu-id="57819-115">以下是此属性的有效值:</span><span class="sxs-lookup"><span data-stu-id="57819-115">The following are valid values for this property:</span></span>
  
<span data-ttu-id="57819-116">PST_CONFIG_UNICODE</span><span class="sxs-lookup"><span data-stu-id="57819-116">PST_CONFIG_UNICODE</span></span>
  
> <span data-ttu-id="57819-117">指示 Unicode .pst 文件。</span><span class="sxs-lookup"><span data-stu-id="57819-117">Indicates a Unicode .pst file.</span></span> 
    
   `#define PST_CONFIG_UNICODE 0x80000000`
    
<span data-ttu-id="57819-118">PST_CONFIG_CREATE_NOWARN</span><span class="sxs-lookup"><span data-stu-id="57819-118">PST_CONFIG_CREATE_NOWARN</span></span>
  
> <span data-ttu-id="57819-119">从客户端标志设置为[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法时, 会将**ConfigureMsgService**视为[IMsgServiceAdmin:: CreateMsgService](imsgserviceadmin-createmsgservice.md)调用, 并跳过 "此信息服务尚未配置"通知.</span><span class="sxs-lookup"><span data-stu-id="57819-119">When set from the client flags to the [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) method, treats **ConfigureMsgService** like a [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) call and skips the "This information service has not been configured" warning.</span></span> 
    
   `#define PST_CONFIG_CREATE_NOWARN 0x00000001`
    
<span data-ttu-id="57819-120">PST_CONFIG_PRESERVE_DISPLAY_NAME</span><span class="sxs-lookup"><span data-stu-id="57819-120">PST_CONFIG_PRESERVE_DISPLAY_NAME</span></span>
  
> <span data-ttu-id="57819-121">指示**ConfigureMsgService**不更改**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值, 即使提供了该属性也是如此。</span><span class="sxs-lookup"><span data-stu-id="57819-121">Tells **ConfigureMsgService** to not change the value of the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property, even though it was supplied.</span></span> <span data-ttu-id="57819-122">在这种情况下, 它只提供给新的 .pst 文件。</span><span class="sxs-lookup"><span data-stu-id="57819-122">In that case, it was supplied only for new .pst files.</span></span>
    
   `#define PST_CONFIG_PRESERVE_DISPLAY_NAME 0x00000002`
    
<span data-ttu-id="57819-123">OST_CONFIG_POLICY_DELAY_IGNORE_OST</span><span class="sxs-lookup"><span data-stu-id="57819-123">OST_CONFIG_POLICY_DELAY_IGNORE_OST</span></span>
  
> <span data-ttu-id="57819-124">通知配置代码首先显示一个对话框, 以确认是否找到了脱机文件夹 (.ost) 文件, 并且根据用户的响应, 可以使用找到的脱机文件夹或允许用户浏览其他脱机文件夹。</span><span class="sxs-lookup"><span data-stu-id="57819-124">Tells the configuration code to first display a dialog box to confirm whether an Offline Folder (.ost) file was found and, depending on the user's response, either use the found Offline Folder or enable the user to browse for another Offline Folder.</span></span>
    
   `#define OST_CONFIG_POLICY_DELAY_IGNORE_OST 0x00000008`
    
<span data-ttu-id="57819-125">OST_CONFIG_CREATE_NEW_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="57819-125">OST_CONFIG_CREATE_NEW_DEFAULT</span></span>
  
> <span data-ttu-id="57819-126">使用新的唯一名称复制 .ost 文件, 并丢弃当前名称。</span><span class="sxs-lookup"><span data-stu-id="57819-126">Copies the .ost file with a new unique name and discards the current name.</span></span> <span data-ttu-id="57819-127">现有 .ost 文件仍保留在计算机上, 但不再用于此配置文件。</span><span class="sxs-lookup"><span data-stu-id="57819-127">The existing .ost file remains on the computer but is no longer used in this profile.</span></span> <span data-ttu-id="57819-128">如果 Microsoft Outlook 不再允许使用特定的 .ost 文件, 并且注册表策略不允许用户重命名该文件, 则通常会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="57819-128">This typically occurs when Microsoft Outlook no longer permits a particular .ost file, and registry policies do not allow the user to rename the file.</span></span> 
    
   `#define OST_CONFIG_CREATE_NEW_DEFAULT_OST 0x00000010`
    
## <a name="related-resources"></a><span data-ttu-id="57819-129">相关资源</span><span class="sxs-lookup"><span data-stu-id="57819-129">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="57819-130">协议规范</span><span class="sxs-lookup"><span data-stu-id="57819-130">Protocol specifications</span></span>

<span data-ttu-id="57819-131">[[毫秒-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="57819-131">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="57819-132">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="57819-132">Provides references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="57819-133">头文件</span><span class="sxs-lookup"><span data-stu-id="57819-133">Header files</span></span>

<span data-ttu-id="57819-134">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="57819-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="57819-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="57819-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="57819-136">Mapitags</span><span class="sxs-lookup"><span data-stu-id="57819-136">Mapitags.h</span></span>
  
> <span data-ttu-id="57819-137">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="57819-137">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="57819-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57819-138">See also</span></span>



[<span data-ttu-id="57819-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="57819-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="57819-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="57819-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="57819-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="57819-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="57819-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="57819-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

