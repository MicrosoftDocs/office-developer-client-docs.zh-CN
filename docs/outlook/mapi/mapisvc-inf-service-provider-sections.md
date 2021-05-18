---
title: MapiSvc.inf 服务提供程序部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ab17dcf2-409b-4a57-9cc4-5794f995cd3e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ea192ec6356cc3b929bf8379567144d3a54223f2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405560"
---
# <a name="mapisvcinf-service-provider-sections"></a>MapiSvc.inf 服务提供程序部分

**适用于**：Outlook 2013 | Outlook 2016 
  
Mapisvc.inf 包含一个针对前面邮件服务部分"提供程序"条目中列出的每个条目的服务提供商部分。 **服务** 提供程序部分类似于邮件服务节，两种类型的节均包含以下格式的条目： 
  
**property tag** = 属性值 
  
但是，服务提供程序节和邮件服务部分的不同是，此类属性条目是服务提供程序节中包含的唯一类型的条目。 服务提供程序不能有其他或链接的分区;所有服务提供程序信息必须包含在一个部分中。 
  
邮件服务部分中设置的一些属性也在服务提供程序部分中设置，因为这些属性对两者都有意义。 PR_DISPLAY_NAME **是** 一个示例。 服务提供程序和邮件服务的名称均用于在配置用户界面中显示。 根据服务提供商的不同，该名称可能相同，也可能不同。 其他属性特定于服务提供商。 
  
典型的服务提供程序部分包括以下条目，所有这些条目都是必需的：
  
**PR_DISPLAY_NAME**  =  _string_
  
**PR_PROVIDER_DISPLAY**  =  _string_
  
**PR_PROVIDER_DLL_NAME**  =  _DLL 文件的名称_
  
**PR_RESOURCE_TYPE**  =  _long_
  
**PR_RESOURCE_FLAGS**  =  _位掩码_
  
[PidTagProviderDllName PR_PROVIDER_DLL_NAME (PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 类似于 PR_SERVICE_DLL_NAME **;** 它指示包含服务提供商的 DLL 的文件名。 邮件服务代码可以与它的一个服务提供程序存储在同一 DLL 文件中，也可以作为单独的 DLL 存在。 请注意，无论目标平台如何，条目中均不包含后缀;MAPI 负责在必要时添加后缀。 
  
**PR_RESOURCE_TYPE (** [PidTagResourceType](pidtagresourcetype-canonical-property.md)) 条目表示服务提供商的类型;服务提供程序会设置为适当的预定义常量。 有效值包括 MAPI_STORE_PROVIDER、MAPI_TRANSPORT_PROVIDER 和 MAPI_AB_PROVIDER。
  
另一个同时适用于邮件服务和服务提供程序的属性项是[PidTagResourceFlags PR_RESOURCE_FLAGS (PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 指示选项。  此属性项的设置可能因服务提供商而异。 例如，如果某些邮件存储PR_RESOURCE_FLAGS无法STATUS_NO_DEFAULT_STORE默认邮件存储，则这些提供程序可能会将邮件存储设置为默认邮件存储。 
  
以下是服务提供商各节的三个示例。 **[AB Provider]** 部分是默认通讯簿服务的服务提供商部分。 **[MsgService Prov1]** **和 [MsgService Prov2]** 部分属于"我的服务";第一个为通讯簿提供程序部分，第二个为邮件存储提供程序部分。 
  
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


