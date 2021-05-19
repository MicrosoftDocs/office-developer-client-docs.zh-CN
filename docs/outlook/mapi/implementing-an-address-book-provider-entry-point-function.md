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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409711"
---
# <a name="implementing-an-address-book-provider-entry-point-function"></a>实现通讯簿提供程序入口点函数

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端应用程序调用 [MAPILogonEx](mapilogonex.md) 以使用包含通讯簿提供程序的配置文件开始会话时，MAPI 将加载您的提供程序以及属于该配置文件的所有其他项。 MAPI 通过查看配置文件来了解提供程序的入口点函数的名称。 请记住，此函数与 DLL 入口点函数不同;请参阅 Win32 文档中 **的 DllMain** 文档。 
  
有几个条目必须出现在 mapisvc.inf 配置文件中，其中包括每个通讯簿提供程序的配置文件部分。 下表列出了这些配置文件节条目以及 mapisvc.inf 文件是否必须包含它们。
  
|**配置文件节条目**|**mapisvc.inf 要求**|
|:-----|:-----|
|PR_DISPLAY_NAME= _string_ <br/> |可选  <br/> |
|PR_PROVIDER_DISPLAY= _string_ <br/> |必需  <br/> |
|PR_PROVIDER_DLL_NAME= _DLL 文件名_ <br/> |必需  <br/> |
|PR_RESOURCE_TYPE= _long_ <br/> |必需  <br/> |
|PR_RESOURCE_FLAGS= _位掩码_ <br/> |可选  <br/> |
   
通讯簿提供程序可以通过调用配置文件节的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法，或者通过修改 MAPISVC.INF 间接将此信息直接放入配置文件中。 配置文件是使用 MAPISVC 中相关信息构建的。所选服务提供商或邮件服务的 INF。 有关 MAPISVC 组织和内容的信息。INF，请参阅 [MapiSvc.inf 的文件格式](file-format-of-mapisvc-inf.md)。
  
通讯簿提供程序的 DLL 入口点函数的名称必须为 [ABProviderInit，](abproviderinit.md) 并且必须符合 **ABProviderInit** 原型。 在提供程序的 DLL 入口点函数中执行以下任务： 
  
- 检查 SPI (的服务提供商接口) 以确保 MAPI 使用的版本与通讯簿提供程序使用的版本兼容。
    
- 实例化通讯簿提供程序对象。
    
请勿在此函数中调用 **MAPIInitialize** 或 **MAPIUninitialize。** 
  
DLL 入口点函数实例化提供程序对象，并返回指向该对象的指针 MAPI。 
  

