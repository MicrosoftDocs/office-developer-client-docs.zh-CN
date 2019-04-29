---
title: mapisvc.inf 服务提供程序部分
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
# <a name="mapisvcinf-service-provider-sections"></a>mapisvc.inf 服务提供程序部分

**适用于**：Outlook 2013 | Outlook 2016 
  
对于前面的 "邮件服务" 一节中的 "**提供程序**" 条目中列出的每个条目, mapisvc.inf 都包含一个 "服务提供程序" 部分。 **服务**提供程序节类似于 "邮件服务" 部分, 这两种类型的节都包含以下格式的条目: 
  
**属性标记**= 属性值 
  
但是, 服务提供程序部分和邮件服务节各不相同, 这种属性条目是服务提供商部分中的唯一条目类型。 服务提供商可能没有任何附加或链接的部分;所有服务提供程序信息必须包含在一节中。 
  
在 "邮件服务" 部分中设置的一些属性也是在服务提供商部分中设置的, 因为这些属性对这两个部分都有意义。 **PR_DISPLAY_NAME**属性是一个示例。 服务提供程序和邮件服务都有一个用于在配置用户界面中显示的名称。 根据服务提供商的不同, 该名称可能是相同的, 也可能不相同。 其他属性特定于服务提供商。 
  
典型的服务提供程序部分包括以下各项, 它们都是必需的:
  
**PR_DISPLAY_NAME** =  _字符串_
  
**PR_PROVIDER_DISPLAY** =  _字符串_
  
**** =  _DLL 文件的 PR_PROVIDER_DLL_NAME 名称_
  
**PR_RESOURCE_TYPE** =  _long_
  
**PR_RESOURCE_FLAGS** =  _位掩码_
  
**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 条目类似于**PR_SERVICE_DLL_NAME**;它指示包含服务提供程序的 DLL 的文件名。 邮件服务代码可以与它的一个服务提供程序存储在同一个 dll 文件中或作为一个单独的 DLL 存在。 请注意, 在条目中不包含任何后缀, 无论目标平台是什么;如果需要, MAPI 将负责添加后缀。 
  
**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 条目表示服务提供程序的类型;服务提供程序将其设置为适当的预定义常量。 有效值包括 MAPI_STORE_PROVIDER、MAPI_TRANSPORT_PROVIDER 和 MAPI_AB_PROVIDER。
  
另一个适用于邮件服务和服务提供程序的属性项, **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 条目指示选项。 此属性项的设置可能会有所不同, 具体取决于服务提供程序。 例如, 某些邮件存储提供程序可能会将**PR_RESOURCE_FLAGS**设置为 STATUS_NO_DEFAULT_STORE (如果它们永远不能作为默认邮件存储区运行)。 
  
下面是三个服务提供程序部分的示例。 **[AB 提供程序]** 一节是默认通讯簿服务的服务提供程序部分。 **[MsgService Prov1]** 和 **[MsgService Prov2]** 节属于我自己的服务;第一个是 "通讯簿提供程序" 部分, 第二个是 "邮件存储提供程序" 部分。 
  
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


