---
title: MapiSvc.inf 邮件服务节中的属性条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 714f99e2-80fc-4785-b707-611d8a6c229f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ad2732f2f8dba4f506318a1b6faefb617a60584a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427995"
---
# <a name="property-entries-in-mapisvcinf-message-service-sections"></a><span data-ttu-id="131ad-103">MapiSvc.inf 邮件服务节中的属性条目</span><span class="sxs-lookup"><span data-stu-id="131ad-103">Property Entries in MapiSvc.inf Message Service Sections</span></span>

  
  
<span data-ttu-id="131ad-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="131ad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="131ad-105">设置属性的条目使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="131ad-105">Entries that set properties use this format:</span></span>
  
 <span data-ttu-id="131ad-106">**属性标记** **=** 属性值</span><span class="sxs-lookup"><span data-stu-id="131ad-106">**property tag** **=** property value</span></span> 
  
<span data-ttu-id="131ad-107">如果配置数据代表 MAPI 预定义的属性之一，则属性标记可以是标准 MAPI 属性标记;如果数据不代表 MAPI 属性，则该属性标记可以是非标准标记。</span><span class="sxs-lookup"><span data-stu-id="131ad-107">The property tag can be a standard MAPI property tag if the configuration data represents one of the properties predefined by MAPI, or a nonstandard tag if the data does not represent a MAPI property.</span></span> <span data-ttu-id="131ad-108">非标准标记通过将属性标识符的值与属性类型组合进行。</span><span class="sxs-lookup"><span data-stu-id="131ad-108">The nonstandard tag is made by combining the value for a property identifier with a property type.</span></span> <span data-ttu-id="131ad-109">结果是一个 8 位十六进制数。</span><span class="sxs-lookup"><span data-stu-id="131ad-109">The result is an 8 digit hexadecimal number.</span></span> <span data-ttu-id="131ad-110">属性值可以是对属性标记有意义的任何内容。</span><span class="sxs-lookup"><span data-stu-id="131ad-110">The property value can be whatever makes sense for the property tag.</span></span> 
  
<span data-ttu-id="131ad-111">邮件服务部分可以包含各种条目，具体取决于要配置的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="131ad-111">Message service sections can contain a variety of entries depending on the message service being configured.</span></span> <span data-ttu-id="131ad-112">以下 MAPI 属性通常以列出的格式包含在邮件服务部分中：</span><span class="sxs-lookup"><span data-stu-id="131ad-112">The following MAPI properties are typically included in a message services section in the listed format:</span></span>
  
 <span data-ttu-id="131ad-113">**PR_DISPLAY_NAME**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="131ad-113">**PR_DISPLAY_NAME** =  _string_</span></span>
  
 <span data-ttu-id="131ad-114">**PR_SERVICE_DLL_NAME**  =  _DLL 文件的名称_</span><span class="sxs-lookup"><span data-stu-id="131ad-114">**PR_SERVICE_DLL_NAME** =  _name of DLL file_</span></span>
  
 <span data-ttu-id="131ad-115">**PR_SERVICE_ENTRY_NAME**  =  _入口点函数的名称_</span><span class="sxs-lookup"><span data-stu-id="131ad-115">**PR_SERVICE_ENTRY_NAME** =  _name of entry point function_</span></span>
  
 <span data-ttu-id="131ad-116">**PR_SERVICE_SUPPORT_FILES**  =  _文件列表_</span><span class="sxs-lookup"><span data-stu-id="131ad-116">**PR_SERVICE_SUPPORT_FILES** =  _list of files_</span></span>
  
 <span data-ttu-id="131ad-117">**PR_SERVICE_DELETE_FILES**  =  _文件列表_</span><span class="sxs-lookup"><span data-stu-id="131ad-117">**PR_SERVICE_DELETE_FILES** =  _list of files_</span></span>
  
 <span data-ttu-id="131ad-118">**PR_RESOURCE_FLAGS**  =  _位掩码_</span><span class="sxs-lookup"><span data-stu-id="131ad-118">**PR_RESOURCE_FLAGS** =  _bitmask_</span></span>
  
<span data-ttu-id="131ad-119">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 字符串是用户界面中显示的邮件服务的名称，即用户与邮件服务关联的名称。</span><span class="sxs-lookup"><span data-stu-id="131ad-119">The **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) string is the name of the message service that is shown in the user interface, the name that the user associates with the message service.</span></span> <span data-ttu-id="131ad-120">the 显示名称 is an optional entry in mapisvc.inf.</span><span class="sxs-lookup"><span data-stu-id="131ad-120">The display name is an optional entry in mapisvc.inf.</span></span> <span data-ttu-id="131ad-121">有时显示名称由两部分组成;邮件服务分配的部件和用户分配的部件。</span><span class="sxs-lookup"><span data-stu-id="131ad-121">Sometimes the display name will be made up of two parts; a part assigned by the message service and a part assigned by the user.</span></span> <span data-ttu-id="131ad-122">如果用户负责分配其中一个部件，则通常使用称为 属性表 的特殊对话框处理，该对话框由客户端应用程序控制下的邮件服务提供。</span><span class="sxs-lookup"><span data-stu-id="131ad-122">If the user is responsible for assigning one of the parts, this is typically handled with a special dialog box known as a property sheet supplied by the message service under the control of a client application.</span></span> 
  
<span data-ttu-id="131ad-123">为[PidTagServiceDllName PR_SERVICE_DLL_NAME (PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 条目提供的信息是包含邮件服务的 DLL 的名称。 </span><span class="sxs-lookup"><span data-stu-id="131ad-123">The information provided for the **PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) entry is the name of the DLL that contains the message service.</span></span> <span data-ttu-id="131ad-124">为 PR_SERVICE_ENTRY_NAME ( [PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 条目提供的信息是 MAPI 调用以配置邮件服务的 DLL 中的入口点函数的名称。</span><span class="sxs-lookup"><span data-stu-id="131ad-124">The information provided for the **PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) entry is the name of the entry point function within that DLL that MAPI calls to configure the message service.</span></span> 
  
<span data-ttu-id="131ad-125">[PR_SERVICE_SUPPORT_FILES (PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md)) 中列出的文件是必须随邮件服务一起安装的文件。 </span><span class="sxs-lookup"><span data-stu-id="131ad-125">The files listed in the **PR_SERVICE_SUPPORT_FILES** ([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md)) entry are files that must be installed with the message service.</span></span> <span data-ttu-id="131ad-126">同样，删除邮件服务PR_SERVICE_DELETE_FILES ( [PidTagServiceDeleteFiles) 中删除 PidTagServiceDeleteFiles](pidtagservicedeletefiles-canonical-property.md)条目中的文件。</span><span class="sxs-lookup"><span data-stu-id="131ad-126">Likewise, the files in the **PR_SERVICE_DELETE_FILES** ([PidTagServiceDeleteFiles](pidtagservicedeletefiles-canonical-property.md)) entry must be removed when the message service is removed.</span></span> 
  
<span data-ttu-id="131ad-127">[PidTagResourceFlag) s PR_RESOURCE_FLAGS (PidTagResourceFlags](pidtagresourceflags-canonical-property.md)条目是为邮件服务定义的选项集合。 </span><span class="sxs-lookup"><span data-stu-id="131ad-127">The **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) entry is a collection of options defined for the message service.</span></span> <span data-ttu-id="131ad-128">例如，当SERVICE_SINGLE_COPY配置文件中只能显示一次时，将设置该位。</span><span class="sxs-lookup"><span data-stu-id="131ad-128">For example, the SERVICE_SINGLE_COPY bit is set when the message service can only appear once in a given profile.</span></span> <span data-ttu-id="131ad-129">如果SERVICE_NO_PRIMARY_IDENTITY未提供标识信息，则设置此SERVICE_NO_PRIMARY_IDENTITY位。</span><span class="sxs-lookup"><span data-stu-id="131ad-129">The SERVICE_NO_PRIMARY_IDENTITY bit is set if the message service does not provide identity information.</span></span> 
  
<span data-ttu-id="131ad-130">以下是两个非标准属性项的示例。</span><span class="sxs-lookup"><span data-stu-id="131ad-130">Two examples of nonstandard property entries follow.</span></span> <span data-ttu-id="131ad-131">第一个条目指定默认通讯簿用作属性值的文件的路径;第二个条目指定一个数值属性值。</span><span class="sxs-lookup"><span data-stu-id="131ad-131">The first entry specifies the path to the file used by the Default Address Book as the property value; the second entry specifies a numeric property value.</span></span> <span data-ttu-id="131ad-132">这两个条目的含义特定于 AB 邮件服务。</span><span class="sxs-lookup"><span data-stu-id="131ad-132">Both entries have meaning specific to the AB message service.</span></span>
  
```cpp
6600001e=full path to file
66040003=integer

```


