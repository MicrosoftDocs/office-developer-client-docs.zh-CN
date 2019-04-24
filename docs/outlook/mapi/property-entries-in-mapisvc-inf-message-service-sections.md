---
title: mapisvc.inf 邮件服务部分中的属性条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 714f99e2-80fc-4785-b707-611d8a6c229f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ad2732f2f8dba4f506318a1b6faefb617a60584a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328516"
---
# <a name="property-entries-in-mapisvcinf-message-service-sections"></a><span data-ttu-id="7e0a1-103">mapisvc.inf 邮件服务部分中的属性条目</span><span class="sxs-lookup"><span data-stu-id="7e0a1-103">Property Entries in MapiSvc.inf Message Service Sections</span></span>

  
  
<span data-ttu-id="7e0a1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7e0a1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7e0a1-105">设置了属性的条目使用以下格式:</span><span class="sxs-lookup"><span data-stu-id="7e0a1-105">Entries that set properties use this format:</span></span>
  
 <span data-ttu-id="7e0a1-106">**属性标记\*\*\*\*=** 属性值</span><span class="sxs-lookup"><span data-stu-id="7e0a1-106">**property tag** **=** property value</span></span> 
  
<span data-ttu-id="7e0a1-107">如果配置数据表示由 MAPI 预定义的属性之一, 则该属性标记可以是标准 MAPI 属性标记, 如果数据不代表 mapi 属性, 则为非标准标记。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-107">The property tag can be a standard MAPI property tag if the configuration data represents one of the properties predefined by MAPI, or a nonstandard tag if the data does not represent a MAPI property.</span></span> <span data-ttu-id="7e0a1-108">通过将属性标识符的值与属性类型相结合来生成非标准标记。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-108">The nonstandard tag is made by combining the value for a property identifier with a property type.</span></span> <span data-ttu-id="7e0a1-109">结果是一个8位十六进制数。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-109">The result is an 8 digit hexadecimal number.</span></span> <span data-ttu-id="7e0a1-110">属性值可以是对属性标记有意义的任何内容。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-110">The property value can be whatever makes sense for the property tag.</span></span> 
  
<span data-ttu-id="7e0a1-111">邮件服务部分可以包含不同的条目, 具体取决于正在配置的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-111">Message service sections can contain a variety of entries depending on the message service being configured.</span></span> <span data-ttu-id="7e0a1-112">以下 MAPI 属性通常以列出的格式包含在 "邮件服务" 部分中:</span><span class="sxs-lookup"><span data-stu-id="7e0a1-112">The following MAPI properties are typically included in a message services section in the listed format:</span></span>
  
 <span data-ttu-id="7e0a1-113">**PR_DISPLAY_NAME** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="7e0a1-113">**PR_DISPLAY_NAME** =  _string_</span></span>
  
 <span data-ttu-id="7e0a1-114">\*\*\*\* =  _DLL 文件的 PR_SERVICE_DLL_NAME 名称_</span><span class="sxs-lookup"><span data-stu-id="7e0a1-114">**PR_SERVICE_DLL_NAME** =  _name of DLL file_</span></span>
  
 <span data-ttu-id="7e0a1-115">\*\*\*\* =  _入口点函数的 PR_SERVICE_ENTRY_NAME 名称_</span><span class="sxs-lookup"><span data-stu-id="7e0a1-115">**PR_SERVICE_ENTRY_NAME** =  _name of entry point function_</span></span>
  
 <span data-ttu-id="7e0a1-116">**PR_SERVICE_SUPPORT_FILES** =  _文件列表_</span><span class="sxs-lookup"><span data-stu-id="7e0a1-116">**PR_SERVICE_SUPPORT_FILES** =  _list of files_</span></span>
  
 <span data-ttu-id="7e0a1-117">**PR_SERVICE_DELETE_FILES** =  _文件列表_</span><span class="sxs-lookup"><span data-stu-id="7e0a1-117">**PR_SERVICE_DELETE_FILES** =  _list of files_</span></span>
  
 <span data-ttu-id="7e0a1-118">**PR_RESOURCE_FLAGS** =  _位掩码_</span><span class="sxs-lookup"><span data-stu-id="7e0a1-118">**PR_RESOURCE_FLAGS** =  _bitmask_</span></span>
  
<span data-ttu-id="7e0a1-119">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 字符串是在用户界面中显示的邮件服务的名称, 该用户与邮件服务关联的名称。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-119">The **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) string is the name of the message service that is shown in the user interface, the name that the user associates with the message service.</span></span> <span data-ttu-id="7e0a1-120">显示名称是 mapisvc.inf 中的可选条目。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-120">The display name is an optional entry in mapisvc.inf.</span></span> <span data-ttu-id="7e0a1-121">显示名称有时由两部分组成;由邮件服务和用户分配的部件分配的部件。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-121">Sometimes the display name will be made up of two parts; a part assigned by the message service and a part assigned by the user.</span></span> <span data-ttu-id="7e0a1-122">如果用户负责分配其中一个部件, 通常会使用一个特殊的对话框来处理, 该对话框称为属性表 (由邮件服务在客户端应用程序的控制下提供)。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-122">If the user is responsible for assigning one of the parts, this is typically handled with a special dialog box known as a property sheet supplied by the message service under the control of a client application.</span></span> 
  
<span data-ttu-id="7e0a1-123">为**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 条目提供的信息是包含邮件服务的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-123">The information provided for the **PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) entry is the name of the DLL that contains the message service.</span></span> <span data-ttu-id="7e0a1-124">为**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 条目提供的信息是该 DLL 中的入口点函数的名称, MAPI 调用它来配置邮件服务。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-124">The information provided for the **PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) entry is the name of the entry point function within that DLL that MAPI calls to configure the message service.</span></span> 
  
<span data-ttu-id="7e0a1-125">**PR_SERVICE_SUPPORT_FILES** ([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md)) 条目中列出的文件是必须随邮件服务一起安装的文件。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-125">The files listed in the **PR_SERVICE_SUPPORT_FILES** ([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md)) entry are files that must be installed with the message service.</span></span> <span data-ttu-id="7e0a1-126">同样, 删除邮件服务时, 必须删除**PR_SERVICE_DELETE_FILES** ([PidTagServiceDeleteFiles](pidtagservicedeletefiles-canonical-property.md)) 条目中的文件。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-126">Likewise, the files in the **PR_SERVICE_DELETE_FILES** ([PidTagServiceDeleteFiles](pidtagservicedeletefiles-canonical-property.md)) entry must be removed when the message service is removed.</span></span> 
  
<span data-ttu-id="7e0a1-127">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 条目是为邮件服务定义的选项的集合。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-127">The **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) entry is a collection of options defined for the message service.</span></span> <span data-ttu-id="7e0a1-128">例如, 当邮件服务在给定配置文件中只能出现一次时, 将设置 SERVICE_SINGLE_COPY 位。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-128">For example, the SERVICE_SINGLE_COPY bit is set when the message service can only appear once in a given profile.</span></span> <span data-ttu-id="7e0a1-129">如果消息服务不提供标识信息, 则设置 SERVICE_NO_PRIMARY_IDENTITY 位。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-129">The SERVICE_NO_PRIMARY_IDENTITY bit is set if the message service does not provide identity information.</span></span> 
  
<span data-ttu-id="7e0a1-130">下面是两个非标准属性条目的示例。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-130">Two examples of nonstandard property entries follow.</span></span> <span data-ttu-id="7e0a1-131">第一项指定默认通讯簿使用的文件的路径作为属性值;第二个条目指定数值属性值。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-131">The first entry specifies the path to the file used by the Default Address Book as the property value; the second entry specifies a numeric property value.</span></span> <span data-ttu-id="7e0a1-132">这两个条目都具有对 AB 邮件服务的意义。</span><span class="sxs-lookup"><span data-stu-id="7e0a1-132">Both entries have meaning specific to the AB message service.</span></span>
  
```cpp
6600001e=full path to file
66040003=integer

```


