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
ms.openlocfilehash: b5a3978741f7ecb871e3c3de28e52dffdcf3a74f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778090"
---
# <a name="pidtagpstconfigurationflags-canonical-property"></a><span data-ttu-id="45d87-103">PidTagPstConfigurationFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="45d87-103">PidTagPstConfigurationFlags Canonical Property</span></span>
  
<span data-ttu-id="45d87-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="45d87-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="45d87-105">指定配置个人存储表 （.pst 文件） 的标志。</span><span class="sxs-lookup"><span data-stu-id="45d87-105">Specfies configuration flags for a personal storage table (.pst file).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="45d87-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="45d87-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="45d87-107">PR_PST_CONFIG_FLAGS</span><span class="sxs-lookup"><span data-stu-id="45d87-107">PR_PST_CONFIG_FLAGS</span></span>  <br/> |
|<span data-ttu-id="45d87-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="45d87-108">Identifier:</span></span>  <br/> |<span data-ttu-id="45d87-109">0x6770</span><span class="sxs-lookup"><span data-stu-id="45d87-109">0x6770</span></span>  <br/> |
|<span data-ttu-id="45d87-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="45d87-110">Data type:</span></span>  <br/> |<span data-ttu-id="45d87-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="45d87-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="45d87-112">区域：</span><span class="sxs-lookup"><span data-stu-id="45d87-112">Area:</span></span>  <br/> |<span data-ttu-id="45d87-113">个人存储表 (.pst) 内部</span><span class="sxs-lookup"><span data-stu-id="45d87-113">Personal storage table (.pst) internal</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="45d87-114">说明</span><span class="sxs-lookup"><span data-stu-id="45d87-114">Remarks</span></span>

<span data-ttu-id="45d87-115">此属性的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="45d87-115">The following are valid values for this property:</span></span>
  
<span data-ttu-id="45d87-116">PST_CONFIG_UNICODE</span><span class="sxs-lookup"><span data-stu-id="45d87-116">PST_CONFIG_UNICODE</span></span>
  
> <span data-ttu-id="45d87-117">指示 Unicode.pst 文件。</span><span class="sxs-lookup"><span data-stu-id="45d87-117">Indicates a Unicode .pst file.</span></span> 
    
   `#define PST_CONFIG_UNICODE 0x80000000`
    
<span data-ttu-id="45d87-118">PST_CONFIG_CREATE_NOWARN</span><span class="sxs-lookup"><span data-stu-id="45d87-118">PST_CONFIG_CREATE_NOWARN</span></span>
  
> <span data-ttu-id="45d87-119">当从客户端设置[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法的标志、 类似[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)调用处理**ConfigureMsgService**和跳过"此信息服务尚未配置"警告。</span><span class="sxs-lookup"><span data-stu-id="45d87-119">When set from the client flags to the [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) method, treats **ConfigureMsgService** like a [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) call and skips the "This information service has not been configured" warning.</span></span> 
    
   `#define PST_CONFIG_CREATE_NOWARN 0x00000001`
    
<span data-ttu-id="45d87-120">PST_CONFIG_PRESERVE_DISPLAY_NAME</span><span class="sxs-lookup"><span data-stu-id="45d87-120">PST_CONFIG_PRESERVE_DISPLAY_NAME</span></span>
  
> <span data-ttu-id="45d87-121">即使在提供通知**ConfigureMsgService**未更改，则**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="45d87-121">Tells **ConfigureMsgService** to not change the value of the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property, even though it was supplied.</span></span> <span data-ttu-id="45d87-122">在这种情况下，在提供只为新的.pst 文件。</span><span class="sxs-lookup"><span data-stu-id="45d87-122">In that case, it was supplied only for new .pst files.</span></span>
    
   `#define PST_CONFIG_PRESERVE_DISPLAY_NAME 0x00000002`
    
<span data-ttu-id="45d87-123">OST_CONFIG_POLICY_DELAY_IGNORE_OST</span><span class="sxs-lookup"><span data-stu-id="45d87-123">OST_CONFIG_POLICY_DELAY_IGNORE_OST</span></span>
  
> <span data-ttu-id="45d87-124">通知配置代码首先显示一个对话框，确认是否已脱机文件夹 (.ost) 文件找到，根据用户的解答，可以使用找到的脱机文件夹或允许用户浏览另一个脱机文件夹。</span><span class="sxs-lookup"><span data-stu-id="45d87-124">Tells the configuration code to first display a dialog box to confirm whether an Offline Folder (.ost) file was found and, depending on the user's response, either use the found Offline Folder or enable the user to browse for another Offline Folder.</span></span>
    
   `#define OST_CONFIG_POLICY_DELAY_IGNORE_OST 0x00000008`
    
<span data-ttu-id="45d87-125">OST_CONFIG_CREATE_NEW_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="45d87-125">OST_CONFIG_CREATE_NEW_DEFAULT</span></span>
  
> <span data-ttu-id="45d87-126">复制新的唯一名称的.ost 文件，并放弃的当前名称。</span><span class="sxs-lookup"><span data-stu-id="45d87-126">Copies the .ost file with a new unique name and discards the current name.</span></span> <span data-ttu-id="45d87-127">现有的.ost 文件的计算机上，但已不再使用此配置文件中。</span><span class="sxs-lookup"><span data-stu-id="45d87-127">The existing .ost file remains on the computer but is no longer used in this profile.</span></span> <span data-ttu-id="45d87-128">这通常发生在 Microsoft Outlook 不再允许一个特定的.ost 文件，并且注册表策略不允许用户重命名该文件。</span><span class="sxs-lookup"><span data-stu-id="45d87-128">This typically occurs when Microsoft Outlook no longer permits a particular .ost file, and registry policies do not allow the user to rename the file.</span></span> 
    
   `#define OST_CONFIG_CREATE_NEW_DEFAULT_OST 0x00000010`
    
## <a name="related-resources"></a><span data-ttu-id="45d87-129">相关资源</span><span class="sxs-lookup"><span data-stu-id="45d87-129">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="45d87-130">协议规范</span><span class="sxs-lookup"><span data-stu-id="45d87-130">Protocol specifications</span></span>

<span data-ttu-id="45d87-131">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="45d87-131">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="45d87-132">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="45d87-132">Provides references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="45d87-133">头文件</span><span class="sxs-lookup"><span data-stu-id="45d87-133">Header files</span></span>

<span data-ttu-id="45d87-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="45d87-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="45d87-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="45d87-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="45d87-136">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="45d87-136">Mapitags.h</span></span>
  
> <span data-ttu-id="45d87-137">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="45d87-137">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="45d87-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45d87-138">See also</span></span>



[<span data-ttu-id="45d87-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="45d87-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="45d87-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="45d87-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="45d87-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="45d87-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="45d87-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="45d87-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

