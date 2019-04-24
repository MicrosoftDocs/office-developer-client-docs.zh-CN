---
title: 实现通讯簿提供程序入口点函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9375b351-1c84-4728-bcdf-e3e7a44820ed
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 00b3b30101ee1efb984cf45afb35b0b085d545ac
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332800"
---
# <a name="implementing-an-address-book-provider-entry-point-function"></a>实现通讯簿提供程序入口点函数

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端应用程序调用[MAPILogonEx](mapilogonex.md)以使用包含通讯簿提供程序的配置文件开始会话时, MAPI 将加载您的提供程序以及作为该配置文件一部分的所有其他项。 MAPI 通过查看配置文件了解提供程序的入口点函数的名称。 请注意, 此函数与 DLL 入口点函数不同;请参阅 Win32 文档中有关**DllMain**的文档。 
  
有几个条目, 其中一些必须出现在 mapisvc.inf 配置文件中, 这些条目包含在每个通讯簿提供程序的 "配置文件" 部分中。 下表列出了这些配置文件节项, 以及 mapisvc.inf 文件是否必须包含它们。
  
|**配置文件节项**|**mapisvc.inf 要求**|
|:-----|:-----|
|PR_DISPLAY_NAME = _string_ <br/> |可选  <br/> |
|PR_PROVIDER_DISPLAY = _string_ <br/> |必需  <br/> |
|PR_PROVIDER_DLL_NAME = _DLL 文件名_ <br/> |必需  <br/> |
|PR_RESOURCE_TYPE = _long_ <br/> |必需  <br/> |
|PR_RESOURCE_FLAGS =_位掩码_ <br/> |可选  <br/> |
   
您的通讯簿提供程序可以通过调用其 profile 节的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法或通过修改 mapisvc.inf 来间接将此信息放入配置文件中。 配置文件是使用 mapisvc.inf 中的相关信息生成的。所选服务提供商或邮件服务的 INF。 有关 mapisvc.inf 的组织和内容的详细信息。inf, 请参阅[mapisvc.inf 的文件格式](file-format-of-mapisvc-inf.md)。
  
您的通讯簿提供程序的 DLL 入口点函数的名称必须为[ABProviderInit](abproviderinit.md) , 并且必须符合**ABProviderInit**原型。 在提供程序的 DLL 入口点函数中执行以下任务: 
  
- 检查服务提供程序接口 (SPI) 的版本, 确保 MAPI 使用的版本与您的通讯簿提供程序使用的版本兼容。
    
- 实例化通讯簿提供程序对象。
    
请勿在此函数中调用**MAPIInitialize**或**MAPIUninitialize** 。 
  
DLL 入口点函数实例化提供程序对象, 并返回到 MAPI 指向该对象的指针。 
  

