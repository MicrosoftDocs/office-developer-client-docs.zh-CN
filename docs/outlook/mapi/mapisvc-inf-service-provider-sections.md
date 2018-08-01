---
title: MapiSvc.inf 服务提供程序部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ab17dcf2-409b-4a57-9cc4-5794f995cd3e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ad6a4661025dfd8cbd39d8f58a36d94ab997ada2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776406"
---
# <a name="mapisvcinf-service-provider-sections"></a>MapiSvc.inf 服务提供程序部分

**适用于**： Outlook 
  
Mapisvc.inf 上述邮件服务部分中的**提供程序**条目中列出的项的每个包含服务提供程序的一部分。 **服务**提供程序部分是邮件服务节相似，，这两种类型的各节包含采用以下格式的条目： 
  
**属性标记**= 属性值 
  
但是，服务提供程序节和消息服务节不同，此类属性条目都是唯一的服务提供程序部分中包含的条目类型。 可以有服务提供商; 没有其他或链接部分一个节中必须包含所有服务提供商信息。 
  
设置消息服务各节中的属性的一些也设置在服务提供程序部分因为这些属性有意义的同时。 **PR_DISPLAY_NAME**属性是一个示例。 服务提供商和消息服务具有用于配置用户界面中显示的名称。 根据服务提供商，该名称可能也可能不能相同。 其他属性是特定于服务提供商。 
  
典型的服务提供程序部分包含以下各项，所有这些都需要：
  
**PR_DISPLAY_NAME** =  _字符串_
  
**PR_PROVIDER_DISPLAY** =  _字符串_
  
**PR_PROVIDER_DLL_NAME** =  _DLL 文件的名称_
  
**PR_RESOURCE_TYPE** =  _长_
  
**PR_RESOURCE_FLAGS** =  _位掩码_
  
**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 条目是类似于**PR_SERVICE_DLL_NAME**;包含服务提供商的 DLL 的它指示文件名。 消息服务代码可能具有相同的 DLL 文件中其服务提供商之一存储或作为单独的 DLL 存在。 请注意，无论目标平台; 条目中包含没有后缀MAPI 负责根据需要添加后缀。 
  
**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 条目代表在服务提供程序; 的类型服务提供商将其设置为适当的预定义常量。 有效值包括 MAPI_STORE_PROVIDER、 MAPI_TRANSPORT_PROVIDER 和 MAPI_AB_PROVIDER。
  
适用于消息服务和服务提供商的另一个属性条目， **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 条目指示选项。 此属性的项的设置将不同根据服务提供商。 例如，某些消息存储提供程序可能设置**PR_RESOURCE_FLAGS**为 STATUS_NO_DEFAULT_STORE 如果从不用作默认邮件存储区。 
  
服务提供程序节的三个示例按照。 在 **[AB Provider]** 部分，默认通讯簿服务的服务提供程序部分。 **[MsgService Prov1]** 和 **[MsgService Prov2]** 部分属于我自己服务;第一个是通讯簿提供程序部分和第二个是消息存储提供程序部分。 
  
```cpp
[AB Provider]
PR_DISPLAY_NAME=Default Address Book
PR_PROVIDER_DISPLAY=Default Address Book
PR_PROVIDER_DLL_NAME=AB.DLL
PR_RESOURCE_TYPE=MAPI_AB_PROVIDER
6600001e=C:\WINNT35\System32\DEFAB.TXT
[MsgService Prov1]
PR_DISPLAY_NAME=My Own Service
PR_PROVIDER_DISPLAY=My Own Address Book
PR_PROVIDER_DLL_NAME=MYXXX.DLL
PR_RESOURCE_TYPE=MAPI_AB_PROVIDER
[MsgService Prov2]
PR_DISPLAY_NAME=My Folders
PR_PROVIDER_DISPLAY=My Own Message Store
PR_RESOURCE_TYPE=MAPI_STORE_PROVIDER
PR_PROVIDER_DLL_NAME=MYZZZ.DLL
PR_RESOURCE_FLAGS=STATUS_NO_DEFAULT_STORE
66060003=00000000
66030003=00000000
34140102=78b2fa70aff711cd9bc800aa002fc45a
66090003=06000000
660A0003=03000000

```


