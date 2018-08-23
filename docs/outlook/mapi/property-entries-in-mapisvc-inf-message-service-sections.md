---
title: MapiSvc.inf 邮件服务部分中的属性条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 714f99e2-80fc-4785-b707-611d8a6c229f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 038c13d24f3d797f7a4f8f9b7692240ce8004b74
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580332"
---
# <a name="property-entries-in-mapisvcinf-message-service-sections"></a><span data-ttu-id="6113d-103">MapiSvc.inf 邮件服务部分中的属性条目</span><span class="sxs-lookup"><span data-stu-id="6113d-103">Property Entries in MapiSvc.inf Message Service Sections</span></span>

  
  
<span data-ttu-id="6113d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6113d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6113d-105">设置属性的项使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="6113d-105">Entries that set properties use this format:</span></span>
  
 <span data-ttu-id="6113d-106">**属性标记****=** 属性值</span><span class="sxs-lookup"><span data-stu-id="6113d-106">**property tag** **=** property value</span></span> 
  
<span data-ttu-id="6113d-107">如果数据不表示的 MAPI 属性，可以标准的 MAPI 属性标记，如果配置数据表示 MAPI，由预定义的属性之一或非标准标记属性标记。</span><span class="sxs-lookup"><span data-stu-id="6113d-107">The property tag can be a standard MAPI property tag if the configuration data represents one of the properties predefined by MAPI, or a nonstandard tag if the data does not represent a MAPI property.</span></span> <span data-ttu-id="6113d-108">通过将与属性类型组合属性标识符的值进行的非标准标记。</span><span class="sxs-lookup"><span data-stu-id="6113d-108">The nonstandard tag is made by combining the value for a property identifier with a property type.</span></span> <span data-ttu-id="6113d-109">结果是 8 位十六进制数。</span><span class="sxs-lookup"><span data-stu-id="6113d-109">The result is an 8 digit hexadecimal number.</span></span> <span data-ttu-id="6113d-110">该属性值可以是任何有意义属性标记。</span><span class="sxs-lookup"><span data-stu-id="6113d-110">The property value can be whatever makes sense for the property tag.</span></span> 
  
<span data-ttu-id="6113d-111">消息服务各节可以包含各种具体取决于要配置的消息服务的条目。</span><span class="sxs-lookup"><span data-stu-id="6113d-111">Message service sections can contain a variety of entries depending on the message service being configured.</span></span> <span data-ttu-id="6113d-112">下面的 MAPI 属性通常包括在邮件服务节中列出的格式：</span><span class="sxs-lookup"><span data-stu-id="6113d-112">The following MAPI properties are typically included in a message services section in the listed format:</span></span>
  
 <span data-ttu-id="6113d-113">**PR_DISPLAY_NAME** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="6113d-113">**PR_DISPLAY_NAME** =  _string_</span></span>
  
 <span data-ttu-id="6113d-114">**PR_SERVICE_DLL_NAME** =  _DLL 文件的名称_</span><span class="sxs-lookup"><span data-stu-id="6113d-114">**PR_SERVICE_DLL_NAME** =  _name of DLL file_</span></span>
  
 <span data-ttu-id="6113d-115">**PR_SERVICE_ENTRY_NAME** =  _的入口点函数名称_</span><span class="sxs-lookup"><span data-stu-id="6113d-115">**PR_SERVICE_ENTRY_NAME** =  _name of entry point function_</span></span>
  
 <span data-ttu-id="6113d-116">**PR_SERVICE_SUPPORT_FILES** =  _的文件列表_</span><span class="sxs-lookup"><span data-stu-id="6113d-116">**PR_SERVICE_SUPPORT_FILES** =  _list of files_</span></span>
  
 <span data-ttu-id="6113d-117">**PR_SERVICE_DELETE_FILES** =  _的文件列表_</span><span class="sxs-lookup"><span data-stu-id="6113d-117">**PR_SERVICE_DELETE_FILES** =  _list of files_</span></span>
  
 <span data-ttu-id="6113d-118">**PR_RESOURCE_FLAGS** =  _位掩码_</span><span class="sxs-lookup"><span data-stu-id="6113d-118">**PR_RESOURCE_FLAGS** =  _bitmask_</span></span>
  
<span data-ttu-id="6113d-119">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 字符串是在用户界面中，用户与邮件服务关联的名称显示的消息服务的名称。</span><span class="sxs-lookup"><span data-stu-id="6113d-119">The **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) string is the name of the message service that is shown in the user interface, the name that the user associates with the message service.</span></span> <span data-ttu-id="6113d-120">显示名称为 mapisvc.inf 中的可选条目。</span><span class="sxs-lookup"><span data-stu-id="6113d-120">The display name is an optional entry in mapisvc.inf.</span></span> <span data-ttu-id="6113d-121">有时的显示名称将是两个部分组成;消息服务分配的部件和由用户分配一个部分。</span><span class="sxs-lookup"><span data-stu-id="6113d-121">Sometimes the display name will be made up of two parts; a part assigned by the message service and a part assigned by the user.</span></span> <span data-ttu-id="6113d-122">如果用户是负责分配的部分之一，这通常是一个特殊的对话框，称为消息服务的客户端应用程序控制下提供的属性表处理。</span><span class="sxs-lookup"><span data-stu-id="6113d-122">If the user is responsible for assigning one of the parts, this is typically handled with a special dialog box known as a property sheet supplied by the message service under the control of a client application.</span></span> 
  
<span data-ttu-id="6113d-123">提供**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 条目的信息是包含邮件服务的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="6113d-123">The information provided for the **PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) entry is the name of the DLL that contains the message service.</span></span> <span data-ttu-id="6113d-124">提供**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 条目的信息是内 MAPI 调用配置消息服务的 DLL 入口点函数的名称。</span><span class="sxs-lookup"><span data-stu-id="6113d-124">The information provided for the **PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) entry is the name of the entry point function within that DLL that MAPI calls to configure the message service.</span></span> 
  
<span data-ttu-id="6113d-125">**PR_SERVICE_SUPPORT_FILES** ([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md)) 条目中列出的文件都必须安装与消息服务的文件。</span><span class="sxs-lookup"><span data-stu-id="6113d-125">The files listed in the **PR_SERVICE_SUPPORT_FILES** ([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md)) entry are files that must be installed with the message service.</span></span> <span data-ttu-id="6113d-126">同样时删除邮件服务,，则必须删除**PR_SERVICE_DELETE_FILES** ([PidTagServiceDeleteFiles](pidtagservicedeletefiles-canonical-property.md)) 条目中的文件。</span><span class="sxs-lookup"><span data-stu-id="6113d-126">Likewise, the files in the **PR_SERVICE_DELETE_FILES** ([PidTagServiceDeleteFiles](pidtagservicedeletefiles-canonical-property.md)) entry must be removed when the message service is removed.</span></span> 
  
<span data-ttu-id="6113d-127">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 条目是定义消息服务选项的集合。</span><span class="sxs-lookup"><span data-stu-id="6113d-127">The **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) entry is a collection of options defined for the message service.</span></span> <span data-ttu-id="6113d-128">例如，当邮件服务仅可以一次出现在给定配置文件设置 SERVICE_SINGLE_COPY 位。</span><span class="sxs-lookup"><span data-stu-id="6113d-128">For example, the SERVICE_SINGLE_COPY bit is set when the message service can only appear once in a given profile.</span></span> <span data-ttu-id="6113d-129">如果邮件服务不提供标识信息，设置 SERVICE_NO_PRIMARY_IDENTITY 位。</span><span class="sxs-lookup"><span data-stu-id="6113d-129">The SERVICE_NO_PRIMARY_IDENTITY bit is set if the message service does not provide identity information.</span></span> 
  
<span data-ttu-id="6113d-130">两个非标准属性条目的示例。</span><span class="sxs-lookup"><span data-stu-id="6113d-130">Two examples of nonstandard property entries follow.</span></span> <span data-ttu-id="6113d-131">第一个条目指定为该属性值; 使用默认通讯簿的文件的路径第二项中指定的数字属性值。</span><span class="sxs-lookup"><span data-stu-id="6113d-131">The first entry specifies the path to the file used by the Default Address Book as the property value; the second entry specifies a numeric property value.</span></span> <span data-ttu-id="6113d-132">这两个条目具有特定于 AB 消息服务的含义。</span><span class="sxs-lookup"><span data-stu-id="6113d-132">Both entries have meaning specific to the AB message service.</span></span>
  
```cpp
6600001e=full path to file
66040003=integer

```


