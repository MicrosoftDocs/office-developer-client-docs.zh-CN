---
title: 使用Thread-Safe对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e688db5e-d1a1-4afc-998f-b3d31eb6239b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 611e0a49f0fd8df8fe40205a33ed5501055c3d45
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425167"
---
# <a name="using-thread-safe-objects"></a>使用Thread-Safe对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序可以假定直接使用的对象或作为回调的对象始终是线程安全的，但以下情况除外：
  
- 通过客户端调用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 获取的传输提供程序的状态对象，该对象具有提供程序的状态表行中的条目标识符。 
    
- 通过客户端调用 [MAPIOpenFormMgr](mapiopenformmgr.md)获取的所有 MAPI 表单对象。 Form 对象遵循单元模型规则，客户端必须使用它们，并且它们包含的所有对象都只能在创建它们的线程上使用。
    
当客户端访问包含关联状态对象的条目标识符的状态表中的传输提供程序行时，客户端可以使用该条目标识符调用 **OpenEntry** 以打开状态对象。 此状态对象不是线程安全的，因为传输提供程序在 MAPI 后台处理程序的上下文中运行，并且不会维护其状态对象的单独上下文。 状态对象遵守单元模型规则，客户端必须仅在创建它的线程上使用它。 
  
客户端还必须在任意 MAPI 对象之前调用每个线程上的[MAPIInitialize，](mapiinitialize.md)在使用该对象完成时调用[MAPIUninitialize。](mapiuninitialize.md) 即使要使用的对象从外部源传递到线程，也应进行这些调用。 **MAPIInitialize** 和 **MAPIUninitialize** 可以从任何位置调用，但 Win32 **DllMain** 函数除外，该函数在进程和线程初始化和终止时由系统调用，或在调用 **LoadLibrary** 和 **FreeLibrary** 函数时调用。 
  
间接使用对象永远不应假定为线程安全对象。 间接使用对象由需要目标接口指针作为输入参数的方法返回。 例如 **，IMAPIProp：：CopyTo** 和 CopyProps、IMAPIFolder：：CopyFolder 和 **CopyMessage** 和 **IMsgServiceAdmin：：CopyMsgService。**   如果服务提供商希望从传递该对象的线程外的其他线程调用此类对象，则提供程序负责显式封送该对象。
  

