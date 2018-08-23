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
ms.openlocfilehash: 68ba23e6ab23ff7306cd1326b73512b1c9f2a0f9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579674"
---
# <a name="implementing-an-address-book-provider-entry-point-function"></a>实现通讯簿提供程序入口点函数

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
当客户端应用程序调用[MAPILogonEx](mapilogonex.md)开始使用包含通讯簿提供程序的配置文件的会话时，MAPI 加载您的提供商和所有其他人的配置文件的一部分。 MAPI 提供程序的入口点函数的名称的学习通过查看配置文件中。 请记住此函数不是 DLL 入口点函数; 相同请参阅**DllMain** Win32 文档中的文档。 
  
有的每个通讯簿提供程序配置文件部分中包含的多个条目，其中某些必须 mapisvc.inf 配置文件中出现。 下表列出了这些模板部分条目和 mapisvc.inf 文件必须包括它们。
  
|**配置文件节项**|**mapisvc.inf 要求**|
|:-----|:-----|
|PR_DISPLAY_NAME =_字符串_ <br/> |可选  <br/> |
|PR_PROVIDER_DISPLAY =_字符串_ <br/> |必需  <br/> |
|PR_PROVIDER_DLL_NAME = _DLL 文件名_ <br/> |必需  <br/> |
|PR_RESOURCE_TYPE =_长_ <br/> |必需  <br/> |
|PR_RESOURCE_FLAGS =_位掩码_ <br/> |可选  <br/> |
   
通过调用其配置文件部分[IMAPIProp::SetProps](imapiprop-setprops.md)方法来直接或间接通过修改 MAPISVC.INF，通讯簿提供程序可以发出此信息传入一个配置文件。 配置文件是构建使用 MAPISVC 中的相关信息。选定的服务提供程序或消息服务的 INF。 有关的组织和 MAPISVC 内容的详细信息。INF，请参阅[的 MapiSvc.inf 文件格式](file-format-of-mapisvc-inf.md)。
  
通讯簿提供程序的 DLL 入口点函数的名称必须是[ABProviderInit](abproviderinit.md) ，并且它必须符合**ABProviderInit**原型。 在您的提供商 DLL 入口点函数中，执行以下任务： 
  
- 检查服务提供程序接口 (SPI) 以确保 MAPI 使用与使用通讯簿提供程序的版本兼容版本的版本。
    
- 实例化通讯簿提供程序对象。
    
不要在此函数调用**MAPIInitialize**或**MAPIUninitialize** 。 
  
DLL 入口点函数实例化提供商对象，并返回到 MAPI 指向该对象的指针。 
  

