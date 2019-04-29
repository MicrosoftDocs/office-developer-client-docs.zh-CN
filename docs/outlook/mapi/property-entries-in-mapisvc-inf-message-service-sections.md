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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427995"
---
# <a name="property-entries-in-mapisvcinf-message-service-sections"></a>mapisvc.inf 邮件服务部分中的属性条目

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置了属性的条目使用以下格式:
  
 **属性标记****=** 属性值 
  
如果配置数据表示由 MAPI 预定义的属性之一, 则该属性标记可以是标准 MAPI 属性标记, 如果数据不代表 mapi 属性, 则为非标准标记。 通过将属性标识符的值与属性类型相结合来生成非标准标记。 结果是一个8位十六进制数。 属性值可以是对属性标记有意义的任何内容。 
  
邮件服务部分可以包含不同的条目, 具体取决于正在配置的邮件服务。 以下 MAPI 属性通常以列出的格式包含在 "邮件服务" 部分中:
  
 **PR_DISPLAY_NAME** =  _字符串_
  
 **** =  _DLL 文件的 PR_SERVICE_DLL_NAME 名称_
  
 **** =  _入口点函数的 PR_SERVICE_ENTRY_NAME 名称_
  
 **PR_SERVICE_SUPPORT_FILES** =  _文件列表_
  
 **PR_SERVICE_DELETE_FILES** =  _文件列表_
  
 **PR_RESOURCE_FLAGS** =  _位掩码_
  
**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 字符串是在用户界面中显示的邮件服务的名称, 该用户与邮件服务关联的名称。 显示名称是 mapisvc.inf 中的可选条目。 显示名称有时由两部分组成;由邮件服务和用户分配的部件分配的部件。 如果用户负责分配其中一个部件, 通常会使用一个特殊的对话框来处理, 该对话框称为属性表 (由邮件服务在客户端应用程序的控制下提供)。 
  
为**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 条目提供的信息是包含邮件服务的 DLL 的名称。 为**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 条目提供的信息是该 DLL 中的入口点函数的名称, MAPI 调用它来配置邮件服务。 
  
**PR_SERVICE_SUPPORT_FILES** ([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md)) 条目中列出的文件是必须随邮件服务一起安装的文件。 同样, 删除邮件服务时, 必须删除**PR_SERVICE_DELETE_FILES** ([PidTagServiceDeleteFiles](pidtagservicedeletefiles-canonical-property.md)) 条目中的文件。 
  
**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 条目是为邮件服务定义的选项的集合。 例如, 当邮件服务在给定配置文件中只能出现一次时, 将设置 SERVICE_SINGLE_COPY 位。 如果消息服务不提供标识信息, 则设置 SERVICE_NO_PRIMARY_IDENTITY 位。 
  
下面是两个非标准属性条目的示例。 第一项指定默认通讯簿使用的文件的路径作为属性值;第二个条目指定数值属性值。 这两个条目都具有对 AB 邮件服务的意义。
  
```cpp
6600001e=full path to file
66040003=integer

```


