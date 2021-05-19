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
# <a name="property-entries-in-mapisvcinf-message-service-sections"></a>MapiSvc.inf 邮件服务节中的属性条目

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置属性的条目使用以下格式：
  
 **属性标记** **=** 属性值 
  
如果配置数据代表 MAPI 预定义的属性之一，则属性标记可以是标准 MAPI 属性标记;如果数据不代表 MAPI 属性，则该属性标记可以是非标准标记。 非标准标记通过将属性标识符的值与属性类型组合进行。 结果是一个 8 位十六进制数。 属性值可以是对属性标记有意义的任何内容。 
  
邮件服务部分可以包含各种条目，具体取决于要配置的邮件服务。 以下 MAPI 属性通常以列出的格式包含在邮件服务部分中：
  
 **PR_DISPLAY_NAME**  =  _string_
  
 **PR_SERVICE_DLL_NAME**  =  _DLL 文件的名称_
  
 **PR_SERVICE_ENTRY_NAME**  =  _入口点函数的名称_
  
 **PR_SERVICE_SUPPORT_FILES**  =  _文件列表_
  
 **PR_SERVICE_DELETE_FILES**  =  _文件列表_
  
 **PR_RESOURCE_FLAGS**  =  _位掩码_
  
**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 字符串是用户界面中显示的邮件服务的名称，即用户与邮件服务关联的名称。 the 显示名称 is an optional entry in mapisvc.inf. 有时显示名称由两部分组成;邮件服务分配的部件和用户分配的部件。 如果用户负责分配其中一个部件，则通常使用称为 属性表 的特殊对话框处理，该对话框由客户端应用程序控制下的邮件服务提供。 
  
为[PidTagServiceDllName PR_SERVICE_DLL_NAME (PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 条目提供的信息是包含邮件服务的 DLL 的名称。  为 PR_SERVICE_ENTRY_NAME ( [PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 条目提供的信息是 MAPI 调用以配置邮件服务的 DLL 中的入口点函数的名称。 
  
[PR_SERVICE_SUPPORT_FILES (PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md)) 中列出的文件是必须随邮件服务一起安装的文件。  同样，删除邮件服务PR_SERVICE_DELETE_FILES ( [PidTagServiceDeleteFiles) 中删除 PidTagServiceDeleteFiles](pidtagservicedeletefiles-canonical-property.md)条目中的文件。 
  
[PidTagResourceFlag) s PR_RESOURCE_FLAGS (PidTagResourceFlags](pidtagresourceflags-canonical-property.md)条目是为邮件服务定义的选项集合。  例如，当SERVICE_SINGLE_COPY配置文件中只能显示一次时，将设置该位。 如果SERVICE_NO_PRIMARY_IDENTITY未提供标识信息，则设置此SERVICE_NO_PRIMARY_IDENTITY位。 
  
以下是两个非标准属性项的示例。 第一个条目指定默认通讯簿用作属性值的文件的路径;第二个条目指定一个数值属性值。 这两个条目的含义特定于 AB 邮件服务。
  
```cpp
6600001e=full path to file
66040003=integer

```


