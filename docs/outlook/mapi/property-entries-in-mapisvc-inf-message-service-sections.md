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
ms.openlocfilehash: 30f5e0b59bacfab91a3a6c77c0b345d6299df9e5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778557"
---
# <a name="property-entries-in-mapisvcinf-message-service-sections"></a>MapiSvc.inf 邮件服务部分中的属性条目

  
  
**适用于**： Outlook 
  
设置属性的项使用以下格式：
  
 **属性标记****=** 属性值 
  
如果数据不表示的 MAPI 属性，可以标准的 MAPI 属性标记，如果配置数据表示 MAPI，由预定义的属性之一或非标准标记属性标记。 通过将与属性类型组合属性标识符的值进行的非标准标记。 结果是 8 位十六进制数。 该属性值可以是任何有意义属性标记。 
  
消息服务各节可以包含各种具体取决于要配置的消息服务的条目。 下面的 MAPI 属性通常包括在邮件服务节中列出的格式：
  
 **PR_DISPLAY_NAME** =  _字符串_
  
 **PR_SERVICE_DLL_NAME** =  _DLL 文件的名称_
  
 **PR_SERVICE_ENTRY_NAME** =  _的入口点函数名称_
  
 **PR_SERVICE_SUPPORT_FILES** =  _的文件列表_
  
 **PR_SERVICE_DELETE_FILES** =  _的文件列表_
  
 **PR_RESOURCE_FLAGS** =  _位掩码_
  
**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 字符串是在用户界面中，用户与邮件服务关联的名称显示的消息服务的名称。 显示名称为 mapisvc.inf 中的可选条目。 有时的显示名称将是两个部分组成;消息服务分配的部件和由用户分配一个部分。 如果用户是负责分配的部分之一，这通常是一个特殊的对话框，称为消息服务的客户端应用程序控制下提供的属性表处理。 
  
提供**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 条目的信息是包含邮件服务的 DLL 的名称。 提供**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 条目的信息是内 MAPI 调用配置消息服务的 DLL 入口点函数的名称。 
  
**PR_SERVICE_SUPPORT_FILES** ([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md)) 条目中列出的文件都必须安装与消息服务的文件。 同样时删除邮件服务,，则必须删除**PR_SERVICE_DELETE_FILES** ([PidTagServiceDeleteFiles](pidtagservicedeletefiles-canonical-property.md)) 条目中的文件。 
  
**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 条目是定义消息服务选项的集合。 例如，当邮件服务仅可以一次出现在给定配置文件设置 SERVICE_SINGLE_COPY 位。 如果邮件服务不提供标识信息，设置 SERVICE_NO_PRIMARY_IDENTITY 位。 
  
两个非标准属性条目的示例。 第一个条目指定为该属性值; 使用默认通讯簿的文件的路径第二项中指定的数字属性值。 这两个条目具有特定于 AB 消息服务的含义。
  
```cpp
6600001e=full path to file
66040003=integer

```


